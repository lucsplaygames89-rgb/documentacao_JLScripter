# Bibliotecas Nativas

As **bibliotecas nativas do JLScript** são conjuntos de ferramentas e funcionalidades que fazem parte oficialmente do ecossistema da linguagem.

Elas existem para fornecer recursos prontos para tarefas específicas sem colocar todas essas funcionalidades diretamente no núcleo do JLScript.

Uma biblioteca pode cuidar de uma área específica, como APIs, banco de dados, interfaces, sistema, matemática, dispositivos ou outras funcionalidades.

A ideia é simples:

> **Você importa somente aquilo que seu programa precisa.**

---

# O que é uma biblioteca?

Uma biblioteca é um conjunto de funcionalidades prontas que podem ser utilizadas por outros programas.

Imagine que você queira criar uma aplicação que faça requisições HTTP.

Você poderia desenvolver manualmente toda a lógica necessária para:

- criar conexões;
- enviar requisições;
- receber respostas;
- interpretar os dados;
- tratar erros;
- controlar o servidor.

Ou pode utilizar uma biblioteca que já fornece essas ferramentas.

De forma simplificada:

```text
Programa
   ↓
Biblioteca
   ↓
Funcionalidade
```

Isso permite que o programador concentre seu código na aplicação que está criando.

---

# O que significa uma biblioteca ser nativa?

Uma biblioteca **nativa** é uma biblioteca que faz parte oficialmente do JLScript.

Ela é desenvolvida para funcionar diretamente com a linguagem e acompanha seu ecossistema.

No JLScript, bibliotecas nativas são identificadas pelo prefixo:

```text
#
```

Por exemplo:

```text
#api
#database
```

O `#` permite reconhecer rapidamente que aquele nome representa uma biblioteca oficial.

---

# Como importar uma biblioteca?

Para utilizar uma biblioteca nativa, primeiro ela deve ser importada.

Quando apenas **uma biblioteca** for necessária, a sintaxe é:

```jls
import #api
```

Depois disso, o programa pode utilizar os recursos fornecidos pela biblioteca.

Outro exemplo:

```jls
import #database
```

A estrutura é:

```jls
import #biblioteca
```

---

# Importando várias bibliotecas

Quando um programa precisa utilizar mais de uma biblioteca, o JLScript permite agrupá-las em um único `import`.

Por exemplo:

```jls
import [#api, #database]
```

A estrutura é:

```jls
import [#biblioteca1, #biblioteca2]
```

Isso também pode ser utilizado com uma quantidade maior de bibliotecas:

```jls
import [#biblioteca1, #biblioteca2, #biblioteca3]
```

Portanto:

```jls
// Uma biblioteca
import #api

// Várias bibliotecas
import [#api, #database]
```

---

# Por que utilizar bibliotecas?

Nem toda funcionalidade precisa fazer parte diretamente da linguagem.

O JLScript precisa conhecer seus elementos fundamentais, como:

```jls
va nome = "Lucas"

se (nome == "Lucas") {
    mostrar("Olá!")
}
```

Variáveis, operadores, condições, funções e outras estruturas pertencem à linguagem.

Já funcionalidades específicas podem ser separadas em bibliotecas.

Por exemplo:

```text
JLScript
│
├── Núcleo da linguagem
│   ├── variáveis
│   ├── funções
│   ├── condições
│   ├── laços
│   └── operadores
│
└── Bibliotecas nativas
    ├── APIs
    ├── banco de dados
    ├── interfaces
    ├── sistema
    ├── dispositivos
    └── outros recursos
```

Essa separação ajuda a manter o núcleo da linguagem organizado enquanto permite que o ecossistema continue crescendo.

---

# Use somente aquilo que precisa

Um programa simples não precisa carregar recursos que nunca serão utilizados.

Este código:

```jls
mostrar("Olá, mundo!")
```

não precisa necessariamente de uma biblioteca.

Já uma aplicação que utiliza recursos externos pode importar aquilo que necessita:

```jls
import #api
```

E uma aplicação maior pode precisar de várias:

```jls
import [#api, #database]
```

Assim, cada programa declara claramente quais bibliotecas utiliza.

---

# Por que não colocar tudo dentro do JLScript?

Colocar todas as funcionalidades diretamente no núcleo da linguagem faria o JLScript crescer desnecessariamente.

