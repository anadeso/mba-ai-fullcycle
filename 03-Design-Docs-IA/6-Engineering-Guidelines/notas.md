# 📘 Software Development Guidelines

## 1. Contexto Geral do Capítulo

Neste capítulo, será abordado de forma mais aprofundada um tipo essencial de **design doc**, indispensável no desenvolvimento de software — especialmente no contexto atual, em que a **inteligência artificial** faz parte do processo.

Além desse documento principal, também serão apresentados os conceitos de:

* **Development Guidelines**
* **Engineering Guidelines**

Ao final do módulo, será apresentado um **mind map organizado**, mostrando outras categorias de design docs que não serão exploradas em profundidade neste momento, mas que aparecerão ao longo do curso.

Alguns desses documentos podem não ser criados diretamente pelos desenvolvedores, porém serão utilizados de forma indireta no dia a dia do projeto.

O próximo passo será entender melhor os **Software Development Guidelines**.

---

# 2. Guidelines na Era da IA

## 2.1 Conceito

As **Software Development Guidelines** são um tipo essencial de documento dentro do conjunto de design docs, especialmente no contexto atual com uso intensivo de **inteligência artificial** no desenvolvimento.

Elas representam um:

> **Conjunto de regras e boas práticas que orientam como o software deve ser escrito, organizado e evoluído.**

Não necessariamente existe apenas um documento desse tipo. Podem existir múltiplas guidelines, inclusive específicas para determinados domínios, times ou áreas da organização.

Algumas empresas adotam padrões corporativos mais rígidos; outras permitem variações entre equipes.

---

## 2.2 Escopo das Guidelines

Guidelines não tratam apenas de **estilo de código**, embora isso também faça parte.

Elas definem:

* Processo de desenvolvimento em nível de código
* Linguagem utilizada
* Frameworks adotados
* Padrões técnicos
* Estrutura do processo de desenvolvimento

Enquanto arquitetura atua no nível **macro**, as guidelines atuam no nível **micro**, focado diretamente no ato de programar.

---

## 2.3 Importância das Guidelines

### 1️⃣ Onboarding automático pela IA

A IA pode ser vista como um novo membro da equipe.
Quando guidelines estão documentadas, a IA absorve o conhecimento como se tivesse passado por onboarding.

---

### 2️⃣ Redução de divergência e aumento de consistência

Sem orientações claras, a IA pode gerar código inconsistente.
Guidelines garantem padrão uniforme no projeto.

---

### 3️⃣ Facilidade para iniciar novos projetos

Com estrutura definida, novos projetos são iniciados com mais clareza.

---

### 4️⃣ Redução de erros e retrabalho

Guidelines permitem:

* Pré-commit checks
* Validações automatizadas
* Redução de inconsistências

---

### 5️⃣ Redução de ruído em code review

Sem guidelines:

* Pull requests com muitos arquivos alterados
* Refatorações desnecessárias
* Commits inconsistentes

Com guidelines claras:

* Alterações fora do escopo são evitadas
* Revisões ficam mais eficientes

---

### 6️⃣ Agentes especializados em paralelo

Hoje existem agentes especializados (front-end, back-end, CI/CD etc.).

Sem guidelines:

* Cada agente pode seguir padrões diferentes

Com guidelines:

* O padrão é ditado pelo projeto
* Evita-se bagunça de padrões

---

### 7️⃣ Code review automático

Agentes podem validar aderência às regras definidas.

---

### 8️⃣ Previsibilidade em ambientes multimodais

Guidelines podem especificar:

* Diagramas C4
* Padrões visuais
* Diretrizes de front-end
* Uso de imagens

Isso aumenta previsibilidade e qualidade.

---

# 3. Seções Sugeridas de um Guidelines

Antes de definir seções, a pergunta central é:

> **Como o software será desenvolvido na prática?**

As guidelines podem incluir:

---

## 3.1 Core Principles

Princípios fundamentais que não devem ser quebrados.

---

## 3.2 Inicialização do Projeto

* Como subir o ambiente
* Rodar scripts
* Executar migrações

---

## 3.3 Estrutura e Ambiente

* Containers
* Dockerfile
* Docker Compose

---

## 3.4 Convenções Técnicas

* Convenções de nomes
* Tipagem
* Funções e métodos
* Tratamento de erros
* Concorrência
* Abstrações

---

## 3.5 Testes

* Testes de unidade
* Mocks
* Integração
* Estresse e carga

---

## 3.6 Performance e Diagnóstico

* Profiling
* Benchmarks
* Otimização

---

## 3.7 Segurança

Diretrizes críticas de desenvolvimento seguro.

---

## 3.8 Padrões de Código

Boas e más práticas claramente definidas.

---

## 3.9 Dependências

* Gerenciamento por linguagem
* Gerenciadores de pacotes

---

## 3.10 Comentários e Documentação

Como comentar código e integrar com documentação.

---

