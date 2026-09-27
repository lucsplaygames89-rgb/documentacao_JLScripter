# `jls fmt`

Formata arquivos `.jls`.

```powershell
jls fmt <arquivo.jls|diretorio>
jls fmt --check <arquivo.jls|diretorio>
```

O comando percorre diretórios recursivamente e ignora `.git`, `build`, `node_modules` e `.jls-cache`.

Na implementação atual, o formatador remove espaços/tabs no fim das linhas preservando o restante do conteúdo e os comentários.

`--check` não altera arquivos. Ele retorna falha se encontrar arquivos que precisariam ser formatados.
