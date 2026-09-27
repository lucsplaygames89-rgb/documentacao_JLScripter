# #process

A biblioteca **`#process`** executa comandos, inicia programas e consulta processos do sistema operacional.

```jls
import #process
```

## Executar comando

```jls
va resultado = process.executar("git --version")

mostrar(resultado.saida)
mostrar(resultado.erro)
mostrar(resultado.codigo)
```

O retorno possui `saida`, `erro` e `codigo`.

## Iniciar programa

```jls
va processo = process.iniciar("programa")
```

Com argumentos:

```jls
va processo = process.iniciar("programa", ["--help"])
```

O handle retornado possui operações nativas como `ativo`, `esperar` e `encerrar`.

```jls
mostrar(processo.ativo())
va codigo = processo.esperar()
```

## Listar processos

```jls
va processos = process.listar()
```

Cada item contém `pid` e `nome`.

## Verificar PID

```jls
se (process.existe(1234)) {
    mostrar("Processo ativo")
}
```

| Método | Função |
|---|---|
| `executar(comando)` | Executa via shell e captura resultado |
| `iniciar(programa, argumentos?)` | Inicia processo diretamente |
| `listar()` | Lista processos |
| `existe(pid)` | Verifica se PID existe |
