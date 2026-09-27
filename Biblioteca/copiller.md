# #compiler

A biblioteca nativa **`#compiler`** é o kit de desenvolvimento de linguagens do JLScript.

Ela permite utilizar o próprio JLScript para definir características de uma nova linguagem de programação, incluindo:

- nome;
- extensão;
- versão;
- tipagem;
- modelo de execução;
- recursos;
- palavras-chave;
- operadores;
- comentários;
- delimitadores de strings.

A biblioteca também possui ferramentas para analisar código e consultar quais recursos do sistema de criação de linguagens já estão disponíveis.

> **Estado atual:** o `#compiler` ainda é experimental e possui recursos em diferentes estágios de implementação.

---

# Importação

```jls
import #compiler
```

Também existe o nome em português:

```jls
import #compilador
```

O módulo carregado é o mesmo.

---

# Para que serve?

Enquanto bibliotecas como `#api` ou `#database` ajudam a construir aplicações, `#compiler` possui outro objetivo:

> **permitir construir linguagens.**

A arquitetura atual funciona assim:

```text
JLScript
   │
   ▼
#compiler
   │
   ▼
Definição da linguagem
   │
   ├── sintaxe
   ├── palavras-chave
   ├── operadores
   ├── recursos
   └── configuração
           │
           ▼
      lang.build()
           │
           ▼
       arquivo .jlc
           │
           ▼
   Language Development Kit
```

O arquivo `.jlc` contém a definição construída da linguagem.

---

# Criando uma linguagem

A maneira mais simples é:

```jls
import #compiler

va lang = compiler.language("MinhaLang")
```

Em português:

```jls
va lang = compiler.linguagem("MinhaLang")
```

Isso cria um objeto de configuração da nova linguagem.

---

# Criando com configuração

Também existe:

```jls
compiler.create({...})
```

ou:

```jls
compiler.criar({...})
```

Exemplo:

```jls
va lang = compiler.create({
    name: "MinhaLang",
    extension: ".ml",
    typing: "dynamic",
    execution: "bytecode"
})
```

Também são reconhecidos alguns nomes em português na configuração, como:

```jls
va lang = compiler.criar({
    nome: "MinhaLang",
    extensao: ".ml"
})
```

---

# Configurações iniciais

Ao utilizar `compiler.create()`, a definição pode conter:

```text
name
nome

extension
extensao

syntax

typing

execution

features
```

Algumas configurações possuem valores padrão.

---

# Nome

O nome identifica a linguagem:

```jls
va lang = compiler.language("MinhaLang")
```

O objeto possui:

```jls
lang.name
```

e:

```jls
lang.nome
```

para consultar o nome.

---

# Extensão

A extensão pode ser configurada utilizando:

```jls
lang.extension(".ml")
```

ou:

```jls
lang.extensao(".ml")
```

A extensão precisa começar com:

```text
.
```

Por exemplo:

```text
.ml
```

é válido.

---

# Versão

Por padrão, uma nova linguagem utiliza:

```text
0.1.0
```

Ela pode ser alterada:

```jls
lang.version("1.0.0")
```

ou:

```jls
lang.versao("1.0.0")
```

---

# Tipagem

A tipagem é configurada através de:

```jls
lang.typing("dynamic")
```

ou:

```jls
lang.tipagem("dynamic")
```

Na implementação atual, somente:

```text
dynamic
```

está pronto para construção e execução.

Outros modelos de tipagem ainda não estão disponíveis nesse estágio.

---

# Modelo de execução

Pode ser definido com:

```jls
lang.execution("bytecode")
```

ou:

```jls
lang.execucao("bytecode")
```

Atualmente, o backend disponível para linguagens criadas pelo LDK é:

```text
bytecode
```

---

# Sintaxe atual

O sistema possui internamente uma configuração de sintaxe.

Atualmente, somente:

```text
brace
```

está pronta.

Isso significa que blocos utilizam:

