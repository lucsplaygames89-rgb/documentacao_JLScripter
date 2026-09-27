# `jls doctor`

Verifica o ambiente do JLShell e os toolchains.

```powershell
jls doctor
jls doctor <target>
```

Targets aceitos pela interface atual:

```text
windows
web
android
android-tv
```

Sem target, consulta todos os targets retornados pelo `ToolchainManager`. Também mostra versão instalada, diretório atual, suporte a cores e status da JLS AI.
