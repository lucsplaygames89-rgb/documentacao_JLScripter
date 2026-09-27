# #file

A biblioteca **`#file`** fornece operações de arquivos e pastas.

```jls
import #file
```

## Arquivos

```jls
va texto = file.ler("dados.txt")
file.escrever("dados.txt", "Olá")
file.adicionar("dados.txt", "\nNova linha")
```

Também existem:

```jls
file.existe("dados.txt")
file.copiar("dados.txt", "backup/dados.txt")
file.mover("dados.txt", "dados/arquivo.txt")
file.excluir("dados/arquivo.txt")
file.tamanho("backup/dados.txt")
```

`file.info(caminho)` retorna um objeto com `nome`, `tamanho`, `extensao`, `pasta` e `existe`.

```jls
va info = file.info("app/config.json")
mostrar(info.extensao)
```

## Pastas

As operações de diretório ficam em `file.pasta`:

```jls
file.pasta.criar("dados")
va itens = file.pasta.listar("dados")
file.pasta.existe("dados")
file.pasta.copiar("dados", "backup")
file.pasta.mover("backup", "arquivos/backup")
file.pasta.excluir("arquivos/backup")
```

## Métodos

| Método | Função |
|---|---|
| `ler` | Lê arquivo como texto |
| `escrever` | Escreve/substitui conteúdo |
| `adicionar` | Acrescenta conteúdo |
| `existe` | Verifica existência |
| `copiar` | Copia arquivo |
| `mover` | Move arquivo |
| `excluir` | Exclui arquivo |
| `tamanho` | Obtém tamanho |
| `info` | Obtém metadados |
| `pasta.criar` | Cria diretório |
| `pasta.listar` | Lista conteúdo |
| `pasta.excluir` | Exclui diretório |
| `pasta.existe` | Verifica diretório |
| `pasta.copiar` | Copia diretório |
| `pasta.mover` | Move diretório |
