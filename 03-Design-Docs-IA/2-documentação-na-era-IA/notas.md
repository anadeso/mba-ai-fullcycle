## Documentação na era da IA

Na era da Inteligência Artificial, a documentação deixou de ser apenas um complemento do projeto e passou a fazer parte ativa do desenvolvimento de software.

Hoje, a IA consegue ler a documentação e utilizá-la como contexto para gerar código, planejar funcionalidades, fazer manutenção e evitar erros — assim como testes automatizados evitam regressões ao longo do tempo. Ou seja, a documentação se torna um ativo estratégico e duradouro do projeto.

Cada novo chat com a IA pode ser visto como a chegada de um “novo funcionário”. Para que ele entenda o projeto rapidamente, além do código, ele precisa de uma documentação clara. Isso traz mais assertividade no desenvolvimento e mais segurança para o time.

Além disso, a própria IA pode ajudar a criar e melhorar a documentação de forma mais rápida e eficiente. E mais importante: ela pode manter a documentação atualizada automaticamente dentro do workflow. Sempre que uma feature for criada ou alterada, a IA pode atualizar os documentos correspondentes.

Assim, a documentação finalmente pode se tornar um documento vivo de verdade — integrada ao fluxo de desenvolvimento, sendo criada, utilizada e atualizada continuamente com apoio da IA.

## Tipos de documentação e Design Docs
Nem toda documentação é igual — e entender essa diferença é essencial. Em um projeto de software, existem diferentes categorias de documentos, cada uma com um papel específico:

* **Produto** → define *o quê* está sendo construído e *por quê*.
* **Design e Arquitetura** → define *como* o sistema será construído.
* **Infraestrutura** → define *onde* e *com o quê* o sistema será executado.
* **Operacional** → define *como manter* a aplicação.
* **Conhecimento e Referência** → define *como trabalhar* no projeto.

O ponto central é que **design docs não são qualquer documento**, nem um único arquivo isolado. Eles são um **conjunto de documentações técnicas** que explicam como o software é desenhado, provisionado, mantido e guiado por boas práticas.

Enquanto a documentação de produto foca na visão estratégica (*o quê e por quê*), os **design docs** estão no nível técnico — cobrindo arquitetura, infraestrutura, operação e padrões de trabalho.

Ter clareza sobre essas categorias evita confusão e melhora a comunicação do time. Cada tipo de documento tem um objetivo diferente dentro do projeto.

Na disciplina, o foco está justamente em entender:

* quais são os principais design docs,
* quando usar cada um,
* qual o tamanho adequado,
* como estruturá-los,
* e como gerar e manter tudo isso com apoio da IA.

Com Inteligência Artificial e Prompt Engineering, é possível criar, atualizar e evoluir esses documentos de forma inteligente e integrada ao fluxo de desenvolvimento.

Em resumo: **design docs são a base técnica estruturada do projeto — e, com IA, eles se tornam muito mais estratégicos e eficientes.**

## PRDs - Product Requirement Document
O PRD é um documento focado em produto. Ele define e contextualiza o que será construído, qual valor será entregue e por que aquilo existe. Mesmo não sendo um design doc técnico, ele é extremamente importante — especialmente na era da IA — porque fornece o contexto necessário para que a inteligência artificial entenda o projeto.

O principal objetivo de um PRD é alinhar produto e time técnico. Ele deve existir quando há uma entrega clara de valor para o usuário ou para o negócio. Pode representar:

Um produto inteiro

Um módulo (ou EPIC)

Uma feature muito relevante

Mas atenção: nem toda feature merece um PRD. Apenas aquelas que são estratégicas, complexas ou entregam alto valor percebido. Quando algo deixa de ser apenas um requisito funcional e passa a ter objetivos, métricas e impacto próprio, faz sentido tratá-lo como um “subproduto” — e, nesse caso, criar um PRD.

Outro ponto importante é que existem níveis de PRD, dependendo da granularidade:

PRD de alto nível → visão geral do produto.

PRD de módulo/EPIC → detalha uma grande parte do sistema.

PRD de feature estratégica → foca em algo altamente relevante.

Mesmo sendo um documento de produto, ele pode e deve conter informações técnicas quando necessário para alinhar expectativas.

Na prática, o PRD é um documento de contextualização estratégica. Para humanos, pode parecer óbvio documentar algo que o time já conhece. Mas para a IA, esse contexto é essencial. Quanto melhor o PRD, mais assertiva será a geração de código, planejamento e decisões técnicas.

