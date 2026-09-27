# #csv

A biblioteca **`#csv`** lê e grava arquivos CSV.

```jls
import #csv
```

## Ler

```jls
va linhas = csv.ler("usuarios.csv")
```

Também é possível informar o separador como segundo argumento.

```jls
va linhas = csv.ler("usuarios.csv", ";")
```

A primeira linha é utilizada como cabeçalho e as linhas seguintes são convertidas em objetos usando os nomes das colunas.

## Escrever

```jls
csv.escrever("usuarios.csv", dados)
```

A função recebe caminho, dados e opcionalmente opções. O código atual reconhece a opção `separador`.

```jls
csv.escrever("usuarios.csv", dados, {
    separador: ";"
})
```

Campos que contêm separador, aspas ou quebras de linha são escapados durante a escrita.

| Método | Função |
|---|---|
| `csv.ler(caminho)` | Lê CSV |
| `csv.ler(caminho, separador)` | Lê com separador personalizado |
| `csv.escrever(caminho, dados)` | Grava CSV |
| `csv.escrever(caminho, dados, opcoes)` | Grava com opções |
