# Home

Painel rapido para navegar o repositório `X1-prompts`.

## Onde Comecar

| Perfil | Ler primeiro | Objetivo |
| --- | --- | --- |
| Visao executiva | `versoes-em-portugues/README.md` | Entender a estrutura sem ler codigo |
| Estudo de prompts publicos | `versoes-em-portugues/prompts-publicos-explicados.md` | Ver o nucleo de monitoramento, review e bloqueio |
| Estudo do `src.zip` | `versoes-em-portugues/src-zip-explicado.md` | Entender shell, permissao, trust e risco |
| Analise completa | `versoes-em-portugues/colecao-seguranca-explicada.md` | Percorrer a colecao ampliada por tema |
| Auditoria tecnica | `guias-em-portugues/revisao-de-cobertura.md` | Confirmar o que entrou e o que ficou ausente |

## Mapa Por Tema

| Tema | Categoria principal | Arquivos de entrada | Risco predominante |
| --- | --- | --- | --- |
| Defensivo | `core-review` | `security-review.ts`, `Security Review`, `Security Monitor` | deteccao de vulnerabilidade exploravel e bloqueio de dano |
| Ofensivo-correlato | `shell-guardrails` | `BashTool-*`, `PowerShellTool-*`, `dangerousPatterns.ts` | RCE operacional, persistencia, exfiltracao |
| Prompt injection | `superficie-de-prompt` | `WebFetchTool-prompt.ts`, `WebSearchTool-prompt.ts`, `promptShellExecution.ts`, `execPromptHook.ts` | contaminacao de contexto e execucao derivada de texto |
| Permissoes | `permissoes` | `permissions-core.ts`, `permissionsLoader.ts`, `classifierDecision.ts`, `yoloClassifier.ts` | bypass de aprovacao e classificacao errada |
| Trust | `trust-remoto` | `PluginTrustWarning.tsx`, `BypassPermissionsModeDialog.tsx`, `TrustDialog.tsx` | plugins inseguros, remoto, autorizacao excessiva |

## Tabela De Risco

| Bloco | Nivel | Motivo |
| --- | --- | --- |
| `yoloClassifier.ts` | Alto | coordena a decisao automatica de permissao e referencia templates ausentes |
| `shell-guardrails` | Alto | qualquer falha pode liberar shell para execucao arbitraria, persistencia ou exfiltracao |
| `superficie-de-prompt` | Alto | une busca web, hooks e execucao derivada de prompt |
| `trust-remoto` | Alto | concentra bypass, plugins, remoto e dialogos de confianca |
| `core-review` | Medio | atua como defesa; risco maior e de evasao de heuristica |
| `catalogos JSON` | Baixo | ajudam a navegar, mas nao executam nada |

## Navegacao Direta

| Secao | Caminho |
| --- | --- |
| Prompts publicos originais | `public-system-prompts/` |
| Analise do ZIP | `src-zip-analise/` |
| Colecao ampliada de seguranca | `src-zip-analise/colecao-seguranca/` |
| Guias em portugues | `guias-em-portugues/` |
| Versoes explicadas em portugues | `versoes-em-portugues/` |
| Indices JSON | `indices/` |

## Lacunas Confirmadas

| Item ausente | Impacto |
| --- | --- |
| `yolo-classifier-prompts/*.txt` | falta o texto-base do classificador mais sensivel |
| implementacao completa interna de `bashClassifier.ts` | parte do fluxo real de classificacao nao veio na amostra |

## Julgamento Final

O repositório cobre o nucleo da area ofensiva e defensiva que estava presente na amostra local. O que falta nao foi omitido por organizacao; nao veio no material original analisado.
