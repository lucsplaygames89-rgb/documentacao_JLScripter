# `jls language`

Ferramentas do **Language Development Kit** associado ao `#compiler`.

Alias do comando principal:

```powershell
jls linguagem ...
```

## Dependência real

A própria ajuda do JLShell informa que a definição utilizada por estes comandos é produzida por:

```jls
import #compiler
```

seguido da construção da linguagem com:

```jls
lang.build()
```

Portanto, o comando não simplesmente transforma qualquer arquivo em uma linguagem. Ele carrega uma definição LDK previamente construída.

## Executar linguagem

```powershell
jls language run <Linguagem> <arquivo>
```

Carrega a definição pelo nome e executa o arquivo com `LanguageKit::run`.

## Inspecionar tokens

```powershell
jls language inspect <Linguagem> <arquivo> --tokens
```

Imprime, para cada token:

```text
linha:coluna  tipo  valor
```

`--tokens` é obrigatório nesta implementação.

## Doctor da linguagem

```powershell
jls language doctor <Linguagem>
```

Carrega e valida a definição e mostra o estado das features. Quando válida, informa que a linguagem é compatível com o backend bytecode atual.
