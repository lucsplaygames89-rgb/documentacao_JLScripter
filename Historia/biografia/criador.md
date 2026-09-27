# Lucas Aguiel Dos Santos De Oliveira

**Lucas Aguiel Dos Santos De Oliveira** é um programador brasileiro, estudante de tecnologia e criador do **JLScript (JLS)** e do projeto **JLScripter**.

Nascido em **7 de setembro de 2006**, Lucas é baiano e desenvolve seus projetos no Brasil.

Seu principal interesse está relacionado à tecnologia, especialmente **programação, desenvolvimento de software, linguagens de programação e segurança cibernética**.

Mais do que utilizar programas e linguagens existentes, Lucas sempre demonstrou interesse em entender como essas tecnologias funcionam por dentro.

Foi essa curiosidade que posteriormente daria origem ao seu maior projeto: criar sua própria linguagem de programação.

---

# O interesse pela tecnologia

A trajetória de Lucas na programação começou através do interesse por computadores e desenvolvimento de software.

No início, como acontece com praticamente qualquer pessoa aprendendo programação, o objetivo era entender como escrever código e fazer um programa funcionar.

Mas, com o tempo, apenas utilizar linguagens prontas começou a gerar outras perguntas.

Não bastava mais saber:

> Como faço isso?

Também começou a importar:

> Como isso funciona por trás?

Como uma linguagem entende uma variável?

Como ela sabe onde começa e termina uma função?

Como um `if` consegue decidir qual código executar?

Como um arquivo de texto se transforma em um programa?

Como um terminal consegue encontrar, executar e compilar código?

Essas perguntas mudaram a forma como Lucas estudava programação.

---

# Aprender construindo

Uma característica importante da trajetória de Lucas é sua forma de aprender.

Em vez de estudar todos os conceitos primeiro e somente depois começar um projeto, muitas vezes o processo acontece ao contrário:

```text
Ter uma ideia
     ↓
Começar a construir
     ↓
Encontrar um problema
     ↓
Estudar o problema
     ↓
Implementar uma solução
     ↓
Descobrir outro problema
     ↓
Continuar aprendendo
```

Essa maneira de trabalhar acabou levando Lucas a áreas cada vez mais complexas da computação.

Um projeto que começa precisando apenas executar uma instrução pode acabar exigindo conhecimento sobre:

- análise léxica;
- parsing;
- árvores de sintaxe;
- interpretadores;
- runtimes;
- compiladores;
- bytecode;
- sistemas operacionais;
- processos;
- redes;
- APIs;
- bancos de dados;
- interfaces;
- segurança;
- arquitetura de software.

Foi exatamente esse processo que aconteceu com o JLScript.

---

# O nascimento do JLScript

Em **2026**, Lucas começou a desenvolver sua própria linguagem de programação.

Ela recebeu o nome de:

# JLScript

Também conhecida pela abreviação:

```text
JLS
```

e utilizando arquivos:

```text
.jls
```

O projeto começou com uma ideia relativamente simples:

> Criar uma linguagem que fosse divertida de desenvolver, simples de utilizar e capaz de se tornar algo sério.

Lucas gostava da simplicidade encontrada em linguagens como Python e de características da programação com JavaScript, mas também encontrava coisas que gostaria de escrever de outra maneira.

Em vez de apenas reclamar dessas escolhas, decidiu experimentar suas próprias.

Nascia assim o JLScript.

---

# Uma linguagem brasileira

JLScript é originalmente uma linguagem brasileira.

O português passou a fazer parte da identidade do projeto desde seu desenvolvimento.

Um programa pode utilizar estruturas como:

```jls
va nome = "Lucas"

se (nome == "Lucas") {
    mostrar("Olá, Lucas!")
} senao {
    mostrar("Usuário desconhecido")
}
```

A ideia não era simplesmente traduzir palavras de outras linguagens.

Lucas queria experimentar uma linguagem em que programar em português pudesse parecer natural.

Ao mesmo tempo, o JLScript também começou a desenvolver suporte a construções em inglês, permitindo que as duas formas façam parte do ecossistema.

---

# Questionando o que parecia desnecessário

Durante o desenvolvimento, Lucas começou a modificar pequenas coisas que considerava desnecessariamente repetitivas em outras linguagens.