Em resumo:
PRD não é um design doc, mas é a base contextual que orienta os design docs e melhora significativamente o uso da IA no desenvolvimento.

### Seções de um PRD
Um **PRD é flexível** — não existe um modelo rígido obrigatório. Nem todo projeto precisa de todas as seções, especialmente projetos menores. O importante é entender os blocos mais comuns e usar o que fizer sentido.

As principais seções normalmente incluem:

* **Visão e propósito** → explica a ideia central do produto e por que ele existe.
* **Contexto e oportunidade** → mostra qual problema está sendo resolvido e qual benefício isso traz para a empresa.
* **Público e personas** → define quem será impactado ou utilizará o produto.
* **Objetivos e métricas** → deixa claro o que se quer alcançar e como medir sucesso (KPIs).
* **Escopo** → define o que está dentro e o que está fora do projeto.
* **Requisitos de alto nível** → descrevem as grandes capacidades do sistema (macro funcionalidades).
* **Estratégia e fases** → como o produto será desenvolvido ao longo do tempo.
* **Riscos** → possíveis problemas ou incertezas.
* **KPIs** → indicadores de desempenho para acompanhar evolução e sucesso.
* **Stakeholders** → todas as pessoas envolvidas ou impactadas pelo projeto.

O ponto central é que um PRD organiza a visão estratégica do produto: define propósito, valor, limites e critérios de sucesso. Ele não entra em detalhes técnicos profundos, mas estrutura o entendimento do que será construído e como medir se deu certo.

Em resumo:
**O PRD organiza visão, valor, escopo e métricas — servindo como guia estratégico antes da execução técnica.**

### PRDs de Alto Nível
O **PRD de alto nível** é um documento macro, usado principalmente em projetos grandes. Ele não entra em detalhes técnicos — ele contextualiza estrategicamente o produto como um todo.

Esse tipo de PRD responde perguntas essenciais como:

* Por que o produto existe?
* O que queremos alcançar?
* O que está dentro e fora do escopo?
* Para quem estamos construindo?
* Qual problema estamos resolvendo?
* Como vamos atingir os objetivos?
* Como saberemos se deu certo?
* Quais são os riscos?
* Qual o roadmap?
* Quem está envolvido?
* Como isso se conecta à estratégia da empresa?

Perceba que muitas dessas perguntas são estratégicas e, em muitos casos, vêm de decisões da alta gestão. Mesmo que você seja desenvolvedor e não participe dessas decisões, entender essas respostas é fundamental. Se você não consegue responder essas perguntas, provavelmente não tem clareza suficiente sobre o projeto.

O PRD de alto nível garante alinhamento, direção e propósito antes da execução. Ele define a visão ampla do produto e serve como base para decisões futuras — inclusive para que a IA compreenda o contexto geral.

Em resumo:
**O PRD de alto nível é o mapa estratégico do produto — ele traz clareza sobre propósito, valor, direção e sucesso antes da construção começar.**

### PRDs de feature e caso de uso
Aqui vai o resumo sobre **PRDs de Feature e Caso de Uso**:

Além do **PRD de alto nível**, que traz a visão estratégica do produto como um todo, também existem **PRDs de nível mais baixo**, focados em módulos ou features específicas.

A diferença está na **relevância e impacto da feature**.

#### Quando NÃO vale criar um PRD de feature

Se a funcionalidade é apenas um requisito técnico padrão — algo comum, já resolvido por frameworks e que não envolve decisões estratégicas de produto — então ela não precisa de um PRD próprio.

Exemplo:

* Um sistema de login simples e padrão.
* Apenas autenticação básica necessária para acessar a plataforma.
* Nenhuma inovação, diferencial ou impacto estratégico.

Nesse caso, o login é apenas um requisito funcional dentro de um PRD maior.

---

#### Quando vale criar um PRD de feature

Se a feature:

* Envolve decisões estratégicas de produto
* Impacta experiência do usuário
* Tem métricas próprias
* Envolve riscos, compliance ou integrações complexas
* Pode ser considerada quase um “subproduto”

Então ela merece um PRD próprio.

Exemplo:

* Plataforma multi-tenant com SSO, OAuth, 2FA, políticas corporativas.
* Sistema de autenticação que impacta segurança, onboarding e compliance.
* Algo que pode ser usado por múltiplos sistemas e clientes.

