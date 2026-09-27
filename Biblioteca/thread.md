# #thread

A biblioteca **`#thread`** permite criar tarefas executadas em threads.

```jls
import #thread
```

## Criar tarefa

```jls
va tarefa = thread.criar(func() {
    retornar 10
})
```

`thread.criar()` exige uma função e retorna um objeto de tarefa.

A tarefa possui os métodos:

```jls
tarefa.iniciar()
va resultado = tarefa.esperar()
```

`esperar()` inicia a tarefa automaticamente caso ela ainda não tenha sido iniciada.

## Executar várias tarefas

```jls
va a = thread.criar(func() { retornar 10 })
va b = thread.criar(func() { retornar 20 })

va resultados = thread.executar([a, b])
```

`thread.executar()` inicia todas as tarefas da lista e depois aguarda seus resultados, retornando uma lista na mesma ordem.

| Método | Função |
|---|---|
| `thread.criar(funcao)` | Cria tarefa |
| `thread.executar(lista)` | Executa várias tarefas e reúne resultados |
| `tarefa.iniciar()` | Inicia uma tarefa |
| `tarefa.esperar()` | Aguarda e retorna resultado |