Um exemplo aparece no `switch`.

No JLScript:

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

Por isso, não é necessário adicionar um `break` simplesmente para indicar que aquele caso terminou.

O próprio:

```text
}
```

já representa esse limite.

Esse tipo de decisão representa uma característica do projeto:

> Se a estrutura já consegue demonstrar claramente a intenção do programador, não é necessário obrigá-lo a repetir essa intenção.

---

# JLScript 1.0.0

A primeira versão oficial foi o **JLScript 1.0.0**.

Ela era pequena.

Muito pequena quando comparada ao projeto que viria depois.

Entre seus recursos estavam:

- `if`;
- `else`;
- funções;
- `switch`;
- `for`;
- loops;
- execução básica;
- um pequeno CLI.

Não existiam todas as bibliotecas atuais.

Não existia o ecossistema atual.

O terminal também fazia muito pouco.

Um dos comandos daquela época era:

```bash
jls version
```

Mesmo limitada, a versão 1.0.0 representou algo importante.

Lucas já não estava apenas tentando descobrir se conseguiria criar uma linguagem.

**Ele tinha uma linguagem funcionando.**

---

# De experimento para projeto

Depois da primeira versão, o JLScript começou a crescer rapidamente.

A estrutura deixou de ser apenas:

```text
Código
  ↓
Interpretador
  ↓
Resultado
```

e começou a envolver diferentes componentes:

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

Cada nova funcionalidade criava novos problemas.

E cada problema resolvido tornava possível construir outra parte.

---

# O terminal também cresceu

O pequeno CLI da primeira versão começou a se transformar em uma das principais partes do projeto.

O que começou com poucos comandos passou a envolver execução, compilação, testes, formatação, análise, projetos, diagnóstico, atualização e ferramentas relacionadas ao desenvolvimento da própria linguagem.

O comando:

```text
jls
```

deixou de ser apenas uma maneira simples de interagir com o executável.

Passou a representar a entrada para diferentes partes do ecossistema.

Essa evolução também demonstra uma característica da forma como Lucas desenvolve seus projetos:

uma funcionalidade inicialmente pequena pode continuar crescendo enquanto houver espaço para melhorá-la.

---

# Bibliotecas e ecossistema

Outra grande mudança aconteceu quando o JLScript começou a receber bibliotecas nativas.

Em vez de colocar todas as funcionalidades diretamente dentro da linguagem, recursos específicos poderiam ser importados.

```jls
import #api
```

ou:

```jls
import [#api, #database]
```

Com isso, o projeto começou a explorar diferentes áreas da programação através do próprio JLScript.

O que inicialmente era apenas uma linguagem experimental começou a se aproximar da ideia de um ecossistema.

---

# O significado do nome

A própria palavra **JLScript** também possui uma história pessoal.

O nome pode ser dividido em três partes:

```text
J       → Joicy
L       → Lucas
Script  → Programação
```

O **J** representa **Joicy Costa**, namorada de Lucas.

O **L** representa **Lucas**.

E **Script** representa a programação.

Portanto:

```text
J + L + Script
      ↓
   JLScript
```

Joicy não participa tecnicamente do desenvolvimento da linguagem.

Ela não criou sua sintaxe, bibliotecas, interpretador ou arquitetura.

Sua presença no nome possui um significado pessoal.

Ela representa alguém importante na vida de Lucas e na história existente ao redor do projeto.

---

# Joicy e Lucas

Lucas e Joicy possuem interesses profissionais bastante diferentes.

Lucas pretende construir sua trajetória principalmente através da tecnologia, com interesse em programação, desenvolvimento de software e segurança cibernética.

Joicy possui seus próprios objetivos, incluindo o interesse em seguir carreira na **Polícia Rodoviária Federal (PRF)** e desenvolver projetos relacionados ao **YouTube**.

Ela não precisa ser programadora para apoiar os projetos de Lucas.

E Lucas não precisa seguir o mesmo caminho profissional dela para apoiá-la.

São duas pessoas com objetivos diferentes que fazem parte da história uma da outra.

Essa relação acabou ficando registrada dentro do próprio nome JLScript.

O projeto pertence à trajetória de Lucas como programador.