Nesse cenário, o login deixa de ser um simples requisito técnico e se torna uma **feature estratégica com valor de negócio**.

---

#### Ideia central

Nem toda feature merece um PRD.

Mas quando uma feature deixa de ser apenas um requisito funcional e passa a ter impacto estratégico, métricas próprias e decisões relevantes de produto, ela deve ser tratada como um “produto dentro do produto”.

Em resumo:
**PRDs de feature existem quando a funcionalidade tem peso estratégico — não apenas técnico.**

### Principais seções em um PRD de Feature
O PRD de feature é mais enxuto que o PRD de alto nível, mas ainda mantém uma estrutura organizada. Ele é flexível — nem sempre precisa conter todas as seções — porém, em projetos mais relevantes, normalmente inclui os seguintes blocos:

* **Resumo da feature** → explica o que será desenvolvido, o problema que resolve e o contexto.
* **Objetivo principal** → metas claras em bullet points, sempre acompanhadas de métricas.
* **Escopo** → define o que entra e o que fica de fora.
* **Requisitos funcionais** → funcionalidades e comportamentos esperados.
* **Requisitos não funcionais** → critérios quantitativos como performance, latência, disponibilidade, segurança etc.
* **Fluxo do usuário** → como a feature será utilizada na prática.
* **Dependências** → sistemas, módulos ou recursos necessários para funcionar.
* **Critérios de aceitação** → checklist que define quando a entrega está concluída.
* **Riscos** → possíveis problemas ou desafios.
* **Considerações gerais** → observações importantes adicionais.

Esse tipo de PRD já se aproxima mais do dia a dia técnico, pois conversa diretamente com desenvolvimento.

Embora não seja um design doc técnico formal, o PRD de feature é essencial para contextualizar — tanto para o time quanto para a IA. Ele garante clareza sobre propósito, limites, metas e critérios de sucesso antes da implementação começar.

Em resumo:
**O PRD de feature organiza contexto, objetivos e critérios práticos para transformar uma ideia relevante em entrega estruturada.**

### Exemplo 1 de PRD
Exemplo de PRD para Feature (Catálogo de eCommerce): 

O professor apresenta um **exemplo prático de PRD de feature** para tangibilizar a teoria. O caso é um **catálogo de produtos para um e-commerce próprio**, mostrando como estruturar um PRD de forma clara e objetiva, sem ser excessivamente longo.

O documento inclui:

* **Resumo da feature** → explica que o catálogo será a fonte única de verdade dos produtos (descrição, preço, estoque, variações), com APIs para vitrine e checkout e painel interno para o time comercial.

* **Contexto do problema** → hoje não existe base centralizada; planilhas causam divergência; produtos esgotados continuam visíveis; falta controle consistente.

* **Cenários de uso** → cliente navega na vitrine; checkout consulta dados atualizados; time comercial altera preço/estoque com reflexo imediato.

* **Objetivos e métricas** → tornar o catálogo a fonte oficial (meta: 100% da loja usar o catálogo), reduzir itens indisponíveis visíveis, acelerar atualização de produtos.

* **Escopo e fora do escopo** → define claramente o que será construído (estrutura de produto, APIs, painel administrativo etc.) e o que não faz parte (checkout, frete, regras fiscais, CMS avançado).

* **Requisitos funcionais (RFs)** → funcionalidades numeradas para facilitar rastreabilidade e uso com IA.

* **Requisitos não funcionais** → performance (ex: P95 < 150ms), disponibilidade 99,9%, segurança, observabilidade etc.

* **Arquitetura e componentes** → microserviço dedicado, API em Go, PostgreSQL, painel em Next.js, integrações.

* **Trade-offs, dependências e riscos** → decisões técnicas, possíveis falhas e estratégias de mitigação.

* **Critérios de aceitação** → checklist final para garantir que tudo foi implementado e validado.

A mensagem central é: **sim, dá trabalho**, mas esse documento vira um ativo estratégico. Ele organiza pensamento, alinha time e melhora drasticamente o contexto para a IA trabalhar com mais precisão.

Em resumo:
Esse exemplo mostra como um PRD de feature bem estruturado conecta problema, escopo, métricas e arquitetura — transformando uma ideia em uma entrega técnica clara e mensurável.

### Exemplo 2  de PRD e JSON Opcional
Exemplo para Feature (Rate Limiter): 

