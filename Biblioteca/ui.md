# #ui

A biblioteca nativa **`#ui`** é o sistema de criação de interfaces gráficas do JLScript.

Ela permite criar janelas, definir interfaces utilizando elementos visuais, selecionar dispositivos e plataformas e construir aplicações gráficas diretamente com a sintaxe do JLScript.

A proposta da `#ui` é permitir que interfaces sejam escritas de forma simples e estrutural, sem exigir HTML ou outras linguagens externas.

---

# Importação

```jls
import #ui
```

Como `#ui` normalmente trabalha junto com `#style`, as duas podem ser importadas:

```jls
import [#ui, #style]
```

---

# Criando uma janela

Uma aplicação gráfica começa criando uma janela:

```jls
va app = ui.janela()
```

Também existe a versão em inglês:

```jls
va app = ui.window()
```

A janela será responsável por armazenar a interface, configurações do aplicativo e estilos.

---

# Nome e título

O título da janela pode ser definido com:

```jls
app.titulo("Meu aplicativo")
```

ou:

```jls
app.title("Meu aplicativo")
```

O nome da aplicação pode ser definido separadamente:

```jls
app.nome("Meu App")
```

ou:

```jls
app.name("Meu App")
```

---

# Criando a interface

A interface é definida através de:

```jls
app.ui {
    div {
        text = "Olá, mundo!"
    }
}
```

Os elementos são organizados utilizando blocos `{ }`.

Isso permite representar visualmente a hierarquia da aplicação:

```jls
app.ui {
    div {
        h1("Login")

        form {
            input(
                type = "email",
                placeholder = "Email"
            )

            input(
                type = "password",
                placeholder = "Senha"
            )

            button = "Entrar"
        }
    }
}
```

---

# Elementos disponíveis

A implementação atual da `#ui` possui diversos elementos.

### Estrutura

```text
html
body
div
section
main
header
footer
nav
aside
article
```

### Texto

```text
h1
h2
h3
h4
h5
h6

p
span
label
text
small
strong
b
em
i
u
mark
del
ins
sub
sup
blockquote
pre
code
kbd
samp
```

### Navegação e organização

```text
a
link
br
hr

figure
figcaption

ul
ol
li

dl
dt
dd
```

### Formulários

```text
form
input
textarea
select
option
optgroup
button
checkbox
radio
fieldset
legend
output
```

`btn` também pode ser utilizado como alias de:

```text
button
```

### Componentes

```text
progress
meter
details
summary
dialog

card
row
column
stack
separator
badge
tooltip
loading
switch
```

### Tabelas

```text
table
caption
colgroup
col
thead
tbody
tfoot
tr
th
td
```

---

# Texto e botões

O JLScript permite uma sintaxe curta para `text`:

```jls
text = "Olá!"
```

E para botões:

```jls
button = "Entrar"
```

Também é possível utilizar:

```jls
button("Entrar")
```

---

# Inputs

Inputs utilizam atributos:

```jls
input(
    type = "text",
    placeholder = "Digite seu nome"
)
```

Outro exemplo:

```jls
input(
    type = "email",
    placeholder = "seu@email.com",
    required
)
```

Atributos booleanos não precisam receber `true` explicitamente.

Por exemplo:

```jls
input(
    type = "email",
    required,
    autofocus
)
```

---

# Atributos

A `#ui` possui suporte a atributos comuns de interfaces.

Entre eles:

```text
id
class
style
title

disabled
required
readonly
selected
hidden
multiple
autofocus
checked
open

type
placeholder
value
min
max

role
ariaLabel
ariaDescription
tabIndex
```

Vários possuem versões em português.

Exemplos:

```text
classe
desabilitado
obrigatorio
somenteLeitura
selecionado
oculto
multiplo
focoAutomatico
marcado
espacoReservado
estilo
aberto
valor
minimo
maximo
rotuloAcessivel
descricaoAcessivel
indiceTab
```

---

# Componentes de seleção

## Checkbox