Mas o nome também preserva uma parte de sua trajetória pessoal.

---

# JLScripter

Conforme a linguagem cresceu, surgiu também uma identidade maior ao redor dela: **JLScripter**.

De maneira simples:

```text
JLScript
    ↓
Linguagem


JLScripter
    ↓
Projeto e ecossistema
```

JLScripter passou a representar o conjunto formado pela linguagem e pelas ferramentas construídas ao redor dela.

Isso inclui áreas como:

```text
JLScripter
│
├── JLScript
├── Runtime
├── Compiladores
├── Bytecode
├── Terminal
├── Bibliotecas
├── Ferramentas
└── Documentação
```

O que começou como uma experiência pessoal começou a ganhar identidade própria.

---

# Segurança cibernética

Além da programação tradicional, Lucas também possui interesse em **segurança cibernética**.

Seu interesse nessa área está ligado à vontade de compreender sistemas mais profundamente: como computadores se comunicam, como aplicações são protegidas, como vulnerabilidades surgem e como sistemas podem ser testados e fortalecidos.

Programação e segurança acabam se encontrando nesse objetivo.

Para compreender como proteger software, também é importante compreender como ele funciona.

E construir software próprio oferece uma maneira prática de estudar essas estruturas.

Seu objetivo profissional envolve continuar se desenvolvendo tanto como programador quanto na área de segurança cibernética.

---

# Outros projetos

JLScript não é a única ideia desenvolvida por Lucas.

Seu interesse por tecnologia também levou a experimentos envolvendo:

- aplicações web;
- aplicações desktop;
- sistemas comerciais;
- ferramentas para programadores;
- automação;
- inteligência artificial;
- agentes de programação;
- comunicação entre dispositivos;
- interfaces;
- servidores;
- APIs.

Um dos projetos desenvolvidos paralelamente envolve a ideia de criar um agente de programação capaz de trabalhar com código, arquivos, terminal e diferentes linguagens.

Essas experiências frequentemente acabam influenciando umas às outras.

Um problema encontrado em outro projeto pode gerar uma ideia para o JLScript.

Uma funcionalidade criada para o JLScript pode gerar uma ideia para outra aplicação.

---

# Inteligência artificial

Inteligência artificial também se tornou uma das áreas de interesse de Lucas.

Mas seu interesse não está limitado a simplesmente utilizar ferramentas de IA.

Assim como aconteceu com linguagens de programação, existe curiosidade sobre como construir ferramentas próprias e como integrar inteligência artificial ao desenvolvimento de software.

Isso levou a experimentos envolvendo agentes, motores, ferramentas de programação e integração de IA com projetos próprios.

Dentro do JLScript, esse interesse também começou a aparecer em ferramentas relacionadas ao ecossistema da linguagem.

---

# Formação

Lucas também iniciou seus estudos em **Análise e Desenvolvimento de Sistemas (ADS)**.

Entretanto, grande parte de sua formação técnica acontece através do desenvolvimento independente.

Projetos reais frequentemente criam problemas que nenhum exercício preparado consegue reproduzir perfeitamente.

Um erro no parser exige entender parsing.

Um problema no runtime exige compreender execução.

Um erro de compilação exige investigar C++ e ferramentas de build.

Uma conexão que não funciona exige estudar redes.

Uma biblioteca mal organizada exige repensar arquitetura.

Dessa forma, seus próprios projetos se tornaram também uma parte importante de sua formação.

---

# Errar também faz parte

O desenvolvimento do JLScript nunca aconteceu em uma linha perfeitamente organizada.

Houve erros.

Houve funcionalidades que precisaram ser refeitas.

Houve problemas de compilação.

Houve decisões que pareciam boas inicialmente e posteriormente precisaram mudar.

Houve momentos em que uma pequena alteração acabou quebrando outra parte completamente diferente do projeto.

Isso faz parte da construção de software.

Especialmente quando o software sendo construído é a própria linguagem que deverá executar outros softwares.

O crescimento do JLScript também representa o crescimento técnico de seu criador.

---

# Construir em vez de apenas imaginar

Muitas das ideias de Lucas começam grandes.

Uma linguagem.

Um compilador.

Um agente de programação.

Um sistema capaz de conversar com dispositivos.

