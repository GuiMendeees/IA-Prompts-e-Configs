O objetivo agora é **executar as subtarefas** detalhadas no arquivo `@current-work.md`, uma de cada vez, até finalizar a tarefa por completo, seguindo meticulosamente as diretrizes do **fluxo de trabalho RIPER para cada subtarefa**.

- **Não invente ou adicione mudanças alem do planejado na subtarefa, exceto se o usuário solicitar ou se for estritamente necessário para implementar a tarefa, no caso de necessidade pontue os aspectos fundamentais que justifiquem as mudanças e o impacto de nâo fazer**


- **Não remova nenhuma das seções, subseções, estrutura e organização do `current-work.md` ao atualiza-lo**

- Mantenha toda a estrutura do documento.

**IMPORTANTE:**

- Excute as subtarefas de forma **contínua e fluída**  seguindo as etapas do fluxo de trabalho RIPER

- **NÃO precisa parar** após cada subtarefa para aguardar instruções.
- **Continue trabalhando até:**

    - :question: Ter dúvidas específicas que precisem de esclarecimento
    - :construction: Encontrar bloqueios que impeçam o progresso.
    - :recycle: Precisar de validações sobre decisões arquiteturais importantes

    Em qualquer desses casos, você deve perguntar ao usuário para obter os insumos necessários para continuar, elabore a pergunta com foco em objetivo da tarefa e detalhando pontos de atenção, conceitos como se o usuário fosse um Product Manager com conhecimento tecnico limitado

- :mag: **Research (Pesquisa)**

    - Revise o arquivo `current-work.md` para entender o progresso atual e o contexto de curto prazo.
    - Verifique a seção de dúvidas e decisões e a partir das respostas do usuário, revise e atulize o planejamento do arquivo `current-work.md`
    - Identifique e leia as regras relevantes (`fetch_rules`) para a subtarefa visando aderência aos guidelines do projeto.
    - Consulte arquivos do Memory Bank na pasta `@ai/memorybank/` para contexto técnico e de negócio sobre o projeto
    - Entenda o código existente para a subtarefa.
    - Identifique dependências e integrações necessárias.

- :bulb: **Inovação:**
    
    - Realize brainstorming para encontrar abordagens e soluções.
    - Analise prós e contras de cada abordagem, com tendência na escolha de opções de menor complexidade caso seja viável
    - Explore trade-offs e alternativas consideradas.

- :brain: **Planejamento:**

    - Confirme a abordagem exata para a implementar a subtarefa.
    - Identifique quais arquivos serão modificados/criados
    - Planeje a estrutura do código a ser alterado/adicionado.
    - Mantenha alinhamento com as regras consideradas relevantes (`fetch_rules`)
    - Considere impacto em outras partes do sistema.

- :gear: **Execução:**

    - Implemente as mudanças seguindo as regras consideradas relevantes (`fetch_rules`).
    - Aplique os padrões arquiteturais definidos no projeto.
    - Adicione logs de observabilidade e comentários para explicar decisões de design complexas ou não obvias (o ´porquê´), nunca paa descrever (´o quê´) do código.

- :check: **Revisão:**

    - Verifique se o código atende aos requisitos da subtarefa.
    - Confirme a consistência com o resto do projeto.
    - Valide contra as regras consideradas relevantes (`fetch_rules`).
    - Teste a funcionalidade implementada.
    
- **Atualiza o arquivo `current-work.md:`**

    - Marque a subtarefa como concluida ´[X]´
    - Adicione notas relevantes na seção "Contexto de Curto Prazo". É muito importante que você coloque lá descorbertas que serão úteis para futuras subtarefas, pois caso você não registre isso, poderá esquecer e perder informações importantes.
    - Atualize os próximos passos, se for necessário.
    - Adicione/modifique outras subtarefas baseado no que foi aprendido.
    - **Continue** imediatamente para a próxima subtarefa a partir da `etapa-01-research`.
    - Antes de declarar tudo como finalizado, sempre rode comandos necessários de build, testes, lints e outras verificações necessárias para garantir que tudo está funcionando corretamente. Caso não esteja, crie subtarefas adicionais para corrigir os problemas encontrados.
    - **Após finalizar todas as subtarefas** em `current-work.md`, sinalize a conclusão completa da tarefa e caso haja algum contexto relavante, tanto técnico quanto do ponto de vista de negócio atualize o arquivos de Memory Bank em`@ai/memorybank/`