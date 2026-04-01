# Analise do src.zip

## Resumo executivo

O `src.zip` analisado parece ser um recorte real do codigo-fonte de um CLI grande em TypeScript/TSX, aparentando estar ligado ao Claude Code.

Nao foram vistos sinais fortes de dropper ou malware obvio. O risco principal esta na superficie poderosa do produto:

- execucao de shell e subprocessos
- modos de bypass de permissao
- sandbox e politicas de acesso
- bridge remota
- telemetria e uploads
- plugins e marketplaces

## Arquivos core de seguranca

- `arquivos-relevantes/security-review.ts`
  Prompt de revisao de seguranca ofensivo-defensiva.

- `arquivos-relevantes/BashTool-prompt.ts`
  Prompt operacional de shell com guardrails.

- `arquivos-relevantes/PowerShellTool-prompt.ts`
  Equivalente em PowerShell.

- `arquivos-relevantes/BypassPermissionsModeDialog.tsx`
  Aviso explicito sobre modo sem aprovacao.

- `arquivos-relevantes/PluginTrustWarning.tsx`
  Aviso de confianca para plugins.

- `arquivos-relevantes/RemoteTriggerTool-prompt.ts`
  Prompt para triggers remotos com token tratado em processo.

- `arquivos-relevantes/yoloClassifier.ts`
  Montador do classificador de permissoes e auto mode.

## Observacao importante

O ZIP nao trouxe todos os prompts-base do classificador. O arquivo `yoloClassifier.ts` referencia templates `.txt` que parecem ser o nucleo do sistema de decisao, mas esses templates nao vieram na extracao.

## Leitura recomendada

1. `security-review.ts`
2. `BashTool-prompt.ts`
3. `PowerShellTool-prompt.ts`
4. `BypassPermissionsModeDialog.tsx`
5. `PluginTrustWarning.tsx`
6. `yoloClassifier.ts`

