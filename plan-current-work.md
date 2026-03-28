o objetivo principal agora é **GERAR um PLANO de implementação DETALHADO para a tarefa**, dividindo-a em subtarefas lógicas e sequencias necessárias priorizadas para a implementação completa. 

O plano de implementação deverá ser organizado no arquivo `current-work.md`, utilizado o template `@ai/templates/task-template.md` e seguindo meticulosamente as diretrizes do fluxo de trabalho RIPER.

Atue como um planejador e **não gere código neste estágio**.

O planejamento deve ser operacional eliminando ambiguidades e decisões deixadas para a execução; todas as decisões necessárias devem estar tomadas e registradas no plano.

-   Um único arquivo `current-work.md` contendo:
    -   O planejamento detalhado, com todas as subtarefas becessárias para a implementação e execução completa da tarefa.

    -   Os critérios de aceitação, **cobrindo integralmente todo os requisitos da tarefa**

    -   **Plano orientado à execução**, com micro subtarefas. Toda analise necessária deve ser feita agora no momento do planejamento, nos minimos detalhes.

-   Para cada subtarefa, incluir obrigatoriamente:

    -   **Passo a Passo** numerado, priorizado e objetivo.
    -   **Arquivos Envolvidos** com caminhos preferencialmente absolutos do workspace (exemplo: `/User/...`) ou `@caminho/arquivo.extensão`.
    -   **ADERÊNCIA** total as regras relevantes ao contexto da tarefa (`fetch_rules`), garantindo conformidade com as guidelines do projeto.
    -   **RIGOROSAMENTE** todas as seções, subseções, estrutura e organização do template `@ai/templates/task-template.md`, da primeira a última linha.
    -   Mensagem final com uma lista de dúidas, ambiguidades e suposições que precisam de esclarecimento ou confirmação antes da execução/implementação do plano. Para cada dúvida, faça uma pesquisa profunda e detalhada e gere opções de prós e contras para facilitar a tomada de decisão por arte do usuário.
    -   **NÃO gere código** Este prompt é exclusivamente para planejamento.
    -   Cetifique-se de que cada subtarefa seja uma **ação contrecta e relativamente pequena**.
    -   **Não remova nenhuma** das seções subseções, estrutura ou organização do `task-template.md` ao gerar o `current-work.md`. Matenha toda as estrutura do documento.
    - Não utilize termos vagos como "investigar", "analisar", "avaliar" sem resultado esperado, artefato e **critérios de conclusão** definidos.
    -   Para comandos sempre prefira flags não interativas, quando houver risco, inclua primeiro um **dry-run** explícito.
    -   **IMPORTANTE:** Realize a análise e o planejamento da tarefa de forma **continua e fluida** seguindo as etapas do fluxo de trabalho RIPER.
    -   **NÃO precisa parar** após cada etapa para aguardar instruções.
    **Continue trabalhando até:**
        -   :question:  Ter dúvidas especificas sobre os reqyusutis da tarefa que precisem de esclarecimento.
        -   :construction: Encontrar ambiguidades ou lacunas nos requisitos que impelam um planejamento completo.
        -   :recycle: Precisar de validação de decisões de arquitetura ou abordagem importantes andes finalizar o plano.
        - Em qualquer um desses casos, **você deve perguntar ao usuário** para obter insumos necessários para continuar.
    - :mag: **Pesquisa:**
        - Compreenda a fundo e refine os requisitos da tarefa.
        - Identifique e lea as regras relevantes (`fetch-rules`) para garantir conformidade com os guidelines do projeto.
        - Consulte os arquivos do Memory Bank na pasta `@ai/memorybank/` para contexto técnico e de negócio sobre o projeto.
        - Identifique ambiguidades nos requisistos ou decisões criticas que precisam de esclarecimento.
        - Leia o código existente relevante para a tarefa.
        - Entenda o código existente, os padrões já usados, possíveis soluções já implementadas, boas práticas adotadas, etc.
        - Identifique dependências e integrações necessárias.
        - Mapeie arquivos, classes, funções e endpoints concretos afetados; liste-os para uso em "Arquivos envolvidos" nas subtarefas.
    -   :bulb: **Inovação:**
        - Realize brainstoming para identificar possíveis soluções e abordagens para a tarefa.
        - Analise de prós e contras de cada abordagem, considerando aspectos como:
            - Impacto de negócio
            - Segurança
            - Escalabilidade
            - Resiliência
            - Perfomance
            - Acoplamento
            - Dependências e etc.
        - Explore trade-offs e alternativas consideradas
    - :brain: **Planejamento:**
        - Confirme a abordagem a ser detalhada no `current-work.md`.
        - Defina como irá preencher cada seção do template.
        - ** Divida a tarefa em subtarefas logicas, pequenas, claras e sequenciais, cada uma representando ação concreta.**
        - Identifique notas relevantes e arquivos chaves que deverão ser incluidos na seção **Contexo de Curto Prazo.**
        - Quebre em **microtarefas**, que possam ser executadas sem análise adicional ("no-brainer").
    - A análise profunda e detalhada deve ser feita neste momento de planejamento.
    - Analises posteriores deverão ser exceções.
    - :gear:**Execução-Geração do Plano-**
        - Gere o conteudo do `current-work.md` com base na análise feita.
        - Esta fase NÃO envolve a execução do planejamento. Apenas a criação `current-work.md` com o plano detalhado.
        - Preencha todas as seções do tamplate no `current-work.md` detalhadamente.
        - Para cada subtarefa planejada:
            - Liste na seção "Plano de Execução" do `current-work.md` usando checkboxes [].
            - Defina os **Arquivos Envolvidos** (preferencialmente caminhos absolutos do workspace ou `@caminho/arquivo.extensao`).
            - Liste as **dependências** (outras subtarefas, componentes externos).
            - Determine o **Status Atual** (e.g., "Pronta para execução. "Rever pesquisa adicional").
            - Detalhe o **Passo a Passo** numerado e objetivo (Passo 1, Passo 2,...).
            - Especifique os **Comandos exatos** com flags não interativos e, quando aplicavel, inclua um **dry-run** antes do comando efetivo.
            - Liste **Validações automatizáveis** (exemplo: testes, linters, build) para confirmar a conclusã, quando aplicável.
            - Mapeie **Riscos** e **Mitigação** (se ouver).
            - Adicione notas relevantes e arquivos chave na seção "Contexto de Curto Prazo" do `current-work.md`.
            - Inclua uma syvtask para atualização dos arquivos no `memorybank` (`@ai/memorybank/`) como uma subtarefa final, caso alguma alteração decorrente desta tarefa seja extremanete relevante para o contexto geral do projeto, pu algo que precisa ser recordado para futuras tarefas.
    - :check: **Revisão:**
        - Verifique se o plano cobre todos os requisitos da tarefa.
        - Confirme que o plano está completo, claro e sem ambiguidades.
        - Validade a conformidade com as regras relevantes ao contexto da tarefa (`fetch_rules`).
        - Validade a conformidade com o template `@ai/templates/task-template.md`.
        - Certifique-se de que impactos e dependências estão mapeados e endereçados no plano.
        - Garanta que **nenhuma subtarefa** requeira análise adicional para ser executda.
        - Valide que todas as subtarefas possuem **critérios de conclusão** claros e, quando aplicável, **validações automatizáveis**
        - Sinalize se o plano está pronto para execução, se precisa de validação adicional ou se há dúvidas (e quais são).
        - Liste as dúvidas, ambiguidades ou suposições que precisam de esclarecimentos ou confirmações antes da execução/implementação do plano.
        - Atualize o `current-work.md`com base nas respostas do usuário.
        - Para cada dúvda, faça uma pesquisa profunda e detalhada e gere opções com prós e contras para facilitar a tomada de decisã por parte do usuário, incluindo **recomendação** e impacto no plano.
        - Verifique se gerou entregáveis conforme esperado e detro das restrições estabelecidades.