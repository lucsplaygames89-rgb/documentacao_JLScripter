# `jls run`

Executa um arquivo fonte JLScript usando o runtime oficial.

```powershell
jls run <arquivo.jls> [--time] [-- argumentos]
```

Também é possível omitir `run`:

```powershell
jls app.jls
```

## Opções

- `-h`, `--help`: mostra ajuda.
- `--time`: imprime o tempo total em milissegundos.
- `--`: tudo depois deste separador é entregue ao programa.

Exemplos:

```powershell
jls run app.jls
jls run app.jls --time
jls run app.jls -- --porta 3000
```

O comando aceita somente arquivos `.jls`. Arquivos `.jlb` não são executados nesta versão.

## Relação com `#cli`

Antes de executar o arquivo, o JLShell armazena os argumentos encontrados depois de `--`. Um programa que usa `#cli` pode consumi-los ao chamar `app.executar()`.
