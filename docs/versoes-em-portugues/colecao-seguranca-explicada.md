# Colecao Seguranca Explicada

## 01. Core review

Arquivo central:

- `security-review.ts`

Esse bloco existe para revisar mudancas de codigo com criterio de exploracao real. E o melhor ponto para entender a filosofia defensiva do pacote.

## 02. Shell guardrails

Arquivos principais:

- `BashTool-prompt.ts`
- `BashTool-bashSecurity.ts`
- `BashTool-bashPermissions.ts`
- `BashTool-readOnlyValidation.ts`
- `PowerShellTool-prompt.ts`
- `PowerShellTool-powershellSecurity.ts`
- `PowerShellTool-powershellPermissions.ts`
- `PowerShellTool-readOnlyValidation.ts`

Em termos simples:

Essa area tenta impedir que shell vire um canal livre para destrutividade, exfiltracao, persistencia ou execucao arbitraria. O Bash cobre substituicao de comando, expansao e evasao. O PowerShell cobre `Invoke-Expression`, nested shell, encoded command, download cradle e elevacao.

## 03. Permissoes

Arquivos principais:

- `permissions-core.ts`
- `permissionsLoader.ts`
- `permissionValidation.ts`
- `permissionExplainer.ts`
- `dangerousPatterns.ts`
- `bashClassifier.ts`
- `classifierDecision.ts`
- `classifierShared.ts`
- `filesystem.ts`
- `shellRuleMatching.ts`
- `bypassPermissionsKillswitch.ts`
- `ssrfGuard.ts`

Em termos simples:

Aqui fica o motor que decide quando perguntar, quando negar e quando permitir. Ele combina regras, classificador, explicacao de risco e validacao de caminho. Para estudo defensivo, essa e a area mais importante depois do `yoloClassifier`.

## 04. Trust e remoto

Arquivos principais:

- `BypassPermissionsModeDialog.tsx`
- `PluginTrustWarning.tsx`
- `TrustDialog.tsx`
- `remoteManagedSettings-securityCheck.tsx`
- `RemoteTriggerTool-prompt.ts`
- `remotePermissionBridge.ts`
- `bridgePermissionCallbacks.ts`
- `yoloClassifier.ts`

Em termos simples:

Esse grupo mostra como o sistema lida com confianca, modo remoto e execucao sem aprovacao. Tambem mostra o risco estrutural: se trust for mal validado, o agente pode receber capacidade demais sem supervisao suficiente.

## 05. Superficie de prompt

Arquivos principais:

- `systemPrompt.ts`
- `systemPromptSections.ts`
- `prompts.ts`
- `AgentTool-prompt.ts`
- `WebFetchTool-prompt.ts`
- `WebSearchTool-prompt.ts`
- `promptShellExecution.ts`
- `execPromptHook.ts`

Em termos simples:

Essa camada mostra como o sistema monta prompts, abre subagentes, usa busca web e executa hooks derivados de prompt. E a parte mais ligada a prompt injection, contaminacao de contexto e acoplamento perigoso entre texto e execucao.

## Julgamento final

Para leitura humana, esta colecao cobre bem o ciclo completo:

- revisao de codigo
- shell e PowerShell
- decisoes de permissao
- trust e bypass
- injecao e superficie de prompt

O unico vazio realmente importante continua sendo o texto-base do `yoloClassifier`, porque ele nao estava presente na amostra original.
