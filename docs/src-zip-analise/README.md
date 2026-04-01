# Analise do src.zip

## Resumo executivo

O `src.zip` analisado parece ser um recorte real do codigo-fonte de um CLI grande em TypeScript/TSX, com forte indicio de ligacao ao Claude Code.

Nao apareceram sinais fortes de malware obvio, dropper ou backdoor simples. O risco real esta na superficie de capacidade:

- execucao de shell e subprocessos
- bypass de permissao
- sandbox e politicas de acesso
- bridge remota e sessoes
- telemetria, upload e feedback
- plugins, marketplaces e MCP

## Arquivos centrais

- `arquivos-relevantes/security-review.ts`
  Prompt de revisao de seguranca com foco em vulnerabilidades exploraveis.

- `arquivos-relevantes/BashTool-prompt.ts`
  Guardrails para shell, incluindo limites operacionais e sinais de abuso.

- `arquivos-relevantes/PowerShellTool-prompt.ts`
  Contraparte do Bash com orientacoes especificas para PowerShell.

- `arquivos-relevantes/BypassPermissionsModeDialog.tsx`
  Texto de risco para modo sem aprovacao humana.

- `arquivos-relevantes/PluginTrustWarning.tsx`
  Aviso de confianca e risco para plugins e componentes externos.

- `arquivos-relevantes/RemoteTriggerTool-prompt.ts`
  Prompt voltado a uso remoto sem expor token no shell.

- `arquivos-relevantes/yoloClassifier.ts`
  Montador do classificador de permissoes e auto mode.

## Colecao ampliada

Agora existe uma colecao separada por categoria em:

- `colecao-seguranca/01-core-review`
- `colecao-seguranca/02-shell-guardrails`
- `colecao-seguranca/03-permissoes`
- `colecao-seguranca/04-trust-remoto`
- `colecao-seguranca/05-superficie-de-prompt`

Ela inclui arquivos que faltavam na primeira selecao, como:

- `BashTool-bashSecurity.ts`
- `BashTool-bashPermissions.ts`
- `PowerShellTool-powershellSecurity.ts`
- `PowerShellTool-powershellPermissions.ts`
- `permissions-core.ts`
- `permissionExplainer.ts`
- `ssrfGuard.ts`
- `TrustDialog.tsx`
- `remoteManagedSettings-securityCheck.tsx`
- `WebFetchTool-prompt.ts`
- `WebSearchTool-prompt.ts`
- `execPromptHook.ts`

## Lacuna importante

O ZIP nao trouxe todos os templates-base do classificador. `yoloClassifier.ts` referencia arquivos `.txt` que parecem ser o nucleo da decisao automatica de seguranca, mas esses templates nao vieram na extracao.

## Como navegar

1. Comece por `security-review.ts`.
2. Leia `BashTool-prompt.ts` e `PowerShellTool-prompt.ts`.
3. Passe pelos avisos de trust e bypass.
4. Feche em `yoloClassifier.ts`.
5. Revise a `colecao-seguranca` por categoria.
6. Consulte `../guias-em-portugues/revisao-de-cobertura.md`.
7. Consulte `../indices/catalogo-cobertura-seguranca.json` para ver a classificacao consolidada.