Aqui vai o resumo:

O exemplo apresenta um **PRD de feature para um Rate Limiter centralizado**, que será utilizado por todos os microserviços da plataforma para controlar requisições por chave de API e IP, evitando sobrecarga.

### Objetivo

Garantir disponibilidade do sistema, reduzir indisponibilidade (meta: menos de 1 minuto), priorizar clientes premium e limitar abuso (monitorando erros 429), mantendo latência P95 abaixo de 150 ms(95% das requisições devem responder em até 150 milissegundos).

### Contexto

Voltado para times de desenvolvimento e DevOps, atendendo microserviços internos e APIs públicas.

### Escopo

**Incluso:**

* Limite por API Key e IP
* Controle de burst e janela deslizante
* Retorno de erro 429 com headers padrão

**Fora do escopo:**

* Console administrativo
* Multi-região
* Fila de prioridade

### Requisitos

* **Funcionais:** definição clara do fluxo (requisição → verificação → bloqueio ou liberação), controle de burst, headers padrão.
* **Não funcionais:** performance, disponibilidade, segurança, observabilidade, compliance.

### Arquitetura

* Microserviço dedicado
* Backend em Go
* Redis como storage de contadores
* Observabilidade com Prometheus e OpenTelemetry
* Integração via REST

### Trade-offs e Dependências

* Uso de Redis como principal armazenamento
* Dependência de DevOps e dos times consumidores

### Riscos

* Redis indisponível
* Configurações incorretas bloqueando clientes legítimos

### Critérios de Aceitação

Checklist validado com testes e exemplos (inclusive em JSON).

---

### Ponto central

O grande diferencial aqui é o uso de **prompt para gerar o PRD tanto em Markdown (leitura humana) quanto em JSON (leitura estruturada para IA e agentes)**.

Isso permite:

* Melhor comunicação entre agentes de IA
* Menos ambiguidade
* Automação de validações e integrações

Em resumo:
Esse exemplo mostra como um PRD técnico bem estruturado organiza contexto, arquitetura, métricas e riscos — e como gerar versões em Markdown e JSON potencializa o uso com IA e automações.

### Prompt para geração de PRD
Prompt de Entrevista para Gerar PRD para desenvolvimento de Feature: 

Aqui vai o resumo:

O autor apresenta um **prompt estruturado para gerar PRDs por meio de entrevista guiada pela IA**. A proposta é simples: você cola o prompt em uma IA, pede para iniciar a entrevista e ela conduz todo o processo passo a passo até gerar um PRD completo.

### Objetivo do prompt

Gerar um PRD de feature que explique:

* **Por que** a feature existe
* **O que** ela deve fazer
* **Como saberemos que está pronta**
* **Onde** será implementada

Ao final, o documento é entregue em **Markdown (português)** e a IA pergunta se o usuário deseja também a versão em **JSON estruturado** (com chaves em inglês).

---

### Como funciona

O prompt segue um modelo de **entrevista step-by-step**, cobrindo:

1. Contexto e visão
2. Problema
3. Oportunidade
4. Objetivos
5. Métricas
6. Escopo
7. Requisitos funcionais e não funcionais
8. Arquitetura
9. Trade-offs
10. Dependências
11. Riscos e mitigações

Em cada etapa, a IA:

* Faz perguntas específicas
* Resume o que entendeu
* Pede confirmação antes de avançar

Ela também armazena internamente as respostas em JSON (sem mostrar ao usuário) e valida consistência antes de gerar o resultado final.

---

### Regras importantes do prompt

* Não fazer perguntas duplas
* Não inventar detalhes técnicos
* Sugerir respostas para facilitar
* Usar linguagem clara e direta
* Aplicar valores padrão inteligentes quando necessário (ex: P95 < 150ms)

---

### Diferencial

O grande valor está em:

* Produzir PRD em **formato humano (Markdown)**
* Produzir PRD em **formato estruturado (JSON)**
* Permitir uso com agentes de IA
* Reduzir ambiguidades
* Evitar geração de código fora do escopo

---

### Mensagem central

Mesmo não sendo um design doc, o PRD é fundamental para dar contexto à IA. Quanto melhor o PRD, menos código desalinhado ou fora do escopo será gerado.

Em resumo:
O prompt transforma a criação de PRDs em um processo guiado, estruturado e automatizável — tornando algo complexo mais leve, consistente e muito mais útil para humanos e para IA.