```text
{
    ...
}
```

Por exemplo:

```text
if condição {
    ...
}
```

Outros estilos de sintaxe ainda não estão prontos no backend atual.

---

# Recursos da linguagem

Recursos podem ser adicionados utilizando:

```jls
lang.feature("variables")
```

ou:

```jls
lang.recurso("variables")
```

O método retorna o estado atual daquele recurso.

Os estados possíveis são:

```text
READY
PARTIAL
PLANNED
```

---

# Recursos atualmente READY

No código atual, os seguintes recursos estão marcados como:

```text
READY
```

São eles:

```text
variables
expressions
conditions
functions
```

Portanto, atualmente o sistema de linguagens possui suporte pronto para:

```text
variáveis
expressões
condições
funções
```

---

# Recursos planejados

A matriz atual também conhece recursos como:

```text
constants
loops
arrays
maps
objects
classes
interfaces
enums
generics
exceptions
modules
async
lambda
patternMatching
```

Porém, no estado atual eles são classificados como:

```text
PLANNED
```

Um recurso `PLANNED` ainda não pode ser utilizado como recurso pronto de uma linguagem construída.

---

# Consultando o estado de um recurso

No módulo:

```jls
va estado = compiler.featureStatus("variables")

mostrar(estado)
```

Resultado:

```text
READY
```

Também é possível consultar através do objeto da linguagem:

```jls
va estado = lang.featureStatus("functions")
```

ou:

```jls
va estado = lang.estadoRecurso("functions")
```

---

# Personalizando variáveis

O recurso `variables` aceita uma configuração especial com palavras-chave.

Por exemplo:

```jls
lang.feature(
    "variables",
    {
        keywords: ["var", "make"]
    }
)
```

Isso define quais palavras podem representar uma declaração de variável naquela linguagem.

---

# Personalizando funções

O recurso `functions` também pode receber uma palavra-chave:

```jls
lang.feature(
    "functions",
    {
        keyword: "func"
    }
)
```

---

# Palavras-chave

Palavras-chave podem ser configuradas individualmente:

```jls
lang.keyword("if")
```

Também é possível adicionar um alias:

```jls
lang.keyword(
    "if",
    alias = "se"
)
```

Assim, uma palavra canônica pode possuir outra representação dentro da linguagem.

Existe também:

```jls
lang.palavraChave(...)
```

como versão em português do método.

---

# Palavras-chave padrão

Quando nenhuma configuração própria é fornecida, o sistema atual possui alguns padrões:

```text
variable → var, make

print → print, show

if → if

else → else

function → func

return → return
```

Essas palavras formam a base inicial da linguagem criada.

---

# Operadores

Operadores podem ser definidos através de:

```jls
lang.operator("+")
```

ou:

```jls
lang.operador("+")
```

Também podem receber configurações.

Exemplo:

```jls
lang.operator(
    "+",
    type = "binary",
    precedence = 10,
    associativity = "left"
)
```

Em português também são reconhecidos:

```text
tipo
precedencia
associatividade
```

---

# Precedência

A precedência determina qual operação acontece primeiro.

Por exemplo:

```text
2 + 3 * 4
```

O operador `*` possui precedência maior que `+`.

Na configuração padrão:

```text
==  → 5
!=  → 5

<   → 6
<=  → 6
>   → 6
>=  → 6

+   → 10
-   → 10

*   → 20
/   → 20
```

---

# Associatividade

Operadores também possuem associatividade.

O valor padrão é:

```text
left
```

Ela pode ser configurada através de:

```jls
associativity = "left"
```

ou:

```jls
associatividade = "left"
```

---

# Operadores atualmente suportados

O backend atual possui bytecode para:

```text
+
-
*
/

==
!=

<
<=
>
>=
```

Tentar construir uma linguagem com um operador que ainda não possui suporte no backend gera erro.

---

# Comentários

O comentário de linha pode ser configurado:

```jls
lang.comments({
    line: "//"
})
```

Também existe:

```jls
lang.comentarios({
    line: "//"
})
```

Por padrão:

```text
//
```

é utilizado.

---

# Strings

Os delimitadores de texto podem ser definidos:

```jls
lang.strings([
    "\"",
    "'"
])
```

Por padrão, a linguagem aceita:

```text
"
'
```

como delimitadores.

---

# Construindo a linguagem

Depois que a configuração estiver pronta:

```jls
va caminho = lang.build()
```

ou:

```jls
va caminho = lang.construir()
```

Nenhum dos dois métodos recebe argumentos.

O sistema valida a definição e cria um arquivo:

```text
.jlc
```

---

# Onde a linguagem é armazenada?

A definição construída é salva dentro de:

```text
.jls-languages/
```

Por exemplo, uma linguagem chamada:

```text
MinhaLang
```

gera:

```text
.jls-languages/
└── MinhaLang.jlc
```

O caminho do arquivo criado é retornado por:

```jls
lang.build()
```

---

# Estado da linguagem

O objeto possui:

```jls
lang.status
```

Antes da construção:

```text
CONFIGURING
```

Depois de:

```jls
lang.build()
```

o estado passa para:

```text
BUILT
```

---

# Tokenização

`#compiler` também permite utilizar o lexer do JLScript para analisar código.

```jls
va tokens = compiler.tokenize(source)
```

O método recebe exatamente um texto.

Por exemplo:

```jls
import #compiler

va source = "va nome = \"Lucas\""

va tokens = compiler.tokenize(source)

mostrar(tokens)
```

---

# Estrutura de um token

Cada token retornado contém:

```text
type
value
file
line
column
start
end
```

Isso fornece informações sobre o tipo do token, seu conteúdo e sua posição no código.

Conceitualmente:

```text
{
    type: "...",
    value: "...",
    file: "<memory>",
    line: 1,
    column: 1,
    start: 0,
    end: 2
}
```

Como `tokenize()` trabalha diretamente com texto em memória:

```text
file = "<memory>"
```

é utilizado.

---

# Ferramentas do terminal

As definições criadas pelo `#compiler` também podem ser utilizadas pelo terminal do JLScript.

## Executar uma linguagem

```text
jls language run <Linguagem> <arquivo>
```

Exemplo:

```text
jls language run MinhaLang programa.ml
```

O JLScript procura a definição construída da linguagem e executa o arquivo utilizando seu backend.

---

# Inspecionar tokens

Também é possível analisar a tokenização:

```text
jls language inspect <Linguagem> <arquivo> --tokens
```

Isso mostra informações como:

```text
linha:coluna
tipo
valor
```

e é útil durante o desenvolvimento de uma linguagem.

---

# Verificar uma linguagem

Para validar uma definição:

```text
jls language doctor <Linguagem>
```

O comando verifica se a linguagem utiliza somente recursos disponíveis no backend atual.

---

# Validação

`lang.build()` não simplesmente grava qualquer configuração.

Antes da construção, o sistema verifica a definição.

Entre as regras atuais:

```text
nome não pode estar vazio

extensão deve começar com "."

syntax precisa ser "brace"

typing precisa ser "dynamic"

execution precisa ser "bytecode"

features precisam estar READY

operadores precisam possuir suporte
```

Isso impede que uma linguagem seja marcada como construída utilizando recursos que o runtime ainda não sabe executar.

---

# Erros do LDK

O sistema possui erros próprios para problemas na construção e utilização de linguagens.

Entre eles estão:

```text
JL901
```

A linguagem solicitada ainda não foi construída.

```text
JL902
```

Problemas básicos na definição, como nome ou extensão inválida.

```text
JL903
```

Tentativa de utilizar um modelo de sintaxe, tipagem ou execução ainda não disponível.

```text
JL904
```

Tentativa de construir utilizando uma feature que ainda não está `READY`.

