# Revisao de Cobertura

## O que foi revisado

Foi feita uma nova varredura da extracao em `src_zip_extract2/src` procurando:

- prompts com nome explicito
- arquivos de permissao e bypass
- validacoes de shell e PowerShell
- defesa contra SSRF
- pontos de trust, plugin e subagentes

## O que estava faltando e foi adicionado

- `WebFetchTool-prompt.ts`
- `WebSearchTool-prompt.ts`
- `AgentTool-prompt.ts`
- `ssrfGuard.ts`
- `BashTool-bashSecurity.ts`
- `BashTool-readOnlyValidation.ts`
- `PowerShellTool-powershellSecurity.ts`
- `PowerShellTool-readOnlyValidation.ts`

Esses arquivos foram copiados para `docs/src-zip-analise/arquivos-relevantes/ampliados` e indexados no catalogo.

## Colecao ampliada encontrada no projeto

Durante a revisao, tambem foi confirmada a existencia de uma colecao mais ampla em:

- `docs/src-zip-analise/colecao-seguranca/01-core-review`
- `docs/src-zip-analise/colecao-seguranca/02-shell-guardrails`
- `docs/src-zip-analise/colecao-seguranca/03-permissoes`
- `docs/src-zip-analise/colecao-seguranca/04-trust-remoto`
- `docs/src-zip-analise/colecao-seguranca/05-superficie-de-prompt`

Essa colecao fecha a maior parte da cobertura operacional da area de seguranca no `src.zip`, inclusive com arquivos alem dos prompts centrais, como `bashPermissions`, `powershellPermissions`, `bridgePermissionCallbacks`, `systemPrompt`, `prompts.ts` e `execPromptHook.ts`.

## Conclusao da revisao

Para a area de seguranca digital ofensiva e defensiva, os principais blocos agora cobertos no repositorio sao:

- monitoramento de acao autonoma
- revisao de seguranca de codigo
- shell e PowerShell com guardrails
- bypass de permissao
- trust warning para plugins
- subagentes e coordenacao
- busca e fetch web com superficie de injecao
- defesa contra SSRF
- validacao de comandos somente leitura

## O que continua ausente

O principal vazio permanece o mesmo:

- `utils/permissions/yolo-classifier-prompts/auto_mode_system_prompt.txt`
- `utils/permissions/yolo-classifier-prompts/permissions_external.txt`
- `utils/permissions/yolo-classifier-prompts/permissions_anthropic.txt`

Esses templates sao referenciados por `yoloClassifier.ts`, mas nao vieram no `src.zip`. Entao o repositorio cobre o contorno e a montagem do classificador, mas nao o texto-base integral desses prompts.

## Julgamento final

Para fins de estudo da nossa area de seguranca, nao ficou faltando nenhum prompt principal que estivesse realmente presente na amostra local. O que falta agora sao artefatos que a propria amostra nao trouxe, principalmente os templates `.txt` do `yoloClassifier`.
