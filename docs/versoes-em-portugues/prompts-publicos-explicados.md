# Prompts Publicos Explicados

## Security Monitor

Arquivos:

- `agent-prompt-security-monitor-for-autonomous-agent-actions-first-part.md`
- `agent-prompt-security-monitor-for-autonomous-agent-actions-second-part.md`

Em portugues simples:

Esse bloco funciona como um fiscal de seguranca para agentes autonomos. Ele observa o que o agente pretende fazer e decide se a acao parece normal ou se entra em zona de risco, como exfiltracao, mudanca de infraestrutura, acesso indevido, auto-modificacao ou uso perigoso de ferramentas. O monitor tambem tenta impedir que o agente trate resultado de busca, arquivo ou pagina web como se fosse instrucao confiavel do usuario.

Valor para pentest:

- detectar prompt injection em arquivos, paginas ou saida de ferramentas
- bloquear exfiltracao para destinos externos
- barrar execucao de codigo externo ou vindo de repo nao confiavel
- impedir criacao de superficies de RCE e automacao insegura

Risco se vazado:

Quem estuda esse monitor entende melhor quais padroes levam a bloqueio e pode tentar dividir a acao maliciosa em passos menores para escapar da classificacao.

## Bash Command Prefix Detection

Arquivo:

- `agent-prompt-bash-command-prefix-detection.md`

Em portugues simples:

Esse prompt examina o inicio e a estrutura de um comando para identificar montagem suspeita, injecao, substituicao de comando e tecnicas de evasao. Ele existe para travar cadeias de shell que parecem simples na superficie, mas escondem execucao adicional.

Valor para pentest:

- bloquear `curl | bash`, backticks, `$()` e montagens com exfiltracao
- detectar wrappers usados para mascarar `eval`, `exec` ou chamada remota
- reduzir abuso de shell como canal de RCE

Risco se vazado:

Um atacante ganha visibilidade sobre o tipo de assinatura que dispara alerta e pode tentar obfuscar melhor o comando.

## Security Review

Arquivo:

- `agent-prompt-security-review-slash-command.md`

Em portugues simples:

Esse prompt faz revisao de mudanca em codigo com foco em vulnerabilidades que realmente podem ser exploradas. Em vez de listar toda boa pratica ausente, ele procura injecao, bypass de autenticacao, escalacao de privilegio, desserializacao insegura, exposure de segredo e outras classes com impacto concreto.

Valor para pentest:

- revisar PR suspeito ou branch com indicio de malware
- detectar mudanca maliciosa distribuida em varios arquivos
- filtrar falso positivo em revisao automatica

Risco se vazado:

Ajuda a entender o que o revisor tende a ignorar, abrindo espaco para alteracoes menos obvias.

## Tool Execution Denied

Arquivo:

- `system-prompt-tool-execution-denied.md`

Em portugues simples:

Esse texto diz ao agente que uma negativa de ferramenta nao deve ser contornada de forma maliciosa. Se uma acao foi bloqueada, ele pode tentar uma alternativa razoavel, mas nao pode usar uma ferramenta secundaria para burlar a intencao do bloqueio.

Valor para pentest:

- impedir bypass por cadeia indireta de ferramentas
- reforcar parada segura quando a permissao nao existe
- reduzir abuso de teste, build ou script como desvio de execucao

Risco se vazado:

O vazamento ajuda a mapear a fronteira entre contorno aceitavel e contorno proibido.

## Referencias de Permissao do SDK

Arquivos:

- `data-agent-sdk-reference-typescript.md`
- `data-agent-sdk-reference-python.md`

Em portugues simples:

Esses arquivos nao sao prompts de defesa puros, mas mostram como o produto modela modos de permissao, inclusive configuracoes perigosas de bypass. Eles ajudam a entender como a superficie operacional muda quando o agente roda com mais liberdade.

Valor para pentest:

- desenhar laboratorios com restricao real
- comparar modos seguros e modos de alto risco
- entender onde um bug de configuracao pode virar execucao sem aprovacao

Risco se vazado:

Mostram com clareza os modos de operacao mais arriscados, o que diminui o custo de exploracao para quem procura bypass.
