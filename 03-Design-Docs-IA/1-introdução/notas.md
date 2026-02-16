# Introdução – Resumo completo e estruturado

## 1. Alinhando expectativas

A disciplina é apresentada como um estudo sobre design docs e documentação técnica, com foco em como esses documentos contribuem para:

* o projeto em si;
* a comunicação entre time e empresa;
* a construção de documentação como ativo de valor quando usada com inteligência artificial.

O autor destaca que, historicamente, a documentação ganhou uma conotação negativa por ser percebida como:

* burocrática;
* rapidamente desatualizada;
* pouco lida por desenvolvedores e profissionais.

Em seguida, aponta uma mudança de cenário: na era da IA, a documentação volta a ser essencial porque passa a funcionar como recurso interpretável por agentes de IA, ajudando a entender:

* contexto do projeto;
* objetivos;
* decisões tomadas;
* padrões adotados;

inclusive tanto no início do projeto quanto após longos períodos de operação (dia 1 e dia 365).

O autor afirma que um problema comum é a falta de clareza sobre:

* a variedade de documentos técnicos existentes;
* quando utilizar cada tipo.

Por isso, o objetivo da disciplina é fornecer uma fundamentação clara sobre:

* tipos de documentação comuns;
* o papel dos design docs;
* momentos adequados para utilizá-los.

Ele reconhece que escrever documentação costuma ser visto como pouco agradável, mas promete aulas práticas, com aplicação desde o primeiro dia do projeto. O argumento é que o uso correto de design docs muda:

* o fluxo de desenvolvimento;
* a comunicação dentro da empresa;
* a manutenção contínua da documentação com auxílio de IA, mantendo-a atualizada e útil.

A disciplina é posicionada como indispensável, não pelo tamanho, mas pelo impacto na prática de desenvolvimento de software moderno.



---

## 2. Contextualizando o mundo da documentação

O autor afirma que, embora a disciplina foque em design docs, é necessário contextualizar documentação de forma geral para entender como se chegou ao cenário atual.

Ele também diz que pretende esclarecer diferenças entre:

* “documentações comuns” usadas em empresas;
* documentos frequentemente confundidos com design docs.

A meta é garantir que o aluno saiba escolher o tipo certo de documentação para o momento certo.

Em seguida, ele estabelece que o processo de documentar acompanha a engenharia de software. A engenharia de software é tratada como disciplina com ciclo completo: criação, projeto, entrega, resiliência e operação. Nesse ciclo, documentação historicamente acompanha o desenvolvimento.



---

## 3. Waterfall (anos 70–80)

O autor relembra que, nos anos 70 e 80, era comum trabalhar com processos sequenciais, como o modelo cascata (waterfall), e também com metodologias como RUP (citada, mas aprofundada depois).

No modelo waterfall, documentação era um ponto central para iniciar projetos. Enquanto documentação, fluxos e registros não estivessem corretos, o software não avançava para implementação.

Isso gerou o uso de “artefatos” (múltiplos documentos), como:

* requisitos;
* especificações de sistemas;
* modelos e diagramas (UML é citada como útil).

No waterfall, documentação é descrita como “contrato”, e as decisões de software ficavam registradas antes da implementação.

O autor descreve o significado do modelo cascata:

* ordem linear rígida;
* cada fase precisa ser concluída completamente antes da próxima começar.

Ele lista o fluxo típico:

1. levantamento de requisitos (muito detalhado no início);
2. análise e projeto (design do projeto, arquitetura, interfaces, componentes);
3. implementação;
4. testes (muitos manuais na época, com playbooks);
5. deploy (entrega do produto ao cliente);
6. manutenção (correções e melhorias após entrega).

O autor reforça que software é tratado como produto: algo vendido/desenvolvido para gerar valor e ser consumido.

Problemas apontados:

