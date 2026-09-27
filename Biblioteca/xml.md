# #xml

A biblioteca **`#xml`** analisa, cria, lê e salva XML.

```jls
import #xml
```

## Analisar texto XML

```jls
va dados = xml.parse("<usuario><nome>Lucas</nome></usuario>")
```

O parser trata elementos, atributos, texto e entidades XML e converte a estrutura para valores utilizáveis no JLScript.

## Ler arquivo

```jls
va dados = xml.ler("config.xml")
```

## Criar XML

```jls
va texto = xml.criar(dados)
mostrar(texto)
```

## Salvar

```jls
xml.salvar("saida.xml", dados)
```

A biblioteca escapa caracteres necessários ao gerar XML e valida nomes de elementos.

| Método | Função |
|---|---|
| `parse(texto)` | Analisa XML em memória |
| `ler(caminho)` | Lê e analisa arquivo XML |
| `criar(valor)` | Gera texto XML |
| `salvar(caminho, valor)` | Gera e grava XML |