## 3.11 Banco de Dados, Logs e Observabilidade

Diretrizes de persistência e monitoramento.

---

## 3.12 Golden Rules

Checklist consolidado para validação pré-commit.

---

## 3.13 Referências

Links e documentos internos/externos.

---

# 4. Project Stack

Um dos primeiros elementos das guidelines é a **Stack**.

Ela deve deixar claro:

* Tecnologias usadas
* Frameworks
* ORM
* Testes
* Banco de dados

Exemplo prático:
📄 `Project Stack Guidelines`

Também pode incluir:

* Bibliotecas
* Links de documentação

Itens podem ser:

* **User Specified**
* **Auto-populated**

---

# 5. Documento como um Todo e Pre-Commit

Após definir a stack, entram os:

## 5.1 Core Principles (exemplo com Go)

* Simplicidade
* Formatação oficial
* Evitar abstrações excessivas
* Uso de golangci-lint e staticcheck

---

## 5.2 Ferramentas Principais

* Formatação
* Imports
* Lint
* Análise estática

---

## 5.3 Inicialização do Projeto

* Dependências
* Estrutura
* Organização de diretórios

---

## 5.4 Containers

* Dockerfile
* Docker Compose
* Volumes
* Postgres
* Dockerignore
* Comandos

---

## 5.5 Convenções Técnicas

* Makefiles
* PascalCase
* Type safety
* Organização

---

## 5.6 Funções e Métodos

* Assinaturas
* Retorno de erros
* Error handling

---

## 5.7 Concorrência

* Goroutines
* Context
* Cancellation

---

## 5.8 Testes

* Table-driven tests
* Dependency injection
* Test doubles

---

## 5.9 Testes Avançados e Performance

* Integração
* Profiling
* Benchmarks

---

## 5.10 Segurança e Qualidade

* Validação de inputs
* Logs
* Observabilidade

---

## 5.11 Pre-Commit Checklist

Antes de commitar:

* Código compila
* Testes passaram
* Erros tratados
* Docker válido
* Documentação atualizada

---

# 6. Comando para Geração de Guidelines – Parte 1

Comando:

```
generate development guideline
```

Permite parâmetros como:

* `--rm=prisma`
* `--web=express`
* `--db=mysql`
* `--test=jest`
* `--log=log4j`

Exemplo:

```
generate-guideline go --rm=sqlc --db=pgx --test=testify
```

---

## 6.1 Fase 1 – Interpretação

* Extrai parâmetros
* Separa User Specified e Auto-populated
* Gera JSON estruturado

---

## 6.2 Fase 2 – Pesquisa

Pesquisa sobre:

* Linguagem
* Bibliotecas
* Boas práticas
* URLs
* Versões

---

# 7. Comando – Parte 2

## 7.1 Análise e Planejamento

Decide:

* O que entra
* O que não entra
* Numeração
* Justificativas

---

## 7.2 Fase 3 – Geração Incremental

Divide o documento em subfases.

Cada seção:

* 30–50 linhas
* Limite de 32k tokens

---

## 7.3 Validações

* Numeração
* Consistência
* Autenticidade da linguagem
* Completude

---

## 7.4 Checklist Final

Valida:

* Documento entre 1.000 e 1.500 linhas
* Se exceder → resume
* Remove verbosidade

---

# 8. Geração na Prática

Exemplo:

```
/guidelines generate
```

Parâmetros:

* PHP
* Laravel
* Postgres
* PHPUnit
* React / Next.js

---

## 8.1 Parsing da Stack

Autopopula:

* Monolog
* Composer

---

## 8.2 Research

Pesquisa oficial e padrões do ecossistema.

---

## 8.3 Geração Incremental

Exemplo com PHP:

* Remove concorrência
* Remove benchmarks
* Remove testes de carga

---

## 8.4 Controle de Tamanho

Se ultrapassar 1.500 linhas:

* Resume
* Remove exemplos longos
* Ajusta seções

---

# 9. Classificação de Documentos

## 9.1 Documentos de Produto

* PRD
* User stories
* Epics
* FRD

---

## 9.2 Design e Arquitetura

* High-Level Design
* Feature Design Doc
* ADR
* Modelo C4
* AI Design Docs
* Prompt Specs
* RFC
* LLD
* TRD

---

## 9.3 Conhecimento e Referência

* Engineering Guidelines
* Security Design Docs
* Test plans
* Test cases formais

---

## 9.4 Operacionais e Infraestrutura

### Operacionais

* Runbooks
* Playbooks
* Observabilidade
* SRE

### Infraestrutura

* CI/CD
* Infra design docs

---

# Conclusão

A organização apresentada:

* Estrutura o conteúdo de forma progressiva
* Mantém todos os tópicos originais
* Agrupa conceitos relacionados
* Facilita leitura, consulta e reutilização

O conteúdo permanece integral, apenas reorganizado para maior clareza estrutural.
