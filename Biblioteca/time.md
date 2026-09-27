# #time

A biblioteca nativa de tempo fornece hora local e timers. O módulo interno é `tempo` e possui aliases em inglês para as operações de tempo.

## Data e hora atual

```jls
va agora = tempo.agora()
mostrar(agora.ano)
mostrar(agora.mes)
mostrar(agora.dia)
mostrar(agora.hora)
```

`tempo.agora()` retorna `ano`, `mes`, `dia`, `hora`, `minuto`, `segundo` e `milissegundo`.

A versão inglesa é:

```jls
va now = time.now()
mostrar(now.year)
mostrar(now.month)
```

## Executar depois

```jls
tempo.depois(2 seg, func() {
    mostrar("Passaram 2 segundos")
})
```

Alias: `time.after()`.

## Executar repetidamente

```jls
tempo.cada(1 seg, func() {
    mostrar("Executando novamente")
})
```

Alias: `time.every()`.

Os timers exigem uma duração e uma função callback. A duração usa o sistema nativo de tempo do JLScript, como `500 ms`, `2 seg` ou outras unidades reconhecidas pela linguagem.

| PT | EN | Função |
|---|---|---|
| `tempo.agora()` | `time.now()` | Hora local atual |
| `tempo.depois()` | `time.after()` | Timer de uma execução |
| `tempo.cada()` | `time.every()` | Timer repetitivo |