```text
JL905
```

Problema na definição ou suporte de um operador.

```text
JL906
```

Falha ao criar ou gravar a definição `.jlc`.

```text
JL907
```

Arquivo de definição de linguagem inválido.

---

# Métodos do módulo

| Método | Função |
|---|---|
| `compiler.create()` | Cria uma linguagem através de configuração |
| `compiler.criar()` | Alias de `create()` |
| `compiler.language()` | Cria uma nova definição pelo nome |
| `compiler.linguagem()` | Alias de `language()` |
| `compiler.tokenize()` | Tokeniza código JLScript |
| `compiler.featureStatus()` | Consulta o estado de uma feature |

---

# Métodos da linguagem

| Inglês | Português | Função |
|---|---|---|
| `extension()` | `extensao()` | Define a extensão |
| `version()` | `versao()` | Define a versão |
| `typing()` | `tipagem()` | Define a tipagem |
| `execution()` | `execucao()` | Define o backend de execução |
| `feature()` | `recurso()` | Adiciona um recurso |
| `keyword()` | `palavraChave()` | Define uma palavra-chave |
| `operator()` | `operador()` | Define um operador |
| `comments()` | `comentarios()` | Configura comentários |
| `strings()` | `strings()` | Configura delimitadores de strings |
| `featureStatus()` | `estadoRecurso()` | Consulta uma feature |
| `build()` | `construir()` | Valida e constrói a linguagem |

---

# Exemplo completo

```jls
import #compiler

va lang = compiler.language("MinhaLang")

lang.extensao(".ml")
lang.versao("1.0.0")

lang.tipagem("dynamic")
lang.execucao("bytecode")

lang.recurso(
    "variables",
    {
        keywords: ["var", "make"]
    }
)

lang.recurso("expressions")
lang.recurso("conditions")

lang.recurso(
    "functions",
    {
        keyword: "func"
    }
)

lang.palavraChave(
    "if",
    alias = "se"
)

lang.operador(
    "+",
    tipo = "binary",
    precedencia = 10,
    associatividade = "left"
)

lang.comentarios({
    line: "//"
})

lang.strings([
    "\"",
    "'"
])

va arquivo = lang.construir()

mostrar(arquivo)
```

Depois da construção:

```text
.jls-languages/
└── MinhaLang.jlc
```

A linguagem pode então ser utilizada pelas ferramentas:

```text
jls language run
jls language inspect
jls language doctor
```

---

# Estado atual do #compiler

O `#compiler` faz parte do processo de tornar o JLScript capaz de participar da construção de outras linguagens e, futuramente, de partes cada vez maiores do próprio ecossistema.

No estado atual:

```text
Language Development Kit
        │
        ├── definição de linguagem      READY
        ├── lexer/tokenização           READY
        ├── variáveis                   READY
        ├── expressões                  READY
        ├── condições                   READY
        ├── funções                     READY
        ├── backend bytecode            READY
        │
        └── recursos avançados          PLANNED
```

O próprio terminal atualmente identifica o **`#compiler LDK` como `PARTIAL`**, porque o sistema completo de desenvolvimento de linguagens ainda está em evolução.

---

# Por que usar #compiler?

`#compiler` transforma o JLScript de uma linguagem que apenas executa programas em uma linguagem que também pode ser utilizada para **experimentar e desenvolver outras linguagens**.

Em vez de começar diretamente implementando lexer, parser, operadores, bytecode e ferramentas do zero em C++, o objetivo do LDK é fornecer uma camada de desenvolvimento:

```text
Criador
   │
   ▼
JLScript
   │
   ▼
#compiler
   │
   ▼
Definição da linguagem
   │
   ▼
.jlc
   │
   ▼
Runtime / Bytecode
```

A implementação atual ainda representa uma primeira fase desse sistema, mas já permite definir, validar, construir, inspecionar e executar linguagens pequenas utilizando a infraestrutura do JLScript.