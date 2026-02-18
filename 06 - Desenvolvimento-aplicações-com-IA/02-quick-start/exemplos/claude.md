# Project Overview

Video Max is a video processing platform that enables users to upload videos, extract audio (client-side using FFmpeg WebAssembly), transcribe using OpenAI Whisper, and generate AI-powered summaries with topic organization using Claude API. The platform features timestamp-grounded navigation linking text summaries to video positions.

---

## Environment Setup & Running

### Environment Status:
- Backend: `./env-scripts/backend-status.sh`
- Frontend: `./env-scripts/frontend-status.sh`
- Both: `./env-scripts/status-all.sh`

### Environment Initialization
- Backend: `./env-scripts/backend-init.sh`
- Frontend: `./env-scripts/frontend-init.sh`
- Both: `./env-scripts/init-all.sh`
- Both with migrations: `./env-scripts/init-all.sh --migrations` (recommended for the first time)

### Environment Stopping / Resetting
- Both: `./env-scripts/down-all.sh`
- Both with clean: `./env-scripts/down-all.sh --clean` (remove containers, volumes, and .env files)

### Running services
- Backend: `docker exec videomax_backend_dev uvicorn app.main:app --host 0.0.0.0 --port 3001 --reload`
- Frontend: `docker exec videomax_frontend_dev npm run dev`
- Frontend default port: 3000

### Migrations
- Run migrations: `docker exec videomax_backend_dev alembic upgrade head`
- Check current migration: `docker exec videomax_backend_dev alembic current`

**IMPORTANT**:
Always run any commands inside the containers. Omit `-it` flag.
- Backend: `docker exec videomax_backend_dev <command>`
- Frontend: `docker exec videomax_frontend_dev <command>`

---

## Project Structure

```text
video-transcriber/
├── backend/                # Python/FastAPI backend
│   ├── .env.example        # Example .env file
│   ├── .env                # Environment variables
│   ├── Dockerfile.dev      # Dockerfile for development
│   ├── docker-compose.yaml # Docker compose for backend
│   ├── app/
│   │   ├── api/            # API routes (v1)
│   │   ├── core/           # Configuration, database, security
│   │   ├── models/         # SQLAlchemy models
│   │   ├── schemas/        # Pydantic schemas
│   │   ├── services/       # Business logic services
│   │   ├── tasks/          # Background tasks (transcription, summary, cleanup)
│   │   └── utils/          # Utility functions
│   ├── alembic/            # Database migrations
│   ├── tests/              # pytest tests
│   │   ├── unit/           # Fast, isolated unit tests
│   │   └── integration/    # API endpoint tests
│   └── storage/            # Local file storage (videos, audio, temp)
├── frontend/               # Next.js/React frontend
│   ├── Dockerfile.dev      # Dockerfile for Frontend
│   ├── docker-compose.yaml # Docker compose for frontend
│   ├── .env.example        # Example .env file
│   ├── .env.local          # Local environment variables
│   └── src/
│       ├── __tests__/      # Jest tests
│       │   ├── unit/
│       │   ├── integration/
│       │   ├── components/
│       │   ├── pages/
│       │   └── hooks/
│       ├── app/            # Next.js app router pages
│       ├── components/     # React components
│       ├── contexts/       # React contexts (auth)
│       ├── lib/            # Utilities, API client, hooks, services, types
│       ├── mocks/          # MSW mock handlers for parallel development
│       └── public/         # Static assets (including ffmpeg WASM)
├── env-scripts/            # Environment setup scripts
└── docker-compose.yaml     # Database service

```

---

## Error Codes & Authentication

### Error Codes

Error codes follow the pattern `PREFIX###`:

* `AUTH0XX` – Authentication errors (AUTH001, AUTH002, etc.)
* `API0XX` – General API errors
* `UPLOAD0XX` – Upload-related errors
* `VIDEO0XX` – Video processing errors

### Authentication

* Bearer token in `Authorization` header
* Access token expires in 1 hour (configurable)
* Refresh token in HTTP-only cookie, expires in 7 days
* Account lockout after 5 failed attempts for 15 minutes

---

## Logging

Use structlog for logging:

```python
import structlog
logger = structlog.get_logger(__name__)
logger.info("event_name", user_id=str(user.id), action="login")

```

---

## Stack Details

### Backend

* **Framework**: FastAPI with async support
* **Database**: PostgreSQL 16 (Docker)
* **ORM**: SQLAlchemy with Alembic migrations
* **Auth**: JWT access tokens (HS256) + refresh tokens (HTTP-only cookies)
* **Password**: bcrypt with cost factor 12
* **External APIs**: OpenAI Whisper (transcription), Claude API (summaries)
* **Logging**: structlog with JSON format in production

### Frontend

* **Framework**: Next.js 15 with App Router
* **State Management**: React Query for server state, React Context for auth
* **Forms**: react-hook-form with zod validation
* **Styling**: Tailwind CSS 4
* **Mocking**: MSW (Mock Service Worker) for parallel development
* **Audio Extraction**: FFmpeg WebAssembly (@ffmpeg/ffmpeg) runs client-side

---

## Systems & Pipelines

### Upload System

* Chunked uploads with 5MB chunks for files up to 2GB
* Resume capability with 24-hour session expiry
* SHA256 checksum verification per chunk

### Video Processing Pipeline

1. User uploads video (chunked)
2. Frontend extracts audio using FFmpeg WASM
3. Audio sent to backend
4. Backend transcribes via OpenAI Whisper
5. Backend generates summary via OpenAI
6. Websocket notification to frontend

---

## Development & Testing

### Code Comments Policy

**Do not include task references in code comments.** Comments should describe what the code does and why, not which task from a planning document it implements.

### Testing - Backend

**Test database**: Uses SQLite in-memory by default. Override with `TEST_DATABASE_URL` env var.

**Pytest markers**:

* `@pytest.mark.unit` – Fast, isolated unit tests
* `@pytest.mark.integration` – API endpoint tests (require database)
* `@pytest.mark.slow` – Skip with `-m "not slow"`

**Available fixtures**:

* `db` – Database session with automatic rollback after each test
* `client` – FastAPI TestClient with dependency injection
* `test_user` – Verified user for authentication tests
* `unverified_user` – Unverified user for verification flow tests
* `auth_headers` – Dict with `{"Authorization": "Bearer <token>"}`
* `multiple_users` – List of 5 test users for pagination tests

**Helper functions in conftest.py**:

* `create_test_user_data()` – Generate valid registration data
* `create_login_data()` – Generate login payload

**Running tests:**
- `docker exec videomax_backend_dev pytest`                     # All tests
- `docker exec videomax_backend_dev pytest -v -k "test_name"`    # Specific test
- `docker exec videomax_backend_dev pytest tests/unit/`         # Unit tests only
- `docker exec videomax_backend_dev pytest tests/integration/`  # Integration tests only

### Frontend Testing

**Jest configuration:**
- Test environment: `jsdom` (browser simulation)
- Module alias: `@/` resolves to `src/`
- Setup file: `jest.setup.js` provides browser API mocks

**Testing patterns:**
- Use `render()` for components, `renderHook()` for hooks
- Use `screen.getByRole()`, `screen.getByText()` for queries
- Use `act()` for state updates
- Use `jest.useFakeTimers()` for timer-based tests

**Running tests:**
- `docker exec videomax_frontend_dev npm test -- --watchAll=false`                                  # All tests
- `docker exec videomax_frontend_dev npm test -- --testPathPattern="TestName" --watchAll=false`       # By name
- `docker exec videomax_frontend_dev npm test -- src/__tests__/pages/FileName.test.tsx --watchAll=false` # By file

**Important:** Always include `--watchAll=false` to avoid interactive mode.

### E2E Testing with Playwright
- `docker exec videomax_frontend_dev npx playwright test --reporter=list`

### Test Policy

- **Coverage reports:** Do NOT use `--coverage` or `--cov-report=html` unless explicitly requested
- **Playwright:** Always use `--reporter=list` (no generated folders)
- **When to run:**
    - All tests: Major changes, before PRs, when task files specify
    - Specific tests: Focused changes, during iteration

### Test Guidelines

**Do NOT Test:**
- Schema validation (Pydantic/Zod handles it)
- Simple CRUD (integration tests cover it)
- Component rendering ("renders without crashing")
- Framework behavior (React, FastAPI internals)
- Trivial utilities (`formatBytes`, `formatDate`)

**DO Test:**
- Critical user flows (auth, upload, core CRUD)
- Business logic with edge cases (lockout, quotas, permissions)
- Error handling (API errors, UI error states)
- State management (context operations)
- Edge cases

**Limits:**
- Max 10 tests per file
- Max 5 mocks per test
- If test file > implementation file -> too many tests

**Run related tests** after finishing a task step

---

## Git Policy

**Commit (conventional format):**
```bash
git commit -m "short description"

Detailed description if there are many files or changes

```

**Never:**

* Update git config
* Run destructive commands (force push, hard reset) without explicit request
* Skip hooks (`--no-verify`) unless requested
* Use `git commit --amend` unless explicitly safe
* Force push to main/master

---

### Common React Pitfalls

**Click propagation in Links:** Interactive elements inside Next.js Link must stop propagation:

```typescript
<div onClick={(e) => e.stopPropagation()} onMouseDown={(e) => e.stopPropagation()}>
  <DropdownMenu>...</DropdownMenu>
</div>

```

**React Hook Form refs:** Never override `register()` ref:

```typescript
// WRONG - ref gets overwritten:
<Input {...register('name')} ref={myRef} />

// RIGHT - use setFocus instead:
const { setFocus } = useForm();
useEffect(() => { setFocus('name'); }, []);

```

**Custom onChange handlers:** When creating components that wrap HTML inputs, support both standard `onChange` and custom callbacks:

```typescript
interface CheckboxProps {
  onChange?: React.ChangeEventHandler<HTMLInputElement>;
  onCheckedChange?: (checked: boolean) => void;
}

```

---

## Important Notes

* **Database types:** Uses custom SQLAlchemy types (GUID, JSONType, IntegerArrayType) for compatibility
* **After pulling:** Always run `docker exec videomax_backend_dev alembic upgrade head` after pulling changes with migrations

Frontend can be developed independently using MSW mocks:

* In `frontend/.env.local` use `NEXT_PUBLIC_USE_MOCKS=true`
* Mock handlers are in `frontend/src/mocks/handlers/`.