Imagine colocar no mesmo lugar recursos para:

```text
HTTP
Banco de dados
Interfaces
Arquivos
Dispositivos
Rede
Matemática
Sistema operacional
```

Mesmo programas que nunca utilizassem esses recursos teriam uma linguagem carregada de funcionalidades específicas.

As bibliotecas resolvem esse problema separando responsabilidades.

```text
            JLScript
               │
      ┌────────┴────────┐
      │                 │
   Linguagem        Bibliotecas
      │                 │
   Sintaxe          Recursos extras
   Variáveis        APIs
   Funções          Banco de dados
   Condições        Interfaces
   Laços            Dispositivos
```

O núcleo continua responsável pela linguagem.

As bibliotecas ficam responsáveis por funcionalidades especializadas.

---

# Por que usar uma biblioteca em vez de criar tudo sozinho?

Porque muitos problemas já possuem uma solução reutilizável.

Se uma biblioteca já fornece determinada funcionalidade, utilizá-la evita repetir código desnecessariamente.

Isso traz vantagens como:

**Menos código**

O programador utiliza uma funcionalidade pronta em vez de implementar todo o funcionamento interno.

**Reutilização**

A mesma biblioteca pode ser utilizada em vários projetos.

**Organização**

Cada biblioteca possui uma responsabilidade específica.

**Padronização**

Projetos diferentes podem utilizar as mesmas ferramentas e comportamentos.

**Manutenção**

Uma funcionalidade pode ser corrigida ou melhorada dentro da própria biblioteca.

---

# Bibliotecas nativas e bibliotecas externas

O JLScript pode trabalhar com diferentes tipos de bibliotecas.

## Bibliotecas nativas

São bibliotecas que pertencem oficialmente ao ecossistema JLScript.

Elas utilizam o identificador `#`.

Exemplo:

```jls
import #api
```

Ou:

```jls
import [#api, #database]
```

Essas bibliotecas são desenvolvidas para trabalhar diretamente com os recursos da linguagem.

## Bibliotecas externas

O ecossistema também pode permitir bibliotecas desenvolvidas por outros programadores.

Isso significa que o JLScript não precisa depender apenas das funcionalidades fornecidas oficialmente.

Desenvolvedores podem criar ferramentas para necessidades específicas e reutilizá-las em seus próprios projetos ou disponibilizá-las para outras pessoas.

---

# Quando devo utilizar uma biblioteca?

Uma biblioteca deve ser utilizada quando seu programa precisa de uma funcionalidade que ela já fornece.

O processo pode ser pensado assim:

```text
Preciso fazer alguma coisa
          │
          ▼
Existe uma biblioteca?
      ┌───┴───┐
      │       │
     Sim      Não
      │       │
      ▼       ▼
  Utilizar   Criar uma
 biblioteca  solução
```

Não existe necessidade de reconstruir uma funcionalidade complexa sempre que ela já estiver disponível.

---

# A filosofia das bibliotecas do JLScript

As bibliotecas seguem uma das ideias principais do JLScript:

> **Uma funcionalidade pode ser poderosa sem ser complicada de utilizar.**

Por trás de uma biblioteca podem existir centenas ou milhares de linhas responsáveis por conexões, validações, processamento e outras operações.

Mas quem utiliza a biblioteca não deveria precisar conhecer toda essa implementação apenas para realizar uma tarefa simples.

A complexidade fica internamente onde ela é necessária.

A utilização continua simples.

---

# Documentação das bibliotecas

Cada biblioteca nativa possui sua própria documentação.

A documentação individual de uma biblioteca deve apresentar:

- o que é a biblioteca;
- para que ela serve;
- quando utilizá-la;
- como importá-la;
- recursos disponíveis;
- funções;
- parâmetros;
- valores retornados;
- exemplos de código;
- possíveis erros;
- comportamentos específicos.

Por exemplo, a documentação de uma biblioteca poderá começar com:

```jls
import #api
```

e depois explicar individualmente cada recurso disponibilizado por `#api`.

Este documento apresenta apenas o funcionamento geral do sistema de bibliotecas nativas.

As funcionalidades específicas são documentadas separadamente para que cada biblioteca possa evoluir sem transformar esta página em um monstro de documentação.