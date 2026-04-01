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

## Conclusao da revisao

Para a area de seguranca ofensiva e defensiva, o repositorio agora cobre os blocos principais:

- monitoramento e revisao
- shell guardrails
- permissao e classificacao
- trust, bypass e remoto
- superficie de prompt e hooks

Se ainda houver mais material sensivel fora daqui, a lacuna mais provavel esta nos artefatos internos que nao acompanharam a amostra, especialmente prompts-base de classificador e componentes internos ant-only.
