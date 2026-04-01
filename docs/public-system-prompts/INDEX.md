# Prompts Publicos

## O que esta nesta pasta

Este bloco concentra o material publico mais util para estudar guardrails de agentes:

- monitoramento de acoes autonomas
- bloqueio de comandos e sinais de injecao
- revisao de seguranca de codigo
- tratamento de negacao de ferramenta
- referencias de SDK e modos de permissao

## Arquivos principais

- `prompts-ciberseguranca.json`
  Resumo em portugues dos prompts publicos mais relevantes para ciberseguranca.

- `agent-prompt-security-monitor-for-autonomous-agent-actions-first-part.md`
- `agent-prompt-security-monitor-for-autonomous-agent-actions-second-part.md`
  Material central de monitoramento de risco para acoes autonomas.

- `agent-prompt-security-review-slash-command.md`
  Regras de revisao de seguranca com foco em vulnerabilidades exploraveis e reducao de falso positivo.

- `agent-prompt-bash-command-prefix-detection.md`
  Logica ligada a deteccao de padroes perigosos na prefixacao de comandos.

- `system-prompt-tool-execution-denied.md`
  Regra para nao tentar contornar uma negacao de execucao de ferramenta.

- `data-agent-sdk-reference-typescript.md`
- `data-agent-sdk-reference-python.md`
  Documentacao de modos de permissao, inclusive cenarios de bypass e risco operacional.

## Como ler

1. Comece em `prompts-ciberseguranca.json`.
2. Leia o monitor de seguranca em duas partes.
3. Passe para `agent-prompt-security-review-slash-command.md`.
4. Revise `system-prompt-tool-execution-denied.md`.
5. Feche com os arquivos de referencia do SDK.

## Observacao

Os arquivos desta pasta preservam o material copiado para consulta. As explicacoes em portugues ficam em `../guias-em-portugues`.
