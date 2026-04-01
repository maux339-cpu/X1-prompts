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
- `PowerShellTool-prompt.ts`
- `system-prompt-tool-execution-denied.md`
- `data-agent-sdk-reference-typescript.md`
- `data-agent-sdk-reference-python.md`
- `yoloClassifier.ts`

Aqui fica a camada mais sensivel para abuso operacional ou RCE indireto.

## Trust, bypass e superficie ampliada

- `BypassPermissionsModeDialog.tsx`
- `PluginTrustWarning.tsx`
- `RemoteTriggerTool-prompt.ts`

Esses arquivos deixam visivel o risco de plugins, automacao remota e execucao sem aprovacao humana.

## Ponto de maior interesse

`yoloClassifier.ts` e o arquivo mais importante desta extracao porque aponta para templates ausentes que provavelmente carregam a logica central de decisao de seguranca.
