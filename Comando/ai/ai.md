# `jls ai`

Interface de terminal da JLS AI.

```powershell
jls ai
jls ai <pergunta>
jls ai --run <arquivo.jls>
jls ai --debug <pergunta>
jls ai ask-b64 <pergunta-base64>
```

## Informações

```powershell
jls ai --help
jls ai --version
jls ai --status
jls ai --erro
```

Também existem aliases como `version`, `status`, `erro`, `error`, `--error`, além dos atalhos `-v` e `-s` onde implementados.

Sem pergunta, abre o modo interativo. Nele, `exit`/`sair` encerra a sessão. O modo interativo também reconhece `.run <arquivo>` para executar um arquivo através do fluxo assistido.
