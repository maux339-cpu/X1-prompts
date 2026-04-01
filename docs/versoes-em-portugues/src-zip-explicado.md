# Src Zip Explicado

## O que o pacote mostra

O `src.zip` parece ser um recorte de codigo-fonte real de um agente com muita capacidade operacional. O interesse para seguranca nao esta em malware obvio, e sim no fato de que ele combina shell, rede, permissao, plugin, subagente e modo de automacao.

## Arquivos principais em portugues

### `security-review.ts`

E o revisor de seguranca do pacote. Procura vulnerabilidades com chance real de exploracao, como injecao, traversal, bypass de auth, problemas de certificado, desserializacao insegura e uso perigoso de `eval`.

### `BashTool-prompt.ts`

E a camada que diz ao agente como usar Bash sem virar uma maquina de dano. Reforca respeito ao sandbox, evita destrutividade gratuita e empurra o agente para ferramentas mais seguras quando elas existem.

### `PowerShellTool-prompt.ts`

Faz o mesmo papel no Windows, com atencao especial a quoting, `Invoke-Expression`, download cradle, persistencia e elevacao.

### `BypassPermissionsModeDialog.tsx`

Nao e prompt de modelo, mas e um aviso central de risco. Ele deixa claro que rodar sem aprovacao humana aumenta muito a chance de dano operacional.

### `PluginTrustWarning.tsx`

Explica que plugin, MCP e codigo externo ampliam a superficie de ataque. Mesmo que o nucleo pareca seguro, extensoes ruins podem virar o ponto de quebra.

### `RemoteTriggerTool-prompt.ts`

Mostra como automatizar gatilhos remotos sem despejar token no shell. O valor de seguranca aqui e reduzir vazamento de credencial.

### `yoloClassifier.ts`

E o arquivo mais sensivel da amostra. Ele monta o classificador de permissoes e do auto mode. O contorno veio no ZIP, mas os templates-base em `.txt` nao vieram.

## O que isso significa para a nossa area

- defensivo: ha muita logica para bloquear injecao, persistencia, exfiltracao e execucao abusiva
- ofensivo-correlato: qualquer falha nessa camada pode virar RCE operacional, leitura de segredo ou bypass de aprovacao
- trust: plugin, remote trigger e subagente ampliam muito a superficie

## O que faltou na amostra

Os arquivos abaixo foram referenciados, mas nao vieram no ZIP:

- `auto_mode_system_prompt.txt`
- `permissions_external.txt`
- `permissions_anthropic.txt`

Esses parecem ser o texto-base do classificador mais importante do pacote.
