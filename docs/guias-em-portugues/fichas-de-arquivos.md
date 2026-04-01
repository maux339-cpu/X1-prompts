# Fichas De Arquivos

## 01. Core review

- `security-review.ts`
  Revisor principal de vulnerabilidade exploravel. Prioriza alta confianca e reduz ruido.

## 02. Shell guardrails

- `BashTool-prompt.ts`
  Instrui o agente a usar shell com limite de dano, respeitar sandbox e evitar bypass de hooks.

- `BashTool-bashSecurity.ts`
  Faz analise de padroes perigosos em shell. Cobre substituicao de comando, expansoes, zsh evasivo e sinais de abuso.

- `BashTool-bashPermissions.ts`
  Decide como comandos Bash entram no fluxo de permissao e como regras de allow, ask e deny sao aplicadas.

- `BashTool-readOnlyValidation.ts`
  Define o que ainda pode ser tratado como somente leitura em Bash sem abrir brecha de escrita ou exfiltracao.

- `PowerShellTool-prompt.ts`
  Equivalente do Bash com foco em PowerShell e risco operacional em ambiente Windows.

- `PowerShellTool-powershellSecurity.ts`
  Detecta download cradle, execucao dinamica, COM, elevacao e padroes de injecao comuns em PowerShell.

- `PowerShellTool-powershellPermissions.ts`
  Aplica o fluxo de permissao a comandos PowerShell e reforca restricoes de escrita, git interno e persistencia.

- `PowerShellTool-readOnlyValidation.ts`
  Faz a mesma classificacao para PowerShell, com foco em cmdlets que parecem inofensivos mas ainda podem alterar estado.

## 03. Permissoes

- `permissions-core.ts`
  Centro do mecanismo de permissao. Costura ferramentas, contexto, classificadores e decisoes finais.

- `permissionExplainer.ts`
  Gera explicacao de risco para decisoes de permissao. E util para auditoria humana.

- `permissionsLoader.ts`
  Carrega regras e configuracoes de permissao a partir de settings.

- `permissionValidation.ts`
  Valida sintaxe e formato de regras de permissao. Evita regra quebrada ou ambigua.

- `permissions-command.tsx`
  Interface de comando para gerenciar permissao. Ajuda a entender a camada operacional.

- `bypassPermissionsKillswitch.ts`
  Kill switch para modo de bypass. Importante para entender controles de emergencia.

- `bashClassifier.ts`
  No pacote analisado veio como stub para build externa. Isso indica que parte do classificador real foi removida ou fica fora desta amostra.

- `classifierDecision.ts`
  Peca de decisao que ajuda a consolidar resultado de classificadores.

- `classifierShared.ts`
  Tipos e utilitarios comuns da logica de classificacao.

- `shellRuleMatching.ts`
  Normaliza e aplica matching de regras sobre comandos de shell.

- `filesystem.ts`
  Regras de acesso e restricao a caminhos, importante para exfiltracao e alteracao indevida.

- `dangerousPatterns.ts`
  Colecao de padroes perigosos usados para triagem de risco.

- `ssrfGuard.ts`
  Protecao contra SSRF em hooks HTTP. Bloqueia acesso a faixas internas e endpoints de metadata.

## 04. Trust e remoto

- `BypassPermissionsModeDialog.tsx`
  Aviso explicito de alto risco quando o operador ativa execucao sem aprovacao.

- `PluginTrustWarning.tsx`
  Alerta sobre plugins, MCP e codigo de terceiros.

- `TrustDialog.tsx`
  Dialogo de confianca do projeto. Explicita risco de hooks, MCP, execucao Bash e variaveis perigosas.

- `remoteManagedSettings-securityCheck.tsx`
  Verifica se configuracoes remotas trouxeram mudancas perigosas e exige aprovacao.

- `RemoteTriggerTool-prompt.ts`
  Prompt para gatilhos remotos sem expor token diretamente no shell.

- `remotePermissionBridge.ts`
  Ponte de permissao para modo remoto. Importante para entender como aprovacoes atravessam processos.

- `bridgePermissionCallbacks.ts`
  Define contrato de request e response para permissao em bridge.

- `yoloClassifier.ts`
  Montador mais sensivel da cadeia de auto mode e permissao. Referencia templates ausentes.

## 05. Superficie de prompt

- `systemPrompt.ts`
  Monta o prompt de sistema por secoes e contexto.

- `systemPromptSections.ts`
  Define a organizacao das secoes que entram no prompt de sistema.

- `prompts.ts`
  Utilitarios e constantes usadas em construcao de prompt.

- `AgentTool-prompt.ts`
  Importante para superficie de subagentes e delegacao.

- `WebFetchTool-prompt.ts`
  Relevante para risco de prompt injection e ingestao de conteudo remoto.

- `WebSearchTool-prompt.ts`
  Relevante para a mesma superficie de busca e injecao via resultados.

- `execPromptHook.ts`
  Executa hooks baseados em prompt. Alto interesse para entender injecao, recursao e acoplamento de ferramenta com LLM.

- `promptShellExecution.ts`
  Faz a ponte entre texto e execucao de shell, por isso e um ponto sensivel para prompt injection com impacto real.
