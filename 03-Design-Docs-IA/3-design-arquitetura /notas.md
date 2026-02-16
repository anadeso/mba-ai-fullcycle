# Design e Arquitetura na Era da IA

Após a definição do **PRD (Product Requirement Document)**, o próximo passo natural é estruturar o **design e a arquitetura técnica** do sistema.

Esses documentos são responsáveis por definir:

* **O que será construído tecnicamente**
* **Como o sistema será desenhado**
* **Como os componentes se conectam**
* **Quais decisões arquiteturais serão tomadas**

Nem todo projeto exige todos os documentos.
O nível de formalidade depende de:

* Tamanho da empresa
* Complexidade do sistema
* Criticidade do projeto
* Maturidade técnica do time

Em empresas maiores, é comum haver múltiplos níveis de documentação (alto e baixo nível).
Em contextos menores, alguns documentos podem ser consolidados.

---

## IA como Aliada (mas não substituta)

A IA não consegue inventar regras de negócio ou decisões estratégicas sozinha. Não existe “prompt mágico” que gere arquitetura perfeita sem contexto.

Ela pode ajudar em:

* Estruturação de documentos
* Entrevistas guiadas
* Organização de ideias
* Geração de rascunhos
* Reorganização de pesquisas extensas
* Uso posterior da documentação como contexto para desenvolvimento assistido

O conhecimento do domínio continua sendo indispensável.

---

# Principais Documentos de Design

## 1. HLD — High Level Design

Documento técnico de alto nível que apresenta a **visão macro da arquitetura do sistema**.

Responde perguntas como:

* Como o sistema é estruturado?
* Quais são os principais componentes?
* Como eles se comunicam?
* Quais tecnologias e padrões serão usados?

### Pode incluir:

* Diagramas (ex: C4)
* Serviços e APIs
* Modelo de dados em alto nível
* Interfaces públicas
* Escalabilidade
* Segurança
* Disponibilidade
* Observabilidade
* Principais riscos

O HLD é mais técnico que o PRD, mas ainda não entra no nível detalhado de implementação.

Ele serve como base para documentos mais específicos, como o FDD ou LLD.

---

## 2. FDD — Feature Design Doc

Documento técnico focado na **implementação de uma feature específica**.

É mais detalhado que o HLD e mais próximo da implementação.

Responde perguntas como:

* Como a feature funciona em runtime?
* Quais contratos ela expõe?
* Como é configurada?
* Como trata erros?
* Como validar sua implementação?

### Normalmente inclui:

* Contexto e objetivos técnicos
* Escopo e exclusões
* Fluxos detalhados
* Contratos (endpoints, headers, interfaces)
* Tratamento de erros
* Concorrência
* Observabilidade
* Dependências
* Critérios técnicos de aceitação
* Riscos e mitigação

Com um FDD bem estruturado, já é possível iniciar a implementação.

---

## 3. LLD — Low Level Design

Documento extremamente detalhado.

Inclui:

* Endpoints específicos
* Estruturas de dados
* Regras exatas
* Padrões de implementação
* Contratos entre sistemas

Nem sempre é necessário se o FDD já estiver suficientemente detalhado.

---

## 4. ADR — Architecture Decision Record

Registra decisões arquiteturais e suas justificativas.

Serve para:

* Manter histórico técnico
* Entender o porquê das escolhas
* Evitar rediscussões desnecessárias

---

## 5. RFC — Request for Comments

Documento de discussão técnica antes de uma decisão formal.

Diferença:

* **RFC → discute**
* **ADR → formaliza**

---

# High Level Design (HLD) — Aprofundamento

O HLD define a estrutura macro do sistema.

Ele:

* Não permite implementação direta
* Não entra em código
* Não detalha contratos específicos
* Fornece clareza arquitetural

As seções não são rígidas e devem ser adaptadas ao contexto.

---

## Exemplo: HLD de um Rate Limiter

Estudo de caso: Rate Limiter implementado como SDK em Go.

### Objetivo

Controlar requisições por:

* API Key
* IP
* Plano do cliente

Garantindo:

* Isolamento entre clientes
* Proteção contra sobrecarga
* Previsibilidade

### Estratégias

* Fixed Window
* Token Bucket

### Arquitetura

* SDK em Go
* Middleware HTTP (in-process)
* Redis ou memória local
* Docker Compose (dev)
* Kubernetes (produção)

