# #math

A biblioteca **`#math`** reúne matemática numérica, estatística, vetores, matrizes, números aleatórios e conversões angulares.

```jls
import #math
```

## Constantes

```jls
mostrar(math.PI)
mostrar(math.E)
```

## Operações numéricas

```jls
math.raiz(25)
math.raizCubica(27)
math.absoluto(-10)
math.arredondar(3.6)
math.teto(3.1)
math.piso(3.9)
math.truncar(3.9)
```

`math.subtrair()` é específico para vetores/matrizes e `math.multiplicar()` para matrizes. Para números comuns, use os operadores `-` e `*` da linguagem.

## Trigonometria e logaritmos

```jls
math.seno(1)
math.cosseno(1)
math.tangente(1)
math.aseno(0.5)
math.acosseno(0.5)
math.atangente(1)
math.log(10)
math.log10(100)
math.exp(2)
```

As funções trigonométricas trabalham em radianos. Para converter:

```jls
va rad = math.radianos(180)
va graus = math.graus(rad)
```

## Estatística

```jls
va dados = [10, 20, 20, 30]

math.media(dados)
math.mediana(dados)
math.moda(dados)
math.maximo(dados)
math.minimo(dados)
math.variancia(dados)
math.desvioPadrao(dados)
math.somaLista(dados)
math.produtoLista(dados)
```

## Vetores

```jls
va a = math.vetor(1, 2, 3)
va b = math.vetor(4, 5, 6)

math.somar(a, b)
math.subtrair(a, b)
math.normalizar(a)
math.produtoEscalar(a, b)
math.produtoVetorial(a, b)
math.distancia(a, b)
```

`produtoVetorial` exige vetores 3D. Operações entre vetores verificam se os tamanhos são compatíveis.

## Matrizes

```jls
va matriz = math.matriz([
    [1, 2],
    [3, 4]
])

math.transposta(matriz)
math.determinante(matriz)
math.inversa(matriz)
math.identidade(3)
```

Multiplicação:

```jls
va resultado = math.multiplicar(a, b)
```

Matrizes são validadas quanto às dimensões. Determinante e inversa exigem matriz quadrada, e uma matriz singular não possui inversa.

## Aleatórios

```jls
math.aleatorio()
math.inteiro(1, 10)
math.decimal(0, 100)
math.booleano()
```

`aleatorio()` retorna decimal entre 0 e 1. `inteiro()` inclui os limites informados.

## Formatação

```jls
va texto = math.formatar(matriz)
math.exibir(matriz)
```

## Referência rápida

| Grupo | Funções |
|---|---|
| Constantes | `PI`, `E` |
| Básica | `raiz`, `raizCubica`, `absoluto`, `arredondar`, `teto`, `piso`, `truncar` |
| Trigonometria | `seno`, `cosseno`, `tangente`, `aseno`, `acosseno`, `atangente` |
| Log/exp | `log`, `log10`, `exp` |
| Estatística | `media`, `mediana`, `moda`, `maximo`, `minimo`, `variancia`, `desvioPadrao` |
| Listas | `somaLista`, `produtoLista` |
| Vetores | `vetor`, `somar`, `subtrair`, `normalizar`, `produtoEscalar`, `produtoVetorial`, `distancia` |
| Matrizes | `matriz`, `multiplicar`, `transposta`, `determinante`, `identidade`, `inversa` |
| Aleatórios | `aleatorio`, `inteiro`, `decimal`, `booleano` |
| Ângulos | `radianos`, `graus` |
| Exibição | `formatar`, `exibir` |
