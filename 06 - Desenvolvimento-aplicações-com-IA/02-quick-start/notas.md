# Quick Start — Guia Completo Estruturado

## O que é o Quick Start?

O Quick Start é a base operacional da IA dentro do projeto.
Ele não é apenas um guia de instalação — é o documento que garante:

* Inicialização correta
* Execução consistente
* Redução de erros
* Economia de tokens
* Paralelização estruturada

Ele é parte estratégica do projeto e não é substituído por README.

---

# Pontos Essenciais (Não Subestime)

O agente precisa obrigatoriamente saber:

* Instalar o ambiente do zero (from scratch)
* Reconhecer se o ambiente já está rodando
* Resetar ou desinstalar o ambiente
* Verificar status rapidamente

Sem isso, a IA:

* Se perde
* Explora desnecessariamente o codebase
* Gasta tokens
* Entra em tentativa e erro

---

# Etapas Básicas para Qualquer Aplicação

## 1. Inicialização

O agente deve:

* Iniciar backend e frontend sem exploração excessiva
* Rodar scripts claramente definidos
* Lidar com migrations
* Subir o ambiente completo com comandos simples

Objetivo: zero ambiguidade.

---

## 2. State (Estado do Sistema)

O agente precisa entender rapidamente:

* O sistema está rodando?
* Quais serviços estão ativos?
* Há migrations pendentes?
* O banco está acessível?

O estado deve ser simples, objetivo e rápido.

---

## 3. Desenvolvimento

O agente precisa:

* Clareza sobre o que desenvolver
* Clareza sobre como desenvolver
* Saber por onde começar
* Saber retomar trabalho em andamento
* Aprender ao longo do tempo (evolução do arquivo)

Não basta um bom prompt — precisa de estrutura.

---

## 4. Testabilidade e Feedback

O agente precisa:

* Validar o próprio trabalho
* Rodar testes automaticamente
* Ter comandos claros de teste
* Receber feedback rápido

O time precisa:

* Melhorar mecanismos de validação continuamente
* Revisar esse fluxo com frequência

---

# O que deve conter um arquivo de inicialização (CLAUDE.md / AGENTS.md / GEMINI.md)

## 1. Contexto do Projeto (1 linha clara)

Exemplo:
API REST com FastAPI para autenticação de usuários usando SQLAlchemy e Pydantic.

Objetivo: orientar imediatamente o agente.

---

## 2. Comandos Frequentes (explícitos)

Evitar que o agente adivinhe flags.

Exemplo:

```bash
docker exec backend pytest
docker exec backend pytest -v
docker exec backend pytest -k "test_name"
```

Incluir:

* Build
* Test
* Lint
* Typecheck
* Start
* Stop

---

## 3. Guias de Estilo Concretos

Evite instruções vagas como:
“Formate corretamente”

Prefira:

* Use ES Modules
* TypeScript strict
* 2 espaços de indentação
* Proibido `any`

Regra: nada vago.

---

## 4. Diretórios-chave

Especialmente importante para monorepos:

* /backend
* /frontend
* /tests
* /docs
* /scripts

Ajuda na navegação eficiente.

---

## 5. Workflow do Time

* Como abrir PR
* Regras de branch
* Code review
* Limite de escopo
* Quando validação manual é obrigatória

---

## 6. Observações de Ambiente

* Variáveis obrigatórias
* Problemas comuns
* Regras específicas de infraestrutura
* Portas padrão

---

## 7. Regras Globais da Empresa

* Nunca fazer push direto na main
* Revisar commit antes de enviar
* Não duplicar testes já cobertos

---

## 8. Importação de Arquivos (@path)

Dividir quando crescer.

Exemplo:

```
@docs/code-styles.md
@docs/api-patterns.md
```

Regra geral:

O que deve ser sempre carregado fica no root.
O restante deve ser carregado sob demanda.

---

# O que NÃO deve ter no arquivo

Não incluir:

* Nomes de arquivos que o agente já consegue identificar
* Documentação extensa de bibliotecas
* Conteúdo que muda constantemente
* Código inseguro
* Texto longo e redundante

Princípio: incluir apenas o que altera o comportamento do agente.

---

# Como Evoluir o Arquivo

* Comece pequeno (init gera apenas esqueleto)
* Revise com frequência
* Faça code review do próprio arquivo
* Divida por temas
* Destaque itens críticos
* Sincronize com Skills
* Remova contradições

O arquivo é vivo.

---

# Já tenho o arquivo, como melhorar?

1. Detecte conflitos
2. Extraia o núcleo universal
3. Separe por tipo de tarefa
4. Referencie arquivos com triggers claros
5. Transforme regras vagas em regras concretas
6. Teste cada regra:

   * O agente agiria diferente sem isso?

---

# Estrutura Ideal (Sistema em Camadas)

Root (mínimo e universal):

* Resumo do projeto
* Stack
* Ambiente
* Estrutura de pastas
* Comandos principais
* Regras universais

Arquivos especializados:

* Code style
* Testes
* API patterns
* Commits
* Estrutura

Com triggers explícitos:

“When adding a new route, read `.claude/api-patterns.md`”

---
Excelente ponto.

Sim — esse trecho faz parte do tema **“Como evoluir o arquivo ao longo do projeto”**, mas ele merece virar um **subtópico próprio**, porque trata especificamente do **feedback loop inteligente com a IA**.

Abaixo está a versão incorporada ao resumo, estruturada corretamente e sem elementos emocionais.

---
# Feedback Loop com a IA (Evolução Contínua do Arquivo)

## Conceito Central

O arquivo de inicialização (CLAUDE.md, AGENTS.md, etc.) deve evoluir com base nos erros e dificuldades reais enfrentadas pela IA durante o desenvolvimento.

O desenvolvimento é vivo.
O arquivo também precisa ser.

---

## Técnica Prática Recomendada

Sempre que:

* Uma tarefa foi difícil
* A IA errou muito antes de acertar
* O processo foi confuso
* Houve retrabalho

Faça a seguinte pergunta para a IA:

> “Percebi que você encontrou pontos complexos durante esse processo. Elenque esses pontos de forma extremamente concisa para que eu possa adicioná-los ao meu Cloud.md (ou arquivo equivalente) e evitar erros futuros.”

A IA tende a identificar exatamente:

* Onde ela sofreu
* Onde houve ambiguidade
* Onde faltou regra
* Onde faltou contexto
* Onde houve conflito de instrução

---

## O Que Fazer com a Resposta

1. Inserir os pontos no arquivo principal
2. Reestruturar seções, se necessário
3. Tornar instruções vagas em regras concretas
4. Detalhar pontos críticos
5. Enxugar trechos redundantes

Com o tempo, você perceberá:

* Algumas seções precisam ser reduzidas
* Outras precisam ser aprofundadas
* Novos tópicos surgirão
* Estrutura precisará ser reorganizada

---

## Regra Fundamental

Sempre pergunte à IA:

* Por que isso foi difícil?
* Onde você sofreu?
* O que faltou para ser mais preciso?

Se a IA está sofrendo constantemente, o problema provavelmente está em:

* Workflow mal estruturado
* Prompt mal definido
* Arquivo de inicialização incompleto
* Codebase confuso

A IA não deveria “apanhar” repetidamente para resolver o mesmo tipo de problema.

---

## Impacto do Feedback Loop

Quando o ciclo é aplicado corretamente:

* Erros recorrentes desaparecem
* A IA se torna progressivamente mais precisa
* O retrabalho diminui
* A frustração reduz drasticamente
* Modelos mais baratos e rápidos passam a resolver tarefas complexas

Isso reduz custo e aumenta produtividade.

---

## Essência do Capítulo

Embora pareça básico, esse mecanismo de refinamento contínuo é um dos pontos mais estratégicos do curso.

A diferença entre:

* Usar IA de forma reativa
* Construir um sistema onde a IA evolui com você

Está exatamente nesse ciclo de aprendizado estruturado.

---
# Essência Final do Quick Start

Ele é:

* Base de produtividade
* Redutor de tokens
* Acelerador de workflows
* Facilitador de paralelização
* Fundamento do Spec Driven Development

Sem ele, não existe desenvolvimento agêntico consistente.

--- 
### Prompt de Exemplo 

[Ver exemplos de arquivos de inicialização do agente](exemplos/claude.md)

### Prompt de Exemplo 

[Ver exemplos - otimizando arquivos existentes](exemplos/claude-refactor.md)