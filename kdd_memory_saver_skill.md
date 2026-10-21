# Skill: Knowledge Discovery and Documentation (KDD) Memory Saver

## 🎯 Objetivo e Escopo

Orientar o agente de IA a identificar, filtrar e salvar aprendizados de alto valor em um arquivo persistente localizado em `docs/KDD_PROJECT.MD`.

**⚠️ Importante:** O objetivo desta skill **NÃO** é registrar a conversa, ampliar o histórico da sessão ou substituir a documentação oficial do projeto. O objetivo é puramente capturar o conhecimento destilado que altera ou otimiza o comportamento futuro.

## 🔄 O Ciclo KDD

O funcionamento desta memória baseia-se em um ciclo contínuo de auto-melhoria (self-improvement loop) inspirado no Hermes Agent:

1. **Observar:** Acompanhar as ações, erros e decisões durante a sessão.
2. **Avaliar:** Filtrar o que aconteceu usando os critérios de utilidade.
3. **Destilar:** Extrair apenas a essência do aprendizado (sem ruídos ou logs).
4. **Persistir:** Salvar de forma estruturada no arquivo `docs/KDD_PROJECT.MD` (seguindo o formato rígido).
5. **Reutilizar:** Consultar o arquivo em sessões futuras.
6. **Verificar:** Checar se a memória recuperada ainda é válida para o contexto atual.
7. **Refinar (Deduplicação Obrigatória):** Garantir que **não haja conhecimento duplicado**. 
   - A gravação deve ter uma chave e escopo deduplicado. 
   - Se uma nova memória tiver vocabulário diferente, mas convergir para o mesmo conhecimento de uma memória existente, o agente deve **revisar/atualizar a memória original** em vez de criar uma nova com sentido igual e palavras diferentes.
   - Atualizar, corrigir, ou depreciar memórias obsoletas.

### 🧠 Continuidade de Intenção

A "Continuidade de Intenção" é a camada aplicada durante a fase de reutilização do ciclo. Ao reutilizar uma memória, o agente deve:
* **Recuperar** o que pode importar para o momento.
* **Verificar** o que ainda é válido e aplicável.
* **Aplicar SOMENTE** o que influencia diretamente a tarefa atual, ignorando o restante para manter o foco.

## ⚡ Gatilho de Execução

Sempre que uma sessão de conversa terminar, o agente deve obrigatoriamente fazer a si mesmo a seguinte pergunta e respondê-la de forma direta antes de encerrar:

> **"O que esta sessão ensinou que vale a pena transformar em memória permanente?"**

## ✅ Critérios de Inclusão (O que É Memória Útil)

Apenas informações destas categorias:
1. **Uma decisão que afeta o futuro:** Escolhas arquiteturais, trade-offs aceitos.
2. **Requisitos ou restrições duráveis:** Diretrizes que influenciem tarefas futuras.
3. **Abordagens que falharam:** Falhas com causa reproduzível e orientação concreta.
4. **Uma armadilha reproduzível (Pitfall):** Bugs específicos, edge cases ou "pegadinhas".
5. **Um procedimento que vai se repetir:** Workflows, passos de deploy ou rotinas específicas.
6. **Um padrão importante do projeto:** Padrões de implementação específicos do domínio.
7. **Uma preferência clara e declarada do usuário:** Regras de formatação e estrutura.

## ❌ Critérios de Exclusão (O que NÃO É Memória Útil)

Ignorar:
1. **Regras e patterns explícitos no código** (ex: clean code, linting).
2. **Um comando de teste** ou CLI de uso único.
3. **Erros transitórios** (problemas de paths, digitação, tipagem simples).
4. **Falhas de ambiente** não persistentes.
5. **Conhecimento já adquirido** ou de amplo domínio público.

## 📝 Formato de Gravação Obrigatório

Quando uma memória for persistida em `docs/KDD_PROJECT.MD`, ela **deve** seguir estritamente o formato abaixo. 

**Regras do Formato:**
* Omita `Relações` quando não houver impacto indireto.
* Omita `Substitui` quando não houver uma memória antecessora a ser deprecada/anulada.
* Ao revisar ou complementar uma memória já existente, adicione um campo `Data de Revisão:` logo abaixo da data original no título.

```markdown
## AAAA-MM-DD - Título curto
**Tipo:** [sucesso | falha | requisito | restrição | decisão | armadilha | procedimento | padrão de projeto | relação | preferência de usuário]
**Chave:** [identificador estável de assunto governado - usado para deduplicação]
**Escopo:** [áreas, módulos, artefatos e ambientes válidos]
**Memória:** [afirmação direta e autocontida]
**Resultado:** [Efeito observado que confirma o aprendizado registrado]
**Relações:** [Módulos, áreas ou tarefas que podem ser afetadas] *(Opcional)*
**Aplicação:** [Quando repetir, aplicar ou evitar]
**Evidência:** [Qual arquivo, decisão ou observação que sustenta a memória]
**Substitui:** [Chave e título da memória que ela estende ou anula] *(Opcional)*
**Status:** [ativa | deprecada]
```

## 🛠️ Procedimento Final da Sessão

1. Execute as fases de **Observar, Avaliar e Destilar**.
2. Avalie deduplicação (**Refinar**) comparando as Chaves e Escopos existentes. Atualize se for redundante, anotando a revisão.
3. Se houver nova memória útil, aplique a fase de **Persistir** seguindo o Formato de Gravação Obrigatório.
4. Se NÃO houver aprendizado qualificado, encerre normalmente sem gravar.