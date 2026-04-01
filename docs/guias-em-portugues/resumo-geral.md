# Resumo Geral

## Prompts publicos

- `Security Monitor`
  Funciona como uma camada de classificacao de risco para acoes autonomas. Tenta barrar exfiltracao, auto-modificacao suspeita, execucao de codigo externo e operacoes fora do escopo normal.

- `Security Review`
  Age como revisor de branch ou diff com foco em vulnerabilidades realmente exploraveis. O objetivo nao e listar tudo, e sim apontar risco alto com boa confianca.

- `Bash Command Prefix Detection`
  Detecta sinais iniciais de comandos que tentam escapar do fluxo normal, contornar hooks ou preparar execucao perigosa.

- `Tool Execution Denied`
  Impoe a regra de nao contornar uma negacao explicita de execucao. Em termos de seguranca, isso reduz tentativa de bypass por engenharia de prompt.

- `SDK Permission References`
  Mostram como o sistema modela modos de permissao, inclusive configuracoes perigosas de bypass.

## Arquivos do src.zip

- `security-review.ts`
  Prompt defensivo mais direto do pacote. Mira injecao, traversal, auth bypass, escalacao, secrets e classes conhecidas de falha.

- `BashTool-prompt.ts`
  Prompt de shell com guardrails práticos. Reforca limites de destrutividade, uso adequado de ferramentas e obediencia ao sandbox.

- `PowerShellTool-prompt.ts`
  Mesmo papel do Bash, mas com regras adaptadas para PowerShell e seus riscos especificos.

- `BypassPermissionsModeDialog.tsx`
  Material de UX de seguranca. Nao e prompt de modelo, mas deixa explicito o risco operacional de modo sem aprovacao.

- `PluginTrustWarning.tsx`
  Material de trust. Deixa claro que plugin e MCP ampliam muito a superficie de ataque se a origem nao for confiavel.

- `RemoteTriggerTool-prompt.ts`
  Prompt util para reduzir exposicao de credencial, evitando uso descuidado de token no shell.

- `yoloClassifier.ts`
  Peca mais sensivel da extracao. Centraliza a montagem de decisao automatica de permissao, mas os templates-base nao vieram no ZIP.

- `BashTool-bashSecurity.ts` e `PowerShellTool-powershellSecurity.ts`
  Mostram com mais precisao tecnica como o sistema tenta identificar abuso em shell, inclusive tecnicas proximas de malware operacional.

- `BashTool-readOnlyValidation.ts` e `PowerShellTool-readOnlyValidation.ts`
  Deixam claro que parte da defesa esta na definicao rigorosa de quais comandos continuam sendo tratados como somente leitura.

- `WebFetchTool-prompt.ts`, `WebSearchTool-prompt.ts` e `AgentTool-prompt.ts`
  Ampliam a superficie de risco por entrada externa, pesquisa web, citacao, orquestracao e contaminacao de contexto entre agentes.

- `permissions-core.ts`, `permissionExplainer.ts` e `permissionValidation.ts`
  Tornam visivel a espinha dorsal da camada de permissao, explicacao de risco e validacao de regras.

- `ssrfGuard.ts`
  Fecha um vetor especifico e importante: conexao HTTP a enderecos privados, link-local e metadata endpoints.

- `execPromptHook.ts` e `promptShellExecution.ts`
  Sao dois pontos de alto interesse para injecao: um executa hooks por prompt e o outro transforma texto aprovado em execucao de shell.

## Leitura de risco

- Defensivo forte: `Security Monitor`, `Security Review`, prompts de shell e validacoes de permissao.
- Ofensivo-correlato: tudo que toca shell, bypass, plugin, bridge remota e auto mode.
- Lacuna principal: templates `.txt` referenciados por `yoloClassifier.ts` ausentes na amostra.
- Lacuna secundaria: `prompt injection` e `trust dialog bypass` nao apareceram como prompts publicos isolados; eles estao espalhados entre shell, web, trust, UX e permissoes.
