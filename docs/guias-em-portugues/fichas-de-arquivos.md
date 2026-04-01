# Fichas de Arquivos

## Prompts publicos

- `agent-prompt-security-monitor-for-autonomous-agent-actions-first-part.md`
  Primeira metade do monitor de seguranca. Serve para classificar risco em acao autonoma antes que ela vire execucao perigosa.

- `agent-prompt-security-monitor-for-autonomous-agent-actions-second-part.md`
  Complementa a triagem do monitor. Ajuda a decidir quando uma acao parece exfiltracao, auto-modificacao ou abuso de comando.

- `agent-prompt-security-review-slash-command.md`
  Prompt de revisao de seguranca para diff, branch ou PR. Valor principal: foco em vulnerabilidade exploravel, nao em checklist generico.

- `agent-prompt-bash-command-prefix-detection.md`
  Detecta prefixos e formas de montagem de comando que costumam esconder evasao ou injecao.

- `system-prompt-tool-execution-denied.md`
  Regra de parada. Se a ferramenta negou, o agente nao deve procurar um desvio improvisado.

- `data-agent-sdk-reference-typescript.md`
- `data-agent-sdk-reference-python.md`
  Referencias operacionais dos modos de permissao e de bypass.

## Arquivos do src.zip

- `security-review.ts`
  Versao em codigo do revisor de seguranca, orientada a classes de falha como injecao, traversal, auth bypass e exposicao de segredo.

- `BashTool-prompt.ts`
  Prompt operacional do shell. Importa porque guarda o limite de dano e a obediencia ao sandbox.

- `PowerShellTool-prompt.ts`
  Contraparte de PowerShell, com preocupacoes especificas de quoting, heredoc, flags perigosas e efeito colateral.

- `BypassPermissionsModeDialog.tsx`
  Explicita para o operador que o modo sem aprovacao so faz sentido em ambiente isolado.

- `PluginTrustWarning.tsx`
  Mostra que plugin e MCP ampliam o risco mesmo quando o nucleo parece seguro.

- `RemoteTriggerTool-prompt.ts`
  Reduz vazamento de token e explicita o cuidado com automacao remota.

- `yoloClassifier.ts`
  Centro da decisao automatica de permissao. O mais valioso para estudo defensivo e tambem o mais perigoso se falhar.

## Arquivos adicionados na revisao

- `ampliados/WebFetchTool-prompt.ts`
  Relevante para prompt injection via pagina, redirecionamento e citaçao controlada.

- `ampliados/WebSearchTool-prompt.ts`
  Relevante para uso de fonte, rastreabilidade e atualidade do dado pesquisado.

- `ampliados/AgentTool-prompt.ts`
  Importante para seguranca de orquestracao. Ensina quando abrir subagente, quando nao inventar resultado e como delimitar contexto.

- `ampliados/ssrfGuard.ts`
  Nao e prompt, mas e defesa tecnica central contra SSRF em hooks HTTP.

- `ampliados/BashTool-bashSecurity.ts`
  Camada de deteccao de operadores, substituicoes, expansoes e tecnicas de evasao em shell.

- `ampliados/BashTool-readOnlyValidation.ts`
  Define o que pode ser considerado somente leitura no Bash sem abrir brecha de exfiltracao ou escrita.

- `ampliados/PowerShellTool-powershellSecurity.ts`
  Bloqueia padroes como `Invoke-Expression`, comando dinamico, cradle de download, reexecucao de PowerShell e elevacao.

- `ampliados/PowerShellTool-readOnlyValidation.ts`
  Faz a allowlist de comandos realmente somente leitura e tenta evitar vazamento de segredo por argumento.
