# `jls build`

Compila um projeto JLScript para artefato nativo.

```powershell
jls build [arquivo.jls] --target <target> [--release|--debug]
jls build <arquivo.jls> [--release|--debug] [-o <arquivo>]
```

## Opções

- `--release`: modo Release. É o padrão quando `--debug` não é usado.
- `--debug`: modo Debug.
- `-t`, `--target <target>`: escolhe target.
- `--verbose`: detalha arquivos do pacote/build.
- `-o`, `--output <arquivo>`: saída do compilador nativo legado.
- `-h`, `--help`: ajuda.

`--release` e `--debug` não podem ser usados juntos.

Quando há target explícito ou definido em `jls.project`, o build usa `BuildManager` e grava em `dist/<target>/...`. Nesse modo, `--output` é rejeitado.

Sem target, o comando usa o compilador nativo legado e exige um arquivo de entrada explícito.
