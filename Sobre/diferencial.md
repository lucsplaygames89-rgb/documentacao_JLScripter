# Diferenciais do JLScript

O **JLScript (JLS)** foi criado com uma proposta simples: tornar a programação mais acessível e agradável sem abandonar recursos necessários para o desenvolvimento de projetos maiores.

A linguagem possui características próprias que fazem parte de sua identidade, principalmente o suporte a **português e inglês**, uma sintaxe pensada para ser fácil de ler e uma integração básica com inteligência artificial através das ferramentas do ecossistema.

---

# Linguagem bilíngue

Um dos principais diferenciais do JLScript é ser uma linguagem **bilíngue**.

A linguagem foi projetada para trabalhar com construções em:

- Português;
- Inglês.

Isso permite que o programador utilize uma sintaxe mais próxima do idioma com o qual se sente confortável.

Em português:

```jls
se (idade >= 18) {
    mostrar("Maior de idade")
} senao {
    mostrar("Menor de idade")
}
```

Em inglês, a linguagem também possui construções equivalentes:

```jls
if (idade >= 18) {
    mostrar("Maior de idade")
} else {
    mostrar("Menor de idade")
}
```

O objetivo não é criar duas linguagens diferentes.

É permitir que **a mesma linguagem possa ser escrita utilizando palavras-chave de idiomas diferentes suportados pelo JLScript**.

---

# Português como parte da linguagem

O JLScript nasceu no Brasil e o português não foi colocado apenas como uma tradução da documentação.

Ele faz parte da própria sintaxe.

Palavras como:

```text
se
senao
enquanto
para
pare
continuar
retorne
```

podem representar conceitos comuns da programação utilizando termos familiares para quem fala português.

Isso ajuda principalmente quem está começando.

Em vez de aprender programação e, ao mesmo tempo, precisar decorar diversas palavras em outro idioma, o programador pode primeiro entender o conceito.

Por exemplo:

```jls
se (usuarioAtivo) {
    mostrar("Bem-vindo")
}
```

A intenção é que a leitura seja próxima da ideia que o código representa.

---

# Português sem abandonar o inglês

Ter uma sintaxe em português não significa isolar o JLScript do restante da programação.

O inglês continua sendo importante no desenvolvimento de software e também faz parte da linguagem.

Por isso, o projeto busca permitir duas experiências:

```text
Quem está começando
        │
        ▼
Pode utilizar português


Quem prefere sintaxe tradicional
        │
        ▼
Pode utilizar inglês
```

Assim, aprender utilizando português não precisa significar ficar preso ao português.

O programador pode compreender primeiro os conceitos e depois se acostumar com as formas equivalentes em inglês.

---

# Sintaxe simples

Outro objetivo do JLScript é reduzir sintaxe desnecessária quando a própria estrutura do código já consegue expressar claramente a intenção.

Um exemplo aparece no `switch`.

Em JLScript:

```jls
switch (opcao) {
    case 1 {
        mostrar("Iniciar")
    }

    case 2 {
        mostrar("Configurações")
    }

    default {
        mostrar("Sair")
    }
}
```

Cada `case` possui seu próprio bloco.

Por isso, não é necessário adicionar:

```text
break
```

apenas para indicar que aquele caso terminou.

O fechamento:

```text
}
```

já delimita o bloco.

A ideia é simples:

> Se o código já deixa claro onde uma estrutura termina, não é necessário adicionar outra instrução apenas para repetir essa informação.

---

# Fácil de ler

O JLScript busca manter o código visualmente simples.

Um programa pode ser entendido observando diretamente sua estrutura:

```jls
va nome = "Lucas"

se (nome == "Lucas") {
    mostrar("Olá, " + nome)
}
```

É possível identificar rapidamente:

```text
va
│
└── cria uma variável

se
│
└── verifica uma condição

mostrar
│
└── apresenta uma informação
```

Isso faz parte da proposta didática da linguagem.

O objetivo não é remover conceitos importantes da programação.

É apresentá-los de uma maneira mais direta.

---

# Fácil para começar, capaz de crescer

Uma linguagem fácil não precisa servir apenas para exemplos pequenos.

O JLScript começou com estruturas básicas, mas seu projeto evoluiu para possuir componentes como:

```text
JLScript
│
├── Lexer
├── Parser
├── AST
├── Interpretador
├── Runtime
├── Compilação
├── Bytecode
├── CLI
├── Bibliotecas
└── Ferramentas
```

Assim, existem duas ideias trabalhando juntas:

```text
Sintaxe simples
      +
Arquitetura crescente
      │
      ▼
   JLScript
```

A intenção é facilitar a entrada sem impedir que o ecossistema evolua.

---

# Bibliotecas nativas

Funcionalidades específicas podem ser organizadas através das bibliotecas do JLScript.

Uma biblioteca pode ser importada assim:

```jls
import #api
```

E várias podem ser importadas juntas:

```jls
import [#api, #database, #json]
```

Isso ajuda a manter o código organizado e evita colocar todas as funcionalidades diretamente no núcleo da linguagem.

