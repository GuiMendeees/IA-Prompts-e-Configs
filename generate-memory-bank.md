Você irá **gerar ou atualizar o Memory Bank** que servirá como contexto de longo prazo para a Inteligência Artificial (IA) de codificação, contendo informações essenciais do projeto atual. 
- Por padrão, a IA não possui memória persistente entre interações, ou seja, ela "esquece" tudo o que foi discutido ou aprendido anteriormente assim que a sessão termina. 
-Isso limita sua capacidade de oferecer respostas consistentes e contextualizadas ao longo do tempo.
- O *Memory Bank* mitiga esse problema ao funcionar como uma memória externa persistente e estruturada: 
    - Um conjunto de arquivos versionados que armazend conhecimento duradouro sobre o projeto. 
    - Contém informações como estrutura do sistema, histórico de decisões, contexto de negócio, entre outros. 
    - Com isso, a IA pode gerar respostas mais precisas, alinhas com o histórico do projeto e com menor risco de inconsistência ou redundância. 
    - Seja conciso mas incua as informações essenciais sobre a estrutura, dependências, decisões arquiteturais e explos de componentes chave. 
- Caso os arquivos do Memory Bank já existam, atualize-os com base nas informações mais recentes obtidas do projeto. 
- Ao atualizar o Memory Bank já existente: 
    - Preserve informações que ainda são relevantes e remova apenas o que estiver obsoleto ou incoerente com o estado atual do projeto. 

    -  Evite criar novas informações que não sejam relevantes. Se o Memory Bank estiver completo, não altere nada.
    -   Leia atentamente os templantes de Memory Bank para entender as informações que serão necessárias obter sobre o projeto.
        -   Execute `git ls-files --cached --others --exclude-standart` para listar arquivos noreposit´rio ignorando tudo que está no `.gitignore`, com intuito de entender a estrutura do projeto.
    -  Caso o comando acima não funcione por não ser um repositorio git execute `find . -type f` para listar todos os arquivos no repositório.
- Analise a base de código atual deste projeto para compreemdê-lo com profundidade. Leia e analise com atenção especial aos seguites arquivos e padrões:
    - Arquivos `package.json` , `pyproject.toml`, `requirements.txt` para identificar as dependências chaves, versões e tecnologias usadas.
    -   Execute os comandos que sejam necessários para um conhecimento mais complexo e fiel da estrutura do projeto. Exemplo `vn hep:effective-pom`.
     - Arquivos Markdown (`*.md*`) na raiz ou em pastas como `/docs` que posasam conter informações arquiteturais.
     - Configurações em `*.properties*`, `*.yml*`, `*.dotfiles*`, etc.
     -  Leia os arquivos de código fonte (exemplo: .java, .js, .ts, .cs, .py, .go e etc) e tente entender o objetivo central desse projeto e as principais logicas relacionadas
     - Use todas as informações obtidas para gerar ou atualizar os arquivos do Memory Bank conforme entregaveis esperados.
- Os seguintes arquivos devem ser criados ou atualizados com base nos templates correspondentes:
    -   `@ai/memorybank/techinical-context.md` baseado no template `ai/templates/memorybank/technical-context-template.md`
    -   `@ai/memorybank/software-architeture-and-patterns.md` baseado no template `ai/templates/memorybank/software-architeture-and-patterns-template.md`
    -   `@ai/memorybank/business-context.md` baseado no template `ai/templates/memorybank/business-context-template.md`

    - Você **NÃO** deve catalogar nenhuma decisão no momento. Apenas gere o arquivo para que seja possível catalogar as decisões futuramente.
    - Os arquivos acima são templates.

Os textos presentes nesses templates são apenas orientações e explos. Você deve obrigatoriamente substituir esses textos pelas informações relevantes do projeto.