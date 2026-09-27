# `jls selfhost`

Ferramentas experimentais de self-hosting do JLScript.

```powershell
jls selfhost
jls selfhost status
jls selfhost test
```

Sem subcomando, usa `status`.

## `status`

Mostra o estágio atual do self-hosting. No código analisado, aparecem como `READY` o bootstrap C++, lexer, parser, MiniLang bytecode VM e `source_info`; `#compiler LDK` aparece como `PARTIAL`; formatter e compiler self-host aparecem como `PLANNED`.

## `test`

Procura `src/jls/tools/source_info.jls` subindo a árvore de diretórios e, quando encontra, executa essa ferramenta oficial escrita em JLScript.