O programador importa aquilo que precisa utilizar.

---

# Terminal próprio

O JLScript também possui seu próprio CLI.

```bash
jls
```

Em vez de o projeto ser apenas uma sintaxe executada por uma ferramenta separada, o ecossistema possui comandos próprios para diferentes tarefas.

Por exemplo:

```bash
jls run app.jls
```

para executar um programa.

Também existem ferramentas do ecossistema para tarefas como build, testes, formatação, análise, diagnóstico e desenvolvimento.

Isso permite que o programador trabalhe com diferentes partes do projeto através de uma interface comum.

---

# Suporte básico com inteligência artificial

O JLScript também explora integração com **inteligência artificial**.

O objetivo dessa integração não é substituir o programador nem transformar a linguagem inteira em uma IA.

A proposta é utilizar IA como uma ferramenta auxiliar dentro do ecossistema.

O CLI possui uma área dedicada:

```bash
jls ai
```

A integração pode ser utilizada para experiências de assistência relacionadas ao desenvolvimento e compreensão de problemas dentro do ambiente JLScript.

---

# IA para ajudar, não esconder

Um dos objetivos de uma linguagem didática é permitir que o programador compreenda o que está acontecendo.

Por isso, o suporte de IA não deve simplesmente esconder erros ou produzir código sem explicação.

A ideia é que a assistência possa ajudar em situações como:

```text
Erro
  │
  ▼
JLScript identifica o problema
  │
  ▼
Assistência de IA
  │
  ▼
Explicação mais compreensível
```

Em vez de apenas receber:

```text
Erro
```

o programador pode receber contexto que o ajude a entender:

```text
O que aconteceu?
Por que aconteceu?
Onde aconteceu?
O que pode ser verificado?
```

Esse suporte continua sendo uma área em evolução dentro do projeto.

---

# IA básica por escolha

A integração de IA é tratada como **assistência**, e não como requisito para utilizar a linguagem.

O JLScript continua sendo uma linguagem de programação independente dessa camada.

```text
JLScript
│
├── Linguagem
├── Runtime
├── Compilação
├── Bibliotecas
├── CLI
│
└── Assistência de IA
```

Isso significa que a IA complementa as ferramentas do ecossistema em vez de definir como a linguagem funciona.

---

# Aprender os conceitos primeiro

Uma das ideias por trás do JLScript é diminuir algumas barreiras iniciais da programação.

Um iniciante precisa aprender conceitos como:

```text
variáveis
condições
funções
loops
tipos
escopo
erros
bibliotecas
```

Esses conceitos já exigem bastante raciocínio.

Se a linguagem puder apresentar parte deles utilizando palavras familiares, o estudante pode concentrar mais atenção no conceito.

Por exemplo:

```jls
enquanto (contador < 10) {
    contador = contador + 1
}
```

Mesmo antes de conhecer todos os detalhes da implementação, a intenção do código é relativamente fácil de perceber para alguém que fala português.

---

# Identidade brasileira

O português não é apenas uma funcionalidade.

Também representa a origem do projeto.

O JLScript foi criado no Brasil e não tenta esconder essa identidade.

```text
Origem
  │
  ▼
Brasil 🇧🇷
  │
  ▼
Português + Inglês
  │
  ▼
JLScript
```

A linguagem pode crescer internacionalmente sem abandonar sua origem.

---

# Resumo dos diferenciais

| Diferencial | Proposta |
|---|---|
| Linguagem bilíngue | Sintaxe com construções em português e inglês |
| Português nativo | Português faz parte da linguagem, não apenas da documentação |
| Sintaxe simples | Reduzir elementos desnecessários quando a estrutura já é clara |
| Fácil leitura | Código pensado para ser compreendido visualmente |
| Entrada amigável | Facilitar o primeiro contato com conceitos de programação |
| Inglês disponível | Permitir uma sintaxe mais próxima de linguagens internacionais |
| `switch` sem `break` obrigatório por caso | O bloco `{ }` delimita cada `case` |
| Bibliotecas nativas | Recursos especializados separados do núcleo |
| CLI próprio | Ferramentas acessadas pelo comando `jls` |
| IA básica | Assistência integrada ao ecossistema |
| Identidade brasileira | Projeto criado no Brasil com português como parte de sua identidade |

---

# A proposta

O JLScript não tenta tornar programação algo sem lógica ou sem conceitos técnicos.

Programar continua exigindo aprender.

A proposta é remover algumas dificuldades que não precisam existir.

```text
Menos barreiras desnecessárias
            +
Conceitos reais de programação
            +
Português e inglês
            +
Ferramentas próprias
            +
Assistência básica de IA
            │
            ▼
         JLScript
```

A linguagem foi criada para ser fácil de começar, agradável de escrever e capaz de continuar crescendo junto com quem a utiliza.

---

<div align="center">

## JLScript

**Português + Inglês • Sintaxe simples • Ferramentas próprias • Assistência de IA**

Uma linguagem de programação brasileira 🇧🇷

</div>
