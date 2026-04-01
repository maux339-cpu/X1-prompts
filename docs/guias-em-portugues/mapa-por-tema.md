# Mapa Por Tema

## Seguranca defensiva

- `agent-prompt-security-monitor-for-autonomous-agent-actions-first-part.md`
- `agent-prompt-security-monitor-for-autonomous-agent-actions-second-part.md`
- `agent-prompt-security-review-slash-command.md`
- `security-review.ts`

Esses arquivos priorizam bloqueio, deteccao e revisao de risco real.

## Shell, execucao e permissoes

- `agent-prompt-bash-command-prefix-detection.md`
- `BashTool-prompt.ts`
- `BashTool-bashSecurity.ts`
- `BashTool-readOnlyValidation.ts`
- `PowerShellTool-prompt.ts`
- `PowerShellTool-powershellSecurity.ts`
- `PowerShellTool-readOnlyValidation.ts`
- `system-prompt-tool-execution-denied.md`
- `data-agent-sdk-reference-typescript.md`
- `data-agent-sdk-reference-python.md`
- `dangerousPatterns.ts`
- `yoloClassifier.ts`

Aqui fica a camada mais sensivel para abuso operacional ou RCE indireto.

## Trust, bypass e superficie ampliada

- `BypassPermissionsModeDialog.tsx`
- `PluginTrustWarning.tsx`
- `RemoteTriggerTool-prompt.ts`
- `AgentTool-prompt.ts`
- `ssrfGuard.ts`
- `permissionExplainer.ts`

Esses arquivos deixam visivel o risco de plugins, automacao remota e execucao sem aprovacao humana.

## Web, prompt injection e entrada externa

- `WebFetchTool-prompt.ts`
- `WebSearchTool-prompt.ts`
- `promptShellExecution.ts`

Esses arquivos nao sao "prompt injection defense" em nome, mas sao a parte da superficie onde conteudo externo, web e comandos embutidos podem contaminar a execucao.

## Ponto de maior interesse

`yoloClassifier.ts` e o arquivo mais importante desta extracao porque aponta para templates ausentes que provavelmente carregam a logica central de decisao de seguranca.
