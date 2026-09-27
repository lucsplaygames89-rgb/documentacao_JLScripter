# História do JLScript

> A história de uma linguagem de programação brasileira que começou pequena, nasceu da curiosidade e foi crescendo junto com seu criador.

## Índice

- [Origem](#origem)
- [Por que criar uma linguagem?](#por-que-criar-uma-linguagem)
- [Uma linguagem brasileira](#uma-linguagem-brasileira)
- [O nome JLScript](#o-nome-jlscript)
- [JLScripter](#jlscripter)
- [A primeira versão](#a-primeira-versão)
- [JLScript 1.0.0](#jlscript-100)
- [O primeiro terminal](#o-primeiro-terminal)
- [A evolução](#a-evolução)
- [As bibliotecas nativas](#as-bibliotecas-nativas)
- [O crescimento do terminal](#o-crescimento-do-terminal)
- [Compilação e bytecode](#compilação-e-bytecode)
- [Uma linguagem que começou a criar um ecossistema](#uma-linguagem-que-começou-a-criar-um-ecossistema)
- [O que diferencia o JLScript](#o-que-diferencia-o-jlscript)
- [Quem criou](#quem-criou)
- [O futuro](#o-futuro)

---

# Origem

O **JLScript (JLS)** nasceu em **2026**, no Brasil, como um projeto criado por **Lucas Aguiel Dos Santos De Oliveira**.

A linguagem começou a ser desenvolvida a partir de uma ideia simples: criar algo próprio.

Não apenas um programa feito utilizando uma linguagem existente, mas a própria linguagem que receberia o código, entenderia sua estrutura e decidiria como executá-lo.

O projeto começou como uma experiência pessoal e educacional, mas rapidamente ganhou proporções maiores.

No início, a pergunta era:

> É possível criar minha própria linguagem de programação?

Depois que os primeiros programas começaram a funcionar, a pergunta mudou:

> Até onde essa linguagem pode chegar?

Foi dessa segunda pergunta que o JLScript começou a crescer.

---

# Por que criar uma linguagem?

O JLScript nasceu da vontade de criar uma linguagem que fosse **divertida de desenvolver, simples de utilizar e capaz de se tornar um projeto sério**.

Lucas já tinha contato com programação e gostava de características encontradas em linguagens diferentes.

Python mostrava como uma linguagem poderia possuir uma escrita relativamente simples.

JavaScript apresentava uma sintaxe familiar e um ecossistema extremamente flexível.

Ao mesmo tempo, existiam escolhas nessas e em outras linguagens que Lucas gostaria de experimentar de outra maneira.

Em vez de apenas imaginar como seria uma linguagem diferente, começou a construir uma.

A ideia não era criar uma cópia de Python ou JavaScript.

Era aprender com linguagens existentes e, ao mesmo tempo, tomar decisões próprias.

```text
Outras linguagens
       │
       ▼
Experiência e aprendizado
       │
       ▼
Ideias próprias
       │
       ▼
    JLScript
```

---

# Uma linguagem brasileira

O JLScript é originalmente brasileiro.

Ele foi criado no Brasil por um programador brasileiro e o português faz parte de sua identidade.

A linguagem começou a explorar construções em português sem abandonar formas equivalentes em inglês.

Por exemplo:

```jls
se (ativo) {
    mostrar("Sistema ativo")
} senao {
    mostrar("Sistema desativado")
}
```

A intenção não é simplesmente traduzir palavras.

A proposta é permitir que alguém possa aprender e escrever código de maneira mais próxima de sua própria língua quando desejar.

Ao mesmo tempo, o projeto mantém espaço para uma sintaxe internacional.

```text
Português + Inglês
        │
        ▼
     JLScript
```

Ter origem brasileira não significa limitar o projeto ao Brasil.

Significa apenas que ele não precisa esconder de onde veio para poder crescer.

---

# O nome JLScript

O nome **JLScript** também possui uma história pessoal.

Ele pode ser dividido assim:

```text
J       → Joicy
L       → Lucas
Script  → Programação
```

O **J** representa **Joicy Costa**.

O **L** representa **Lucas Aguiel Dos Santos De Oliveira**.

E **Script** representa a programação.

Portanto:

```text
J + L + Script
      │
      ▼
   JLScript
```

O `J` não significa Java.

Também não significa JavaScript.

A semelhança existe apenas porque `Script` naturalmente lembra linguagens de script.

A origem oficial do nome é pessoal.

---

## Por que Joicy está no nome?

Joicy não desenvolveu tecnicamente o JLScript.

Ela não criou o lexer, parser, runtime, sintaxe ou bibliotecas da linguagem.

Sua presença no nome possui outro significado.

Ela representa uma pessoa importante na vida de Lucas.

Os dois possuem objetivos profissionais diferentes.

Lucas deseja seguir seu caminho principalmente através da tecnologia, programação e segurança cibernética.

Joicy possui seus próprios sonhos e interesses.

Eles não precisam construir a mesma carreira para fazer parte da história um do outro.

Por isso, Lucas decidiu guardar uma parte dessa história no nome de seu projeto.

```text
Joicy                    Lucas
  │                         │
  J            +            L
               │
               ▼
             JL
               +
            Script
               │
               ▼
           JLScript
```

O projeto é desenvolvido por Lucas.

O nome carrega os dois.

---

# JLScripter

Com o crescimento da linguagem, o nome **JLScripter** passou a representar uma identidade maior ao redor do projeto.

De maneira simples:

```text
JLScript
   │
   └── linguagem de programação


JLScripter
   │
   └── projeto e ecossistema
```

O nome começou a aparecer associado não apenas à sintaxe da linguagem, mas também às ferramentas construídas ao redor dela.

```text
JLScripter
│
├── JLScript
├── Runtime
├── Compiladores
├── Bytecode
├── CLI
├── Bibliotecas
├── Ferramentas
└── Documentação
```

A abreviação da linguagem tornou-se:

```text
JLS
```

E seus arquivos utilizam:

```text
.jls
```

Assim, a identidade original passou a aparecer em diferentes partes do projeto.

---

# A primeira versão

A primeira versão oficial foi o **JLScript 1.0.0**.

Ela era muito menor que o projeto atual.

Naquele momento, o objetivo principal ainda era fazer a linguagem funcionar.

Entre os recursos existentes estavam:

- `if`;
- `else`;
- funções;
- `switch`;
- `for`;
- loops;
- execução de programas;
- um CLI inicial.

Não existia todo o sistema atual de bibliotecas.

Não existiam todas as ferramentas atuais.

O terminal também fazia muito menos.

Mas havia algo mais importante:

**a linguagem já conseguia executar código.**

---

# JLScript 1.0.0

Uma representação simplificada daquela fase seria:

```text
JLScript 1.0.0
│
├── Condições
│   ├── if
│   └── else
│
├── Funções
│
├── switch
│
├── for
│
├── loops
│
└── CLI
    └── poucos comandos
```

Comparado ao que viria depois, era pequeno.

Mas a versão 1.0.0 provou que a ideia poderia deixar de ser apenas uma ideia.

---

# O primeiro terminal

Desde cedo, o JLScript já possuía uma ferramenta de linha de comando.

O terminal era muito mais simples que o atual.

Um dos comandos básicos era:

```bash
jls version
```

Naquela fase, o comando `jls` ainda não controlava um grande conjunto de ferramentas.

Mesmo assim, uma decisão importante já estava presente:

> O JLScript teria seu próprio CLI.

O terminal cresceria junto com a linguagem.

---

# A evolução

Depois da primeira versão, o projeto começou a mudar rapidamente.

A estrutura inicial:

```text
Código
  │
  ▼
Execução
```

começou a se transformar em algo muito maior:

```text
Código .jls
    │
    ▼
  Lexer
    │
    ▼
 Parser
    │
    ▼
   AST
    │
    ▼
Interpretador
    │
    ▼
 Runtime
```

Com o tempo, outras áreas foram surgindo.

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
├── Módulos
├── Bibliotecas
└── Ferramentas
```

A linguagem deixou de ser apenas um experimento de sintaxe.

Começou a possuir uma arquitetura própria.

---

# As bibliotecas nativas

Uma das maiores mudanças foi o surgimento das bibliotecas nativas.

Na primeira versão, não existia o sistema atual de importações como:

```jls
import #api
```

ou:

```jls
import [#api, #database]
```

Conforme novas funcionalidades surgiram, ficou cada vez menos interessante colocar tudo diretamente no núcleo.

Bibliotecas passaram a separar responsabilidades.

```text
JLScript
│
├── Núcleo
│
├── Runtime
│
├── CLI
│
└── Bibliotecas
    ├── #api
    ├── #database
    ├── #json
    ├── #ui
    ├── #style
    ├── #mobile
    ├── #connector
    └── #compiler
```

Isso permitiu que o projeto explorasse áreas diferentes sem transformar cada funcionalidade em parte obrigatória da sintaxe central.

---

# O crescimento do terminal

Talvez uma das maneiras mais fáceis de enxergar a evolução do JLScript seja olhar para seu terminal.

No começo:

```text
jls
│
└── poucos comandos
```

Depois, o CLI começou a receber ferramentas para diferentes etapas do desenvolvimento.

Entre elas estão áreas como:

```text
jls
│
├── run
├── repl
├── build
├── compile
├── test
├── fmt
├── lint
├── fix
├── doctor
├── config
├── update
└── dev
```

O terminal deixou de servir apenas para iniciar um programa.

Passou a participar do desenvolvimento, compilação, análise, testes, diagnóstico e manutenção do ambiente.

## Execução

```bash
jls run app.jls
```

## REPL

```bash
jls repl
```

## Build

```bash
jls build app.jls
```

## Bytecode

```bash
jls compile app.jls
```

## Testes

```bash
jls test
```

## Formatação e análise

```bash
jls fmt
jls lint
jls fix
```

## Diagnóstico

```bash
jls doctor
```

## Atualização

```bash
jls update
```

## Desenvolvimento

```bash
jls dev
```

O pequeno CLI da versão 1.0.0 começou a se transformar em uma das principais interfaces do ecossistema.

---

# Compilação e bytecode

O JLScript também deixou de depender exclusivamente da execução interpretada.

O projeto começou a explorar caminhos de compilação.

Um deles envolve geração de C++ para construção nativa:

```text
Código JLScript
      │
      ▼
     AST
      │
      ▼
 Geração C++
      │
      ▼
Compilador C++
      │
      ▼
  Executável
```

Outro caminho envolve bytecode próprio:

```text
Código .jls
     │
     ▼
Compilador
     │
     ▼
Bytecode .jlb
```

Isso representou uma mudança importante.

A pergunta já não era apenas:

> Como executar JLScript?

Passou a ser também:

> De quantas formas JLScript pode ser executado ou transformado?

---

# Uma linguagem que começou a criar um ecossistema

O crescimento do projeto fez com que o JLScript começasse a ultrapassar a definição de um simples interpretador.

```text
                     JLScript
                        │
          ┌─────────────┼─────────────┐
          │             │             │
      Linguagem      Execução      Ferramentas
          │             │             │
        Lexer       Runtime          CLI
        Parser      Bytecode         Testes
         AST        Build            Lint
                                   Formatter
                                   Doctor
```

Depois vieram bibliotecas e outras áreas:

```text
                     JLScripter
                         │
        ┌────────────────┼────────────────┐
        │                │                │
     JLScript        Bibliotecas      Ferramentas
        │                │                │
     Runtime           #api              CLI
     Parser            #json             Testes
     Lexer             #ui               Build
     AST               #style            Doctor
                       #mobile            Dev
                       #connector
                       #compiler
```

O projeto começou como uma linguagem.

Depois começou a construir tudo ao redor dela.

---

# O que diferencia o JLScript

O objetivo do JLScript não é ser diferente apenas por ser diferente.

Algumas decisões surgiram porque Lucas acreditava que determinadas estruturas poderiam ser mais diretas.

## Switch sem `break`

Um exemplo é o `switch`.

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

Não é necessário adicionar:

```text
break
```

ao final de cada `case`.

O próprio fechamento:

```text
}
```

já informa onde aquele bloco termina.

A ideia é simples:

> Se a estrutura já deixa clara a intenção, não é necessário escrever outra instrução apenas para repetir essa informação.

---

## Português e inglês

Outra característica é a possibilidade de trabalhar com construções em português e inglês.

```jls
se (condicao) {
    mostrar("Português")
} senao {
    mostrar("Outro caminho")
}
```

A linguagem nasceu no Brasil e não tenta esconder isso.

Ao mesmo tempo, sua arquitetura não precisa ficar presa a um único idioma.

---

## Importações

As bibliotecas nativas utilizam uma identidade visual própria:

```jls
import #api
```

E múltiplas bibliotecas podem ser importadas juntas:

```jls
import [#api, #database, #json]
```

O `#` ajuda a distinguir visualmente bibliotecas pertencentes ao ecossistema.

---

# Quem criou

O JLScript foi criado por **Lucas Aguiel Dos Santos De Oliveira**.

Lucas é brasileiro, estudante de tecnologia e desenvolvedor interessado principalmente em:

- programação;
- desenvolvimento de software;
- linguagens de programação;
- segurança cibernética;
- arquitetura de sistemas;
- inteligência artificial;
- ferramentas para desenvolvedores.

Grande parte de seu aprendizado acontece construindo.

O processo costuma seguir uma lógica simples:

```text
Ideia
  ↓
Tentar construir
  ↓
Encontrar um problema
  ↓
Aprender
  ↓
Resolver
  ↓
Continuar
```

Foi dessa maneira que um projeto inicialmente pequeno começou a exigir conhecimentos sobre lexer, parser, AST, interpretadores, runtime, compiladores, bytecode, terminal, rede, bibliotecas e outras áreas.

O crescimento do JLScript também acompanha o crescimento técnico de seu criador.

---

# De `jls version` para um ecossistema

Talvez essa seja a comparação que melhor resume a história.

No começo, havia um pequeno terminal onde algo como:

```bash
jls version
```

já representava parte importante do projeto.

Depois, o mesmo comando principal passou a abrir caminho para execução, REPL, build, bytecode, testes, análise, diagnóstico, atualização e desenvolvimento.

```text
ANTES

jls
└── poucos comandos


DEPOIS

jls
├── run
├── repl
├── build
├── compile
├── test
├── fmt
├── lint
├── fix
├── doctor
├── config
├── update
└── dev
```

A primeira versão precisava provar que uma linguagem própria poderia funcionar.

As versões seguintes começaram a descobrir o que poderia ser construído em cima dela.

---

# Linha de evolução

```text
Ideia
  │
  ▼
Primeiros testes
  │
  ▼
JLScript 1.0.0
  │
  ▼
Interpretador
  │
  ▼
Runtime
  │
  ▼
CLI
  │
  ▼
Bibliotecas
  │
  ▼
Compilação
  │
  ▼
Bytecode
  │
  ▼
Ferramentas
  │
  ▼
JLScripter
  │
  ▼
?
```

O último ponto continua aberto.

Porque o projeto ainda está sendo desenvolvido.

---

# O futuro

O JLScript ainda está em evolução.

Sua história não termina na versão atual.

A intenção é continuar melhorando a linguagem, suas ferramentas, bibliotecas, compilação e experiência de desenvolvimento.

O objetivo não é fingir que um projeto jovem já resolveu todos os problemas de uma linguagem madura.

É continuar construindo.

A versão 1.0.0 começou com pouco.

Esse pouco foi suficiente para criar a base.

Depois vieram novas estruturas, bibliotecas, ferramentas e ideias.

A história do JLScript pode ser resumida em uma frase:

> **Começou como a vontade de criar uma linguagem própria e se transformou na vontade de construir um ecossistema inteiro ao redor dela.**

---

<div align="center">

## JLScript

**Criado no Brasil 🇧🇷**

**J = Joicy • L = Lucas • Script = Programação**

Criado por **Lucas Aguiel Dos Santos De Oliveira**

</div>