```jls
checkbox(
    checked
)
```

## Radio

```jls
radio(
    checked
)
```

## Switch

Dentro de uma interface, `switch` representa o componente visual:

```jls
switch(
    checked
)
```

Isso é diferente do `switch` utilizado como estrutura de controle da linguagem.

O JLScript reconhece pelo contexto quando `switch` representa código ou um componente de interface.

---

# Select

Um seletor pode ser criado utilizando:

```jls
select {
    option("Brasil")
    option("Argentina")
    option("Chile")
}
```

`select` aceita `option` e `optgroup` como elementos filhos.

---

# Tabelas

A estrutura de tabelas segue uma hierarquia organizada:

```jls
table {
    thead {
        tr {
            th("Nome")
            th("Idade")
        }
    }

    tbody {
        tr {
            td("Lucas")
            td("20")
        }
    }
}
```

O JLScript valida a estrutura.

Por exemplo, um `tr` aceita:

```text
th
td
```

e `thead`, `tbody` e `tfoot` recebem linhas `tr`.

---

# Escolhendo o dispositivo

A janela pode receber um dispositivo:

```jls
app.dispositivo("desktop")
```

ou:

```jls
app.device("desktop")
```

Também é possível configurar propriedades adicionais:

```jls
app.dispositivo(
    "desktop",
    largura = 1280,
    altura = 720
)
```

A API também aceita os nomes em inglês:

```jls
app.device(
    "desktop",
    width = 1280,
    height = 720
)
```

A plataforma pode ser especificada através de:

```text
sistema
system
```

---

# Orientação

A orientação pode ser configurada:

```jls
app.orientacao("portrait")
```

ou:

```jls
app.orientation("portrait")
```

Essa configuração é especialmente útil para interfaces destinadas a dispositivos móveis.

---

# Ícone

O aplicativo pode receber um ícone:

```jls
app.icone("assets/app.ico")
```

ou:

```jls
app.icon("assets/app.ico")
```

---

# Informações da janela

As informações atuais podem ser obtidas com:

```jls
va info = app.informacoes()
```

A versão em inglês é:

```jls
va info = app.info()
```

As informações incluem dados como:

```text
nome
dispositivo
plataforma
orientacao
largura
altura
```

---

# Aplicando estilos

Uma interface pode receber um estilo através de:

```jls
app.style {
    fundo: "#111111"
    cor: "#ffffff"
}
```

O sistema de estilos é fornecido pela biblioteca nativa `#style`.

Por isso, aplicações mais completas normalmente utilizam:

```jls
import [#ui, #style]
```

---

# Abrindo a aplicação

Depois que a interface estiver configurada:

```jls
app.abrir()
```

Também existe:

```jls
app.open()
```

A interface precisa ser definida antes da janela ser aberta.

---

# Exemplo completo

```jls
import [#ui, #style]

va app = ui.janela()

app.nome("JLScript App")
app.titulo("Login")

app.ui {
    main {
        h1("Entrar")

        form {
            input(
                type = "email",
                placeholder = "Email",
                required
            )

            input(
                type = "password",
                placeholder = "Senha",
                required
            )

            button = "Entrar"
        }
    }
}

app.style {
    fundo: "#111111"
    cor: "#ffffff"
    largura: 500px
    altura: 600px
}

app.abrir()
```

---

# Por que usar #ui?

A `#ui` permite construir interfaces utilizando diretamente o JLScript.

A ideia é manter uma estrutura simples:

```text
#ui
 │
 ├── Janela
 │
 ├── Elementos
 │
 ├── Formulários
 │
 ├── Componentes
 │
 ├── Tabelas
 │
 ├── Dispositivos
 │
 └── Renderização
```

A estrutura da interface fica sob responsabilidade da `#ui`.

Sua aparência fica sob responsabilidade da `#style`.

```text
#ui      → o que existe na interface
#style   → como essa interface aparece
```

As duas bibliotecas foram projetadas para trabalhar juntas.