* o cliente vê o resultado apenas no final;
* se requisitos estiverem errados, o retrabalho é alto;
* projetos grandes podem levar meses ou anos;
* empresas mudam nesse período (mercado, processos, produto), e o software pode não acompanhar essas mudanças;
* isso gera retrabalho, conflitos, estresse e custos elevados.



---

## 4. RUP (Rational Unified Process)

O RUP é apresentado como método criado pela Rational, posteriormente comprado pela IBM, com objetivo de oferecer um processo mais iterativo e flexível do que o waterfall, embora ainda com forte controle de documentação.

O RUP organiza disciplinas (levantamento de requisitos, análise, design, implementação, teste, gerenciamento de configuração) em fases que se repetem de forma iterativa, permitindo ciclos menores e feedback mais rápido.

Fluxo do RUP:

* Inception (concepção): define escopo, objetivos e viabilidade;
* Elaboration (elaboração): detalha arquitetura, identifica riscos e refina requisitos principais;
* Construction (construção): desenvolvimento incremental com base na arquitetura aprovada;
* Transition (transição): entrega, treinamento e correções.

O autor comenta a transição histórica para Scrum e métodos ágeis, e cita também aprendizado de práticas como TDD, BDD e pair programming (como contexto histórico da época).

Principais diferenciais mencionados:

* processo iterativo;
* forte utilização de casos de uso (modelagem a partir da interação do usuário com o sistema);
* arquitetura centralizada;
* definição clara de papéis (analistas, devs, testadores etc.);
* o analista como elo com o cliente, criando fluxos/diagramas e preparando material para implementação.

Vantagens do RUP frente ao waterfall:

* revisões e ajustes por iteração;
* redução de riscos por validação progressiva;
* melhora da comunicação entre times e stakeholders.

Desvantagens:

* mais complexo de gerenciar;
* muita documentação e planejamento;
* custoso para projetos pequenos (burocracia).



---

## 5. Agile (Manifesto Ágil, 2001)

O autor apresenta o Manifesto Ágil como reação ao modelo anterior. A frase destacada é:

“Software em funcionamento é mais importante que documentação abrangente.”

Ele explica que o ágil não elimina documentação, mas muda seu propósito:

* a documentação deixa de ser um fim em si mesma;
* antes, a documentação era tratada com peso semelhante ao software, e em alguns casos parecia ser “o produto”;
* com o ágil, o foco passa para software funcionando, e documentação deve apoiar o desenvolvimento, não substituí-lo.

Ele menciona que surgiram extremos:

* quem vinha de documentação muito grande e não aceitava outra forma de desenvolver;
* quem defendia que não precisava de documentação e que documentar seria perda de tempo.

O autor recomenda equilíbrio e afirma que a forma de desenvolver software mudou muito com as metodologias ágeis e está mudando novamente com IA.



---

## 6. Problemas conhecidos com documentação

O autor volta a discutir documentação como prática ainda presente em empresas “sérias”, mas ressalta problemas recorrentes:

1. Documentação inexistente ou fortemente desatualizada

   * documentação errada pode ser pior que nenhuma;
   * dados incorretos (números, guidelines) levam a decisões incorretas.

2. Priorização de desenvolver software em vez de documentar

   * pressão por entrega (deploy, sprint) faz documentação ser adiada;
   * fatores culturais e pressões organizacionais influenciam;
   * em setores com compliance, documentação mínima é exigida.

3. Criação de documentação é lenta e desagradável

   * pode levar dias para produzir algo “decente”;
   * depois exige manutenção contínua, e rapidamente pode desatualizar.

4. Documentação raramente é lida pelo time todo

   * em projetos corridos, pessoas priorizam correções e entregas e não leem documentação.

5. Falta de conhecimento sobre como criar o documento certo para cada caso

   * existem muitos tipos de documentos, cada um com função e objetivo;
   * tentar criar um template único para tudo deixa o processo confuso;
   * aprender documentação não costuma ser prioridade em treinamentos.

Conclusão desse trecho: o mercado conhece pouco sobre tipos de documentos, o que documentar, o que não documentar, e o que é realmente importante.



