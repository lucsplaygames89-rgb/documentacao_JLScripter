# `jls lint`

Analisa sintaxe e diagnósticos de arquivos JLScript.

```powershell
jls lint <arquivo.jls|diretorio>
```

Para cada arquivo, o comando executa o lexer e o parser. Erros são transformados em diagnósticos `JLError` e renderizados com o código fonte.

Assim como `fmt`, a busca recursiva ignora `.git`, `build`, `node_modules` e `.jls-cache`.