### Considerações

* P95 < 5ms
* Observabilidade (Prometheus, OpenTelemetry)
* Segurança (abuso, replay, flood)
* Riscos (hotkeys, indisponibilidade Redis)
* Fallback open

Esse documento define a visão estrutural, mas não entra na implementação detalhada.

---

# Prompt para HLD

Pode-se usar um prompt estruturado para:

* Entrevistar o usuário
* Coletar objetivos técnicos
* Definir arquitetura
* Identificar riscos
* Organizar modelo de dados

O valor principal está no **template estruturado**, não na entrevista em si.

---

# Feature Design Doc (FDD) — Aprofundamento

O FDD detalha a feature dentro da arquitetura já definida.

Ele:

* Reduz ambiguidades
* Define contratos
* Explicita comportamento
* Permite implementação segura

---

## Exemplo: FDD do Rate Limiter

### Define:

* API pública estável
* Estratégias de rate limiting
* Redis e memória local
* Middleware HTTP
* Atomicidade (Lua / mutex)
* Headers de rate limit
* Telemetria
* Fallback permissivo

### Inclui:

* Escopo
* Exclusões
* Segurança
* Concorrência
* Métricas
* Critérios de aceite
* Riscos e mitigação

Com isso, já é possível começar o desenvolvimento.

---

# Deep Research com IA

Deep Research é usada para gerar base técnica sólida antes da escrita dos documentos.

Exemplo: PDF técnico de 27 páginas sobre Rate Limiting em Go.

Inclui:

* Estratégias
* Bibliotecas
* Conceitos arquiteturais
* Pontos críticos
* Aplicações práticas

---

## Processo de Deep Research

### Fase 1 — Entrevista Preparatória

Coleta:

* Tema técnico
* Problema
* Contexto
* Tecnologias
* Profundidade desejada
* Requisitos críticos

Gera resumo estruturado antes da pesquisa.

---

### Fase 2 — Execução e Estruturação

Após gerar o PDF:

* Importar no chat
* Rodar segundo prompt
* Reorganizar conteúdo
* Adaptar a um template estruturado

Importante:

* Garantir que nada seja omitido
* Revisar criticamente
* Adaptar ao formato desejado

---

# Adaptando Deep Research

Um template estruturado pode incluir:

1. Contexto
2. Fundamentos
3. Conceitos-chave
4. Abordagens existentes
5. Arquiteturas
6. Estratégias e algoritmos
7. Tecnologias
8. Boas práticas
9. Diretrizes técnicas
10. Métricas
11. Casos de uso
12. Riscos
13. Segurança
14. Tendências
15. Impacto

Esse template facilita:

* Reaproveitamento
* Criação de FDD
* Organização do conhecimento

---

# Gerando um FDD a partir da Deep Research

Processo prático:

1. Usar Deep Research como base
2. Usar HLD definido
3. Usar template de FDD
4. Enviar tudo para IA
5. Gerar rascunho estruturado

O ponto-chave:

O contexto forte é mais importante que o prompt sofisticado.

---

# Principais Aprendizados

## 1. Nunca parta do zero

Templates e pesquisa estruturada reduzem drasticamente o esforço inicial.

## 2. Não existe prompt mágico

O processo envolve:

* Iteração
* Ajustes
* Revisões

## 3. Templates são ativos estratégicos

Eles:

* Reduzem fricção
* Evitam esquecimentos
* Padronizam documentos

## 4. Documentação é um asset

Mesmo não sendo a parte mais prazerosa, ela:

* Estrutura o pensamento
* Permite uso estratégico de IA
* Reduz ambiguidade
* Facilita manutenção
* Melhora qualidade do software

## 5. Engenharia de software é ciclo completo

Não é apenas escrever código.

Envolve:

* Pesquisa
* Design
* Documentação
* Implementação
* Evolução
* Atualização contínua

---

# Conclusão Geral

Com:

* Deep Research estruturada
* HLD bem definido
* FDD detalhado
* Templates organizados
* Uso estratégico de IA

Você:

* Evita começar do zero
* Trabalha com mais clareza
* Reduz ambiguidade
* Melhora qualidade técnica
* Aumenta eficiência no desenvolvimento

Documentação deixa de ser burocracia e passa a ser parte ativa do processo de engenharia moderna — especialmente na era da IA.


