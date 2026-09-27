# `jls fix`

Aplica correções seguras conhecidas pelo JLShell.

```powershell
jls fix
jls fix <arquivo.jls>
```

Sem arquivo, usa `app.jls`.

## Estado atual

A correção realmente implementada nesta versão é específica: substitui a primeira ocorrência de `#htpp` por `#http`.

Se nenhuma correção conhecida for necessária, o arquivo não é alterado.
