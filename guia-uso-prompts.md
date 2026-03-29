# Guia de Uso dos Prompts de IA para Desenvolvimento

Este guia descreve o processo passo a passo para utilizar os prompts de IA e o Cursor para auxiliar no desenvolvimento de software, desde a análise inicial do projeto até a execução de tarefas específicas.

## Passo a Passo
### 1- Geração do Memory Bank

O Memory Bank serve como um contexto de longo prazo para a IA, contendo informações essenciais sobrea a estrutura, tecnologias e decisões arquiteturais do projeto.

1.  Abra um novo chat no Cursor.
2.  Execute o comando /aic/generate-memory-bank
3.  A IA analisará o projeto e gerará ou atualizará os arquivos do Memory Bank na pasta ai/memorybank/ com base nos templates. Revise o conteudo gerado para garantir que as informações essenciais foram capturadas.
4.  Você mesmo pode complementar com informações relevantes o qual a AI não consiga inferir. Pode adicionar nos arquivos gerados ou criar novos arquivos.

    Por exemplo:
    
    *   Regras de Negócio críticas que não sejam óbvias no código, por exemplo, depende de alguma etapa que esteja em outro serviço
    
    *   Um design system em formato textual (Mermaid, PlantUML) ajudará a AI a entender onde o projeto se encaixa numa solução maior.
    
    *   Volumetria de acessos, throughput, tamanho da base de dados: ajudará a AI a entender quais tipos de soluções ou cuidados devem ser usados, onde pode ser aplicado algum cache, onde deve evitar um processo mais pesado etc.

    *   Decision Log: Sumarizar decisões importantes e suas justificativas. Isso evita que a IA sugira abordagens que já foram consideradas e descartadas por motivos específicos.

    * Tecnologias/Abordagens Avaliadas e Descartadas: Um breve resumo das principais alternativas que foram consideradas durante o design e porque não foram escolhidas.
    
    * Areas conhecidas como débito técnico e planoes de refataração: Marcar seções do código ou arquitetura que são conhecidas por serem problemáticas ou que estão planejadas para refatoração. Isso pode ajudar a IA a não sugerir modificações que entrem em conflito com esses planos ou a focar em ajudar nessas áreas

    * Gargaos de Perfomance COnhecidos ou Limitações Atuais: Se existem partes do sistema/pipeline que já operam no limite ou já são conhecidas por serem lentas

    <b>Conteudo do Prompt</b>: #genetate-memory-bank.md# 



### 2-  Geração da Tarefa (Task)

Com o Memory Bank criado, o próximo passo é definir a tarefa específica que você deseja que a IA execute.
1. Abra um novo chat no Cursor. É importante usar um chat separado para não misturar o contexto da geração do Memory Bank com a definição da tarefa.
2. Descreava a tarefa e invoque o comando:

> Descrição da Tarefa: Deixe claro que se trata da descrição da tarefa
    -   [Descreva aqui a tarefa, de forma objetiva e completa]

    -   [Qual o objetivo funcional da tarefa?]

    -   [Quais são os requisitos técnicos e de negócio?]

    -   [Quais arquivos ou módulos estão envolvidos?] Use @nome-do-arquivo para referencial-los no contexto do Cursor.

    -   [Há regras especificas que devem ser seguidas?] Use @nome-da-rule para garantir que o plano gerado esteja em conformida com as regras.

    -   [Qual o resultado esperado da tarefa?]

    # Use separadores explicitos
    /aic/plan-current-work # Invoque o comando


<b>Conteudo do Prompt</b>: #plan-current-work.md# 

### 3-  Execução da Tarefa (Task)

Finalmente, com a tarefa detalhada em `@current-work.md`, você pode instruir a IA a executar as subtarefas uma a uma.
    
1.  Abra outro novo chat no Cursor. Novamente, use um chat dedicado para a execução, mantendo os contextos separados.
2.  **Anexe arquivos ou pastas relevantes para a tarefa**, por exemplo toda a pasta ai/memorybank, o proprio current-work.md, arquivos de codigo fonte importantes (tudo isso via @)
3. Execute o comando /aic/execute-current-work
4. A IA irá ler o current-work.md, identificará a primeira subtarefa pendente [], a executará (pesquisando, planejando, codificando e revisando), e atualizara o current-work.md, marcando a subtarefa como concluida [X]
5. Apos a IA confirmar a execução da subtarefa, você pode revisar as alterações. Para executar a proxima subtarefa, basta instruir a IA a "continuar com a proxima subtarefa" repitindo até ter todas concluidas.
6. Caso prefira continuar a execução das subtarefas em outro chat, você pode executar o comando /aic/continue-current-work para continuar a execução das subtarefas.

> 
    ---
    Observações adicionais:
    Ajustes, observaçoes. novas subtarefas

    /aic/continue-current-work

Conteudo do prompt #execute-current-work.md#
Conteudo do prompt #continue-current-work.md#

Seguindo estes passos, você pode usar os prompots para guiar a IA de forma estruturada através do clico de desenvolvimento, aproveitando o contexto do projeto e a definição clara de tarefas.

## Outros Comandos
Aplicando prompt engeneering para melhorar seu prompt.

O comando aic/improve-prompt aplica uma série de padrões de engenharia de prompt para otimizar ao máximo tudo que for passado como parâmetro para ele no footer do output e ainda dá dicas para melhorar ainda mais a execução do prompt gerado. Por exemplo:
Passando este input
>/aic/improve-prompt The flow controller code cleanup is taking over the @LivenessDetectionFlowControler.swift make a step by step plan using code-reasoning and refactor to a single class responsible for the flowcontrollers dependencies cleanup

O agente então irá retornar um prompt extremamente detalhado e otimizado para ser o mais eficiente possível e o seu rodapé ainda virá dicas de como melhorar ainda mais a perfomance do prompt.
O comando improve-prompt está pre-configurado para gerar prompt para o Claud, caso deseje outro LLM é necessário adicionar ao comando a LLM desejada:

>/aic/improve-prompt PROMPT for Gemini: "< Prommpt a ser otimizado >"

Conteudo do prompt #improve-prompt.md#
