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

## Arquivos adicionais relevantes

- `arquivos-relevantes/ampliados/WebFetchTool-prompt.ts`
  Regras de fetch web com limites de citaçao e uso de dominio aprovado.

- `arquivos-relevantes/ampliados/WebSearchTool-prompt.ts`
  Busca web com exigencia de fontes e cuidado com ano corrente.

- `arquivos-relevantes/ampliados/AgentTool-prompt.ts`
  Prompt de subagentes e fork, importante para coordenacao segura e para nao inventar resultado.

- `arquivos-relevantes/ampliados/ssrfGuard.ts`
  Bloqueio de SSRF para hooks HTTP.

- `arquivos-relevantes/ampliados/BashTool-bashSecurity.ts`
- `arquivos-relevantes/ampliados/BashTool-readOnlyValidation.ts`
- `arquivos-relevantes/ampliados/PowerShellTool-powershellSecurity.ts`
- `arquivos-relevantes/ampliados/PowerShellTool-readOnlyValidation.ts`
  Camada pratica de deteccao de execucao perigosa, evasao e comandos somente leitura.

## Colecao organizada

Para visualizacao mais completa, existe uma colecao separada por tema:

- `colecao-seguranca/01-core-review`
- `colecao-seguranca/02-shell-guardrails`
- `colecao-seguranca/03-permissoes`
- `colecao-seguranca/04-trust-remoto`
- `colecao-seguranca/05-superficie-de-prompt`

Essa colecao e a visao mais completa da area de seguranca dentro do repositorio.

## Lacuna importante

O ZIP nao trouxe todos os templates-base do classificador. `yoloClassifier.ts` referencia arquivos `.txt` que parecem ser o nucleo da decisao automatica de seguranca, mas esses templates nao vieram na extracao.

## Como navegar

1. Comece por `security-review.ts`.
2. Leia `BashTool-prompt.ts` e `PowerShellTool-prompt.ts`.
3. Passe pelos avisos de trust e bypass.
4. Feche em `yoloClassifier.ts`.
5. Revise os arquivos em `arquivos-relevantes/ampliados`.
6. Consulte `../guias-em-portugues/revisao-de-cobertura.md`.
7. Consulte `../indices/catalogo-mestre.json` para ver a classificacao consolidada.
