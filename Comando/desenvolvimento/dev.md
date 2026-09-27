# `jls dev`

Pipeline de desenvolvimento do próprio JLScript.

Estes comandos só funcionam no checkout de desenvolvimento, identificado pela presença de `CMakeLists.txt` e `src/`.

```powershell
jls dev
jls dev build
jls dev watch
jls dev clean
jls dev status
jls dev help
```

Aliases implementados incluem `--build`, `--watch`, `-w`, `--clean`, `-c`, `--status`.

- `dev` ou `dev build`: reconstrói e sincroniza o executável após validações.
- `dev watch`: observa alterações no código de desenvolvimento e aciona o pipeline.
- `dev clean`: faz build limpo.
- `dev status`: mostra estado do ambiente de desenvolvimento.

A ajuda do código deixa explícito que `src/` é a fonte de verdade do executável de desenvolvimento.
