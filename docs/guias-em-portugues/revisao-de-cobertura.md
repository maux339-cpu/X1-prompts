# Revisao De Cobertura

## O que foi revisto

Foi feita uma segunda passada focada em:

- prompts publicos copiados
- prompts e builders no `src.zip`
- shell guardrails
- mecanismos de permissao
- trust dialogs
- hooks e superficie de prompt injection

## O que entrou nesta revisao

- colecao separada em `docs/src-zip-analise/colecao-seguranca`
- novos arquivos de shell e permissao que nao estavam na primeira selecao
- arquivos de trust e remoto
- builders de prompt e hook de prompt
- catalogo de cobertura em JSON

## O que continua faltando na amostra original

- templates referenciados por `yoloClassifier.ts`
  Esses arquivos `.txt` parecem ser o nucleo mais valioso da politica de classificacao e nao vieram no ZIP.

- classificador Bash real
  `bashClassifier.ts` veio como stub para build externa, o que indica ausencia da implementacao interna mais rica.

## Arquivos adjacentes nao puxados para a colecao principal

Esses arquivos apareceram na segunda varredura, mas ficaram fora da colecao principal por serem mais operacionais, de UX ou de apoio do que prompts centrais de seguranca:

- `commands/review.ts`
- `commands/review/reviewRemote.ts`
- `commands/review/ultrareviewCommand.tsx`
- `commands/sandbox-toggle/sandbox-toggle.tsx`
- `commands/hooks/hooks.tsx`
- `components/hooks/PromptDialog.tsx`
- `utils/hooks/hooksConfigManager.ts`
- `utils/hooks/hookHelpers.ts`
- `utils/hooks/hookEvents.ts`
- `services/mcp/channelPermissions.ts`
- `services/api/dumpPrompts.ts`
- `services/api/promptCacheBreakDetection.ts`
- `utils/classifierApprovals.ts`
- `utils/classifierApprovalsHook.ts`
- `utils/processUserInput/processTextPrompt.ts`

## Conclusao da revisao

Para a area de seguranca ofensiva e defensiva, o repositorio agora cobre os blocos principais:

- monitoramento e revisao
- shell guardrails
- permissao e classificacao
- trust, bypass e remoto
- superficie de prompt e hooks

Se ainda houver mais material sensivel fora daqui, a lacuna mais provavel esta nos artefatos internos que nao acompanharam a amostra, especialmente prompts-base de classificador e componentes internos ant-only.
