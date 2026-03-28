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