Uma ferramenta própria de inteligência artificial.

Nem todas começam completas.

A maneira encontrada para lidar com isso é começar por alguma parte que possa realmente funcionar.

O JLScript é provavelmente o maior exemplo disso.

Ele não começou com todas as funcionalidades atuais.

Começou com algumas estruturas básicas.

Depois veio outra.

Depois outra.

Até que aquilo que inicialmente era uma experiência começou a exigir uma arquitetura inteira.

---

# Objetivo profissional

Lucas pretende seguir profissionalmente na área de tecnologia.

Entre seus principais objetivos estão se desenvolver como **programador** e aprofundar seus conhecimentos em **segurança cibernética**.

Também existe interesse em construir produtos próprios.

Isso inclui sistemas que possam ser utilizados comercialmente, ferramentas para outros programadores e projetos independentes.

A intenção é não depender exclusivamente de ideias abstratas.

Projetos precisam eventualmente funcionar fora da cabeça de quem os imaginou.

---

# Filosofia pessoal de desenvolvimento

A trajetória de Lucas e o desenvolvimento do JLScript compartilham algumas ideias.

## Curiosidade

Não basta apenas descobrir qual comando funciona.

Entender por que funciona também importa.

## Experimentação

Uma ideia pode ser testada antes de existir certeza de que será mantida.

## Simplicidade

Algo não precisa ser complicado apenas porque tecnicamente pode ser.

## Independência

Existe satisfação em construir ferramentas próprias e compreender aquilo que normalmente seria entregue pronto.

## Evolução

Um projeto não precisa nascer completo.

Ele precisa possuir uma base sobre a qual possa continuar crescendo.

---

# Ainda no começo

Apesar do tamanho que alguns projetos começaram a alcançar, a trajetória profissional de Lucas ainda está no início.

O JLScript nasceu em 2026.

Muitas das tecnologias estudadas hoje ainda estão sendo exploradas.

Isso significa que esta biografia não representa uma carreira concluída.

Representa seu começo.

Há muito que ainda precisa ser aprendido, construído, refeito e descoberto.

E isso também significa que ainda existe muito espaço para decidir o que virá depois.

---

# O futuro

Lucas pretende continuar estudando programação, desenvolvimento de software e segurança cibernética.

Também pretende continuar desenvolvendo seus próprios projetos e expandindo o JLScript.

O objetivo de longo prazo do JLScript não é permanecer apenas como um experimento capaz de executar alguns arquivos `.jls`.

A ideia é continuar construindo um ecossistema ao redor da linguagem.

```text
JLScript
│
├── Linguagem
├── Runtime
├── Compilação
├── Bibliotecas
├── Terminal
├── Ferramentas
├── Aplicações
└── Ecossistema
```

Até onde isso chegará ainda não está definido.

E talvez essa seja justamente uma das partes mais importantes da história.

O projeto ainda está sendo construído.

Assim como seu criador.

---

# Informações

**Nome:** Lucas Aguiel Dos Santos De Oliveira  
**Nascimento:** 7 de setembro de 2006  
**Nacionalidade:** Brasileiro 🇧🇷  
**Naturalidade:** Bahia, Brasil  
**Área:** Tecnologia e desenvolvimento de software  
**Interesses:** Programação, linguagens de programação e segurança cibernética  
**Formação:** Estudos em Análise e Desenvolvimento de Sistemas  
**Criador:** JLScript (JLS) / JLScripter  
**Início do JLScript:** 2026

---

# Uma história ainda sendo escrita

Lucas começou estudando como utilizar programas e linguagens criadas por outras pessoas.

Em algum momento, surgiu a vontade de descobrir como seria construir as próprias.

Essa curiosidade resultou em uma linguagem.

A linguagem gerou um runtime.

O runtime precisou de ferramentas.

As ferramentas precisaram de um terminal.

A linguagem ganhou bibliotecas.

O projeto continuou crescendo.

E aquilo que começou como uma experiência passou a ocupar uma parte importante de sua trajetória como programador.

```text
Curiosidade
    ↓
Programação
    ↓
Experimentação
    ↓
JLScript
    ↓
JLScripter
    ↓
?
```

O último passo permanece em aberto.

Porque essa parte da história ainda não aconteceu.