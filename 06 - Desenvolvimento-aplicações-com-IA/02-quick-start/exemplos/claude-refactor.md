Restructure my CLAUDE.md into a layered system: a lean root file with universal rules, and dedicated files for context-specific guidance that the agent reads only when relevant.

**Steps:**

1. **Detect conflicts:** Scan for instructions that contradict each other. When you find one, show me both versions and ask which to keep.
2. **Extract the universal core:** The root CLAUDE.md should contain only:
    - Project summary (one paragraph)
    - Tech stack: language, framework, runtime
    - Environment: how to start, how to verify it's running, how to stop
    - Folder structure: main directories and their purpose, 2-3 levels deep for stable paths
    - Build tooling: package manager, build/lint/typecheck commands (only if non-standard)
    - Test commands: how to run all tests, a single test file, or a specific test
    - Rules that apply regardless of what task is being performed
3. **Split by task type:** Move everything else into separate files based on when the agent would need them:
    - Code style and naming
    - How to write and organize tests
    - API and endpoint design
    - Commit messages and branching
    - Project structure and file placement
4. **Link with triggers:** In the root file, tell the agent when to check each file.
    
    Example: "When adding a new route, first read `.claude/api-patterns.md`"
    
5. **Make vague rules concrete:** For any instruction that sounds abstract, rewrite it to include:
    - The specific action to take
    - A brief example if it helps
    - Why it matters (when non-obvious)
6. **Challenge each instruction:** For every rule, ask:
    - "Would the agent behave differently without this?"
    - Collect the ones that fail this test and show them to me with a one-line reason for each.
    - Wait for my confirmation before removing any.
7. **Output the new structure:**
    - Rewritten root CLAUDE.md (minimal, with pointers to other files)
    - Each specialized file with its instructions
    - Recommended folder layout (e.g., `.docs/guidelines/`)