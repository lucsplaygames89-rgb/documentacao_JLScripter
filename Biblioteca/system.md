# #system

A biblioteca **`#system`** expõe informações do sistema operacional e operações básicas de arquivos e diretórios.

```jls
import #system
```

## Sistema

```jls
mostrar(system.os())
mostrar(system.so())
mostrar(system.architecture())
mostrar(system.arquitetura())
mostrar(system.username())
mostrar(system.usuario())
```

Os pares PT/EN retornam a mesma categoria de informação.

## Arquivos

O submódulo pode ser acessado como `system.file` ou `system.arquivo`.

```jls
system.arquivo.existe("config.txt")
va texto = system.arquivo.ler("config.txt")
system.arquivo.escrever("config.txt", "JLScript")
system.arquivo.criar("novo.txt", "conteúdo")
system.arquivo.apagar("novo.txt")
mostrar(system.arquivo.tamanho("config.txt"))
mostrar(system.arquivo.extensao("config.txt"))
```

Aliases ingleses: `exists`, `read`, `write`, `create`, `delete`, `size`, `extension`.

## Pastas

`system.folder` e `system.pasta` apontam para o submódulo de diretórios.

```jls
system.pasta.criar("dados")
va itens = system.pasta.listar("dados")
mostrar(system.pasta.atual())
system.pasta.entrar("dados")
```

Também existem operações de apagar pasta e aliases `create`, `delete`, `list`, `current` e `cd`.

`#system` é voltado a utilidades diretas do sistema. Para operações mais completas de arquivos e pastas, existe também `#file`.
