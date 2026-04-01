# Public System Prompts

## O que tem aqui

Esta pasta agrupa material publico focado em seguranca:

- monitoramento de acoes autonomas
- bloqueio de comandos e injeção
- revisao de seguranca
- bypass de permissao
- componentes relacionados a trust e execucao negada

## Arquivos principais

- `prompts-ciberseguranca.json`
  Resumo em portugues dos prompts mais relevantes para ciberseguranca.

- `agent-prompt-security-monitor-for-autonomous-agent-actions-first-part.md`
- `agent-prompt-security-monitor-for-autonomous-agent-actions-second-part.md`
  Nucleo de classificacao de risco para acoes autonomas.

- `agent-prompt-security-review-slash-command.md`
  Prompt de revisao de seguranca de alteracoes em branch/PR.

- `system-prompt-tool-execution-denied.md`
  Regra de nao contornar negacao de ferramenta de forma maliciosa.

- `data-agent-sdk-reference-typescript.md`
- `data-agent-sdk-reference-python.md`
  Referencias com modos de permissao, incluindo bypass.

## Uso recomendado

Ler nesta ordem:

1. `prompts-ciberseguranca.json`
2. monitor de seguranca
3. security review
4. negacao de ferramenta
5. modos de permissao no SDK

