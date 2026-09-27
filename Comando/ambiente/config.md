# `jls config`

Mostra ou altera configurações do JLShell e da JLS AI.

Sem argumentos:

```powershell
jls config
```

mostra as configurações atuais.

## Subcomandos implementados

```powershell
jls config theme <dark|light|mono>
jls config no-color <1|0>
jls config update-check <on|off>
jls config ai-typing <on|off>
jls config ai-typing-speed <fast|normal|slow>
jls config ai-spinner <on|off>
jls config ai-emoji <on|off>
```

`no-color` também considera `true` como ativado. Os controles `on/off` indicados acima também aceitam `1/0` internamente onde implementado.
