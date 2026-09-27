# #style

A biblioteca nativa **`#style`** é o sistema de estilização de interfaces do JLScript.

Ela trabalha principalmente em conjunto com `#ui` e controla a aparência dos elementos de uma aplicação.

Com ela é possível definir cores, tamanhos, espaçamentos, fontes, layouts, posições, estados, transições, transformações, sombras e comportamento responsivo.

---

# Importação

```jls
import #style
```

Para interfaces:

```jls
import [#ui, #style]
```

---

# Criando um estilo

Um estilo pode ser criado diretamente:

```jls
va estilo = style({
    fundo: "#111111",
    cor: "#ffffff"
})
```

Também existem:

```jls
style.criar({
    fundo: "#111111"
})
```

e:

```jls
style.create({
    background: "#111111"
})
```

---

# Estilo da aplicação

Quando utilizado com `#ui`:

```jls
app.style {
    fundo: "#111111"
    cor: "#ffffff"
    largura: 500px
    altura: 600px
}
```

---

# Dimensões

O sistema suporta propriedades como:

```text
largura
altura

minLargura
maxLargura

minAltura
maxAltura
```

Exemplo:

```jls
app.style {
    largura: 500px
    altura: 700px

    minLargura: 320px
    maxLargura: 1200px
}
```

Também existem aliases em inglês:

```text
width
height
minWidth
maxWidth
minHeight
maxHeight
```

---

# Unidades

O JLScript possui unidades próprias para estilos.

Entre elas:

```text
px
%
vw
vh
rem
em
pt
```

Exemplos:

```jls
largura: 500px
altura: 100vh
tamanhoFonte: 2rem
```

Números sem unidade também podem representar dimensões em pixels quando apropriado.

---

# Cores

As propriedades principais são:

```text
cor
fundo
```

ou:

```text
color
background
```

Exemplo:

```jls
app.style {
    fundo: "#101010"
    cor: "#ffffff"
}
```

Cores podem utilizar valores como nomes, hexadecimal e funções de cor suportadas pelo sistema.

Hexadecimais aceitos incluem formatos como:

```text
#RGB
#RGBA
#RRGGBB
#RRGGBBAA
```

---

# Opacidade

```jls
opacidade: 0.8
```

ou:

```jls
opacity: 0.8
```

O valor deve estar entre:

```text
0
e
1
```

---

# Margem e padding

```jls
margem: 20px
padding: 15px
```

Também existem propriedades individuais:

```text
margemTopo
margemDireita
margemBaixo
margemEsquerda

paddingTopo
paddingDireita
paddingBaixo
paddingEsquerda
```

E seus equivalentes:

```text
marginTop
marginRight
marginBottom
marginLeft

paddingTop
paddingRight
paddingBottom
paddingLeft
```

---

# Bordas

O sistema possui:

```text
borda
bordaCor
bordaLargura
bordaEstilo
raio
```

Exemplo:

```jls
va card = style({
    bordaLargura: 1px,
    bordaCor: "#333333",
    bordaEstilo: "solid",
    raio: 12px
})
```

Aliases incluem:

```text
border
borderColor
borderWidth
borderStyle
borderRadius
```

---

# Fontes e texto

Propriedades disponíveis incluem:

```text
fonte
tamanhoFonte
pesoFonte
alinhamento
decoracao
alturaLinha
espacamentoLetras
```

Equivalentes em inglês:

```text
fontFamily
fontSize
fontWeight
textAlign
textDecoration
lineHeight
letterSpacing
```

---

# Layout

O layout pode ser definido utilizando:

```jls
layout: "flex"
```

ou:

```jls
display: "flex"
```

Valores reconhecidos incluem:

```text
flex
grid
bloco
block
inline
nenhum
none
```

---

# Flex

O sistema possui propriedades como:

```text
flex
direcao
alinhar
justificar
gap
```

Também podem ser utilizadas:

```text
flexDirection
alignItems
justifyContent
```

Exemplo:

```jls
va container = style({
    layout: "flex",
    direcao: "column",
    alinhar: "center",
    justificar: "center",
    gap: 12px
})
```

---

# Grid

O sistema também possui suporte a:

```text
colunas
linhas
```

ou:

```text
gridColumns
gridRows
```

Isso permite definir estruturas de grid para interfaces mais complexas.

---

# Posição

A propriedade:

```text
posicao
```

ou:

```text
position
```

aceita modos como:

```text
estatica
static

relativa
relative

absoluta
absolute

fixa
fixed

sticky
```

Também existem:

```text
topo
direita
baixo
esquerda
zIndex
```

ou:

```text
top
right
bottom
left
zIndex
```

---

# Estados

O JLScript permite definir estilos específicos para estados de um elemento.

Os estados implementados incluem:

```text
hover
foco
ativo
desabilitado
```

Também existem:

```text
focus
active
disabled
```

Isso permite que um elemento altere sua aparência dependendo de sua situação na interface.

---

# Transições

A propriedade:

```text
transicao
```

ou:

```text
transition
```

permite definir animações entre mudanças de estado.

Uma transição pode trabalhar com informações como:

```text
duracao
duration

delay

easing

propriedade
property
```

---

# Transformações

O sistema possui transformações como:

```text
escala
rotacao
moverX
moverY
```

Equivalentes:

```text
scale
rotation
translateX
translateY
```

Exemplo conceitual:

```jls
va botao = style({
    escala: 1.05,
    rotacao: 5deg
})
```

Rotações podem utilizar graus ou radianos.

---

# Sombras

Existem propriedades para sombra do elemento e do texto:

```text
sombra
sombraTexto
```

ou:

```text
boxShadow
textShadow
```

---

# Responsividade

O sistema possui suporte a:

```text
responsivo
```

ou:

```text
responsive
```

Isso permite que estilos sejam adaptados para diferentes condições de exibição.

Esse recurso é especialmente importante quando `#ui` é utilizado com diferentes tamanhos e tipos de dispositivo.

---

# Temas

Um tema pode ser criado através de:

```jls
style.tema({
    fundo: "#101010",
    cor: "#ffffff"
})
```

Também existe:

```jls
style.theme({
    background: "#101010",
    color: "#ffffff"
})
```

Temas são tratados separadamente de estilos comuns.

---

# Juntando estilos

Dois ou mais estilos podem ser combinados:

```jls
va resultado = style.juntar(estilo1, estilo2)
```

ou:

```jls
va resultado = style.merge(estilo1, estilo2)
```

É necessário fornecer pelo menos dois estilos.

Quando propriedades se repetem, o estilo posterior pode substituir o valor anterior.

---

# Classes

Um estilo pode ser registrado para uma classe:

```jls
style.classe("card", {
    fundo: "#181818",
    raio: 12px
})
```

Também existe:

```jls
style.class("card", {
    background: "#181818",
    borderRadius: 12px
})
```

Depois, elementos da `#ui` podem utilizar a classe correspondente.

---

# Estilo por tipo

Também é possível registrar estilos pelo tipo de elemento:

```jls
style.tipo("button", {
    fundo: "#202020",
    cor: "#ffffff"
})
```

ou:

```jls
style.type("button", {
    background: "#202020",
    color: "#ffffff"
})
```

Assim, todos os elementos daquele tipo podem compartilhar uma aparência.

---

# Estilo por ID

Um estilo também pode ser associado a um identificador:

```jls
style.id("login", {
    largura: 400px
})
```

Isso permite estilizar especificamente um elemento identificado na interface.

---

# Consultando um estilo

Objetos de estilo possuem métodos próprios.

Para verificar se uma propriedade existe:

```jls
estilo.tem("fundo")
```

ou:

```jls
estilo.has("fundo")
```

Para obter uma propriedade:

```jls
estilo.obter("fundo")
```

ou:

```jls
estilo.get("fundo")
```

Também é possível converter o estilo novamente para um objeto:

```jls
estilo.objeto()
```

ou:

```jls
estilo.toObject()
```

---

# Validação

O `#style` não aceita qualquer propriedade silenciosamente.

Se uma propriedade desconhecida for utilizada, o JLScript gera um erro.

Além disso, o sistema tenta sugerir propriedades parecidas quando identifica um possível erro de digitação.

Por exemplo, propriedades de dimensão precisam receber valores compatíveis com dimensões.

A opacidade precisa estar entre `0` e `1`.

O `zIndex` precisa ser inteiro.

Dimensões que não podem ser negativas também são verificadas.

Isso ajuda a encontrar erros de estilo antes que eles se transformem naquele clássico ritual de olhar para a tela durante quarenta minutos perguntando por que um botão decidiu morar fora da janela.

---

# #ui + #style

As duas bibliotecas possuem responsabilidades diferentes:

```text
#ui
 │
 └── Estrutura
     ├── janela
     ├── div
     ├── textos
     ├── inputs
     ├── botões
     └── componentes

#style
 │
 └── Aparência
     ├── cores
     ├── tamanhos
     ├── espaçamento
     ├── layout
     ├── estados
     ├── efeitos
     └── responsividade
```

Um exemplo completo:

```jls
import [#ui, #style]

va app = ui.janela()

style.tipo("button", {
    fundo: "#e53935",
    cor: "#ffffff",
    padding: 12px,
    raio: 8px
})

app.titulo("JLScript")

app.ui {
    main {
        h1("JLScript")

        p("Interface criada diretamente em JLScript.")

        button = "Continuar"
    }
}

app.style {
    fundo: "#101010"
    cor: "#ffffff"
    largura: 500px
    altura: 600px
}

app.abrir()
```

---

# Por que usar #style?

A `#style` mantém a aparência separada da estrutura da aplicação.

Enquanto `#ui` determina **o que existe**, `#style` determina **como aquilo será apresentado**.

Isso permite criar interfaces maiores sem misturar toda a lógica visual com a estrutura da aplicação e mantém o sistema de UI do JLScript organizado, reutilizável e extensível.