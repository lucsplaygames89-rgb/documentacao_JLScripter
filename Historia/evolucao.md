# A evolução do JLScript

O **JLScript** mudou muito desde sua primeira versão.

Quando a versão **1.0.0** foi criada, o objetivo principal ainda era fazer a linguagem funcionar e provar que o projeto poderia sair de uma ideia e realmente executar programas escritos em `.jls`.

Naquela época, o JLScript possuía poucos recursos.

Não existiam as bibliotecas nativas atuais, o sistema de compilação ainda era muito menor, não havia todo o ecossistema de ferramentas existente hoje e o terminal possuía apenas algumas funções básicas.

Mesmo assim, aquela pequena versão criou a base para tudo que viria depois.

---

# JLScript 1.0.0

A primeira versão oficial do JLScript foi a **1.0.0**.

Ela possuía recursos básicos da linguagem, como:

- `if`;
- `else`;
- funções;
- `switch`;
- `for`;
- loops;
- execução de código JLScript;
- um CLI inicial.

Comparada às versões posteriores, era uma linguagem pequena.

Sua estrutura podia ser representada aproximadamente assim:

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

Ainda não existia um grande ecossistema ao redor da linguagem.

O foco era fazer o núcleo funcionar.

---

# O primeiro terminal

Mesmo na versão 1.0.0, o JLScript já possuía seu próprio CLI.

Ele era extremamente simples comparado ao terminal atual.

Um dos comandos disponíveis era:

```bash
jls version
```

O terminal ainda não possuía dezenas de ferramentas.

Não existiam todos os comandos atuais para compilação, análise, projetos, testes, diagnóstico e desenvolvimento.

Mas uma decisão importante já havia sido tomada:

> O JLScript teria suas próprias ferramentas de terminal.

O comando:

```text
jls
```

começou pequeno, mas posteriormente se tornaria a entrada para praticamente todo o ecossistema da linguagem.

---

# Antes das bibliotecas

Na versão 1.0.0 ainda não existia o sistema atual de bibliotecas nativas.

Não era possível escrever coisas como:

```jls
import #api
```

ou:

```jls
import [#api, #database]
```

O JLScript estava concentrado principalmente no funcionamento da própria linguagem.

Com a evolução do projeto, isso começou a mudar.

Funcionalidades específicas passaram a ser separadas em bibliotecas.

A ideia era evitar colocar tudo diretamente dentro do núcleo da linguagem.

---

# O nascimento das bibliotecas nativas

Com o crescimento do JLScript surgiu o sistema de bibliotecas nativas.

Uma biblioteca pode ser importada utilizando:

```jls
import #json
```

E várias bibliotecas podem ser utilizadas juntas:

```jls
import [#api, #database]
```

Isso permitiu que novas funcionalidades fossem adicionadas sem transformar o núcleo da linguagem em uma coleção gigantesca de recursos sem separação.

As bibliotecas começaram a atender diferentes áreas, como:

```text
APIs
Banco de dados
JSON
Arquivos
Sistema
Processos
Rede
Tempo
Matemática
Criptografia
Testes
Interfaces
Estilos
Dispositivos
Conexões
Desenvolvimento de linguagens
```

A estrutura começou a mudar:

```text
ANTES

JLScript
│
└── Recursos da própria linguagem


DEPOIS

JLScript
│
├── Linguagem
├── Runtime
├── Compilação
├── CLI
└── Bibliotecas
    ├── #api
    ├── #database
    ├── #json
    ├── #ui
    ├── #style
    ├── #mobile
    ├── #connector
    └── ...
```

Essa foi uma das mudanças que permitiram que o projeto crescesse sem colocar toda funcionalidade diretamente na linguagem.

---

# A evolução do terminal

Uma das partes que mais mudou desde a versão 1.0.0 foi o terminal.

No começo, existiam poucos comandos.

Um exemplo era:

```bash
jls version
```

Com o crescimento da linguagem, o terminal também precisou crescer.

O CLI atual possui ferramentas relacionadas a:

- execução;
- projetos;
- compilação;
- bytecode;
- testes;
- formatação;
- análise;
- correção;
- diagnóstico;
- configuração;
- atualização;
- inteligência artificial;
- desenvolvimento de linguagens;
- desenvolvimento do próprio JLScript;
- self-hosting.

O que antes era apenas um terminal pequeno começou a se transformar em uma ferramenta de desenvolvimento completa para o ecossistema.

---

# Antes e depois do terminal

## Antes

Na primeira versão, a ideia do CLI era muito menor:

```text
JLScript 1.0.0

jls
│
└── poucos comandos
    │
    └── version
```

## Depois

O terminal atual possui uma estrutura muito maior:

```text
JLS CLI
│
├── Execução
│   ├── run
│   ├── repl
│   └── preview
│
├── Projetos
│   ├── new
│   ├── create
│   └── init
│
├── Compilação
│   ├── build
│   ├── compile
│   ├── targets
│   ├── clean
│   └── verify-bytecode
│
├── Qualidade
│   ├── test
│   ├── fmt
│   ├── lint
│   └── fix
│
├── Ambiente
│   ├── doctor
│   ├── config
│   └── update
│
├── Inteligência Artificial
│   └── ai
│
├── Desenvolvimento de linguagens
│   └── language
│
├── Desenvolvimento
│   └── dev
│
└── Self-hosting
    └── selfhost
```

Essa diferença mostra claramente como o projeto mudou.

O terminal deixou de ser apenas uma forma de executar ou consultar informações sobre a linguagem.

Ele passou a participar de praticamente todo o processo de desenvolvimento.

---

# Executando programas

A execução de arquivos JLScript passou a fazer parte diretamente do CLI.

```bash
jls run app.jls
```

O terminal recebe o arquivo e inicia sua execução através da infraestrutura da linguagem.

Também é possível encaminhar argumentos para o programa:

```bash
jls run app.jls -- --porta 3000
```

Assim, o terminal começou a servir como interface entre o usuário e o runtime do JLScript.

---

# REPL

O terminal também ganhou um modo interativo:

```bash
jls repl
```

Em vez de criar um arquivo para cada teste pequeno, o programador pode trabalhar diretamente com a linguagem através do terminal.

Isso torna possível experimentar expressões e recursos durante o desenvolvimento.

---

# Preview

Outra ferramenta adicionada ao terminal foi:

```bash
jls preview
```

Ela faz parte das ferramentas voltadas à visualização e desenvolvimento de projetos compatíveis com esse sistema.

Esse tipo de comando demonstra como o CLI começou a assumir responsabilidades que simplesmente não existiam na versão 1.0.0.

---

# Compilação

Outra grande evolução foi o sistema de compilação.

O JLScript atual possui ferramentas específicas para transformar código em outros formatos.

Um projeto pode utilizar:

```bash
jls build app.jls
```

para processos de build suportados pelo compilador.

Também existe:

```bash
jls compile app.jls
```

para geração de bytecode JLScript.

O bytecode utiliza arquivos:

```text
.jlb
```

Isso criou uma nova estrutura:

```text
Código .jls
    │
    ├──────────────┐
    │              │
    ▼              ▼
Interpretador   Compilador
                   │
                   ▼
                Bytecode
                   │
                   ▼
                  .jlb
```

A primeira versão não possuía essa infraestrutura.

---

# Verificação de bytecode

Com a existência de bytecode também surgiu a necessidade de ferramentas para verificar esses arquivos.

O terminal atual possui:

```bash
jls verify-bytecode arquivo.jlb
```

Isso permite verificar bytecode através das próprias ferramentas do JLScript.

Mais uma vez, algo que não fazia sentido existir na versão 1.0.0 passou a ser necessário conforme o projeto cresceu.

---

# Targets

O sistema de build também passou a trabalhar com targets.

O terminal possui:

```bash
jls targets
```

Essa área está relacionada aos destinos disponíveis para processos de construção suportados pelo projeto.

O terminal também possui ferramentas de limpeza:

```bash
jls clean
```

Assim, o CLI passou a controlar diferentes etapas do processo de build.

---

# Testes

O JLScript também ganhou infraestrutura própria para testes.

O terminal possui:

```bash
jls test
```

O sistema procura testes JLScript utilizando arquivos no formato:

```text
tests/**/*.test.jls
```

associados à biblioteca:

```jls
#test
```

Isso permite que testes façam parte do próprio ecossistema da linguagem.

Na versão 1.0.0, esse tipo de integração ainda não existia.

---

# Formatação

O terminal atual também possui ferramentas para trabalhar com a formatação do código.

```bash
jls fmt app.jls
```

A ideia é permitir que o próprio ecossistema possua uma maneira consistente de organizar código JLScript.

---

# Análise de código

Para análise existem ferramentas como:

```bash
jls lint app.jls
```

Isso permite detectar determinados problemas sem depender apenas da execução do programa.

Também existe:

```bash
jls fix
```

para operações de correção suportadas pelo CLI.

O terminal deixou de apenas executar código.

Ele começou a ajudar a cuidar do código.

---

# Diagnóstico

Outra evolução importante foi a criação de ferramentas para analisar o ambiente.

```bash
jls doctor
```

O objetivo é permitir que o próprio JLScript identifique problemas relacionados ao ambiente necessário para determinadas funcionalidades.

O CLI atual possui verificações relacionadas a diferentes targets e ferramentas utilizadas pelo projeto.

Isso é muito diferente do terminal inicial.

Antes:

```text
Execute alguma coisa.
```

Depois:

```text
Execute.
Compile.
Teste.
Analise.
Formate.
Diagnostique.
Configure.
Atualize.
```

---

# Configuração

O terminal também passou a possuir gerenciamento de configurações:

```bash
jls config
```

Isso ajuda a centralizar configurações utilizadas pelo ecossistema.

À medida que uma linguagem ganha mais ferramentas, configurações deixam de ser um detalhe e começam a fazer parte da própria experiência de desenvolvimento.

---

# Atualizações

Outra ferramenta adicionada foi:

```bash
jls update
```

O sistema de atualização passou a fazer parte do CLI.

Isso permite que o próprio terminal participe do processo de manutenção da instalação do JLScript.

---

# Criação de projetos

O JLScript também deixou de trabalhar apenas com arquivos isolados.

O terminal atual possui comandos relacionados à criação e inicialização de projetos:

```bash
jls new
```

```bash
jls create
```

```bash
jls init
```

Isso representa outra mudança de escala.

No começo:

```text
arquivo.jls
```

Depois:

```text
Projeto JLScript
│
├── código
├── configuração
├── testes
├── bibliotecas
└── build
```

A linguagem começou a ganhar ferramentas voltadas não apenas para pequenos arquivos, mas também para organização de projetos.

---

# Inteligência artificial

O terminal atual também possui integração com ferramentas de inteligência artificial através de:

```bash
jls ai
```

Essa área passou a fazer parte das ferramentas experimentais e de assistência do ecossistema.

É uma comparação curiosa com a primeira versão.

Na 1.0.0, o desafio era fazer:

```bash
jls version
```

funcionar corretamente.

Depois, o mesmo terminal começou a receber integração com IA.

O projeto claramente não recebeu o memorando sobre crescer devagar.

---

# Desenvolvimento de outras linguagens

Uma das evoluções mais diferentes do projeto foi a criação do sistema relacionado ao `#compiler`.

A biblioteca funciona como um **Language Development Kit (LDK)**.

Ela permite utilizar infraestrutura do JLScript para definir e experimentar outras linguagens.

O terminal possui comandos como:

```bash
jls language run
```

```bash
jls language inspect
```

```bash
jls language doctor
```

A evolução pode ser representada assim:

```text
JLScript 1.0.0
│
└── tentando executar
    sua própria linguagem


JLScript atual
│
├── executa JLScript
├── compila JLScript
├── gera bytecode
│
└── possui infraestrutura experimental
    para desenvolvimento de outras linguagens
```

Esse tipo de recurso sequer fazia parte da escala original do projeto.

---

# Desenvolvimento do próprio JLScript

O terminal também passou a possuir ferramentas voltadas ao desenvolvimento do próprio projeto.

Existe:

```bash
jls dev
```

com operações relacionadas ao ambiente de desenvolvimento.

Entre elas estão comandos como:

```bash
jls dev build
```

```bash
jls dev watch
```

```bash
jls dev clean
```

```bash
jls dev status
```

Isso cria uma situação interessante:

> O terminal criado para trabalhar com JLScript também começou a ajudar no desenvolvimento do próprio JLScript.

---

# Self-hosting

Outra área presente no projeto atual é:

```bash
jls selfhost
```

O sistema possui operações relacionadas aos experimentos de self-hosting do projeto.

Entre elas:

```bash
jls selfhost status
```

e:

```bash
jls selfhost test
```

Essa área representa parte do objetivo de tornar o JLScript cada vez mais capaz de participar da construção de seu próprio ecossistema.

---

# A linguagem também cresceu

A evolução não aconteceu apenas no terminal.

O núcleo da linguagem também continuou crescendo.

O projeto passou a possuir uma arquitetura muito maior envolvendo:

```text
Lexer
Parser
AST
Interpretador
Runtime
Compiladores
Bytecode
CLI
Sistema de módulos
Bibliotecas nativas
Ferramentas
```

O que começou com algumas estruturas básicas passou a exigir diferentes subsistemas trabalhando juntos.

---

# Antes e depois

A diferença entre a versão 1.0.0 e o projeto atual pode ser resumida assim:

| JLScript 1.0.0 | JLScript atual |
| --- | --- |
| Poucos recursos | Ecossistema muito maior |
| `if` e `else` | Sistema de controle mais completo |
| Funções | Sistema de funções integrado ao runtime |
| `switch` | Estruturas de seleção mais maduras |
| `for` e loops | Sistema de repetição expandido |
| Sem bibliotecas nativas | Sistema de bibliotecas nativas |
| CLI pequeno | CLI com várias categorias de ferramentas |
| Poucos comandos | Execução, build, testes, análise e manutenção |
| Sem bytecode atual | Compilação para `.jlb` |
| Sem ferramentas de projeto | `new`, `create` e `init` |
| Sem sistema de testes atual | `jls test` + `#test` |
| Sem ferramentas de análise | `fmt`, `lint` e `fix` |
| Sem diagnóstico avançado | `jls doctor` |
| Sem LDK | `#compiler` + `jls language` |
| Sem ferramentas de desenvolvimento próprias | `jls dev` |
| Sem self-hosting | `jls selfhost` |
| Sem integração atual de IA | `jls ai` |

---

# A maior diferença

Talvez a maior mudança não seja uma função específica.

É a forma como o projeto passou a ser organizado.

No começo:

```text
JLScript
   │
   ▼
Executar código
```

Depois:

```text
                    JLScript
                       │
        ┌──────────────┼──────────────┐
        │              │              │
     Linguagem       Runtime      Ferramentas
        │              │              │
     Parser        Execução          CLI
     Lexer         Bytecode          Testes
     AST           Compilação        Lint
                                    Format
                                    Doctor
                                      │
                    ┌─────────────────┼─────────────────┐
                    │                 │                 │
               Bibliotecas       Projetos          Desenvolvimento
                    │                                   │
              #api                                   dev
              #database                              language
              #json                                  selfhost
              #ui
              #style
              #mobile
              #connector
              ...
```

JLScript deixou de ser apenas um interpretador capaz de entender algumas instruções.

Começou a se transformar em um ecossistema.

---

# De `jls version` para tudo isso

Talvez a evolução do terminal seja a maneira mais simples de resumir a história.

No começo havia algo pequeno como:

```bash
jls version
```

Anos de arquitetura não separam esses dois momentos.

Tudo isso começou a acontecer dentro do próprio período inicial de desenvolvimento do projeto.

Mesmo assim, hoje o mesmo comando `jls` abre caminho para execução, compilação, projetos, testes, diagnóstico, desenvolvimento de linguagens e várias outras ferramentas.

```text
jls
│
├── run
├── repl
├── preview
├── new
├── create
├── init
├── build
├── compile
├── targets
├── clean
├── verify-bytecode
├── test
├── fmt
├── lint
├── fix
├── doctor
├── config
├── update
├── ai
├── language
├── dev
└── selfhost
```

O pequeno CLI da primeira versão acabou se tornando uma das principais interfaces do projeto.

---

# De uma linguagem para um ecossistema

A versão 1.0.0 precisava responder uma pergunta:

> **É possível fazer o JLScript funcionar?**

Depois que essa resposta começou a ser positiva, surgiu outra:

> **Até onde o JLScript pode crescer?**

A partir daí vieram novas estruturas da linguagem, bibliotecas, compilação, bytecode, projetos, testes, ferramentas e novas áreas de experimentação.

A evolução pode ser resumida assim:

```text
Ideia
  ↓
Primeiros códigos
  ↓
JLScript 1.0.0
  ↓
Interpretador
  ↓
Runtime
  ↓
CLI
  ↓
Bibliotecas
  ↓
Compilação
  ↓
Bytecode
  ↓
Ferramentas
  ↓
Projetos
  ↓
LDK
  ↓
Ecossistema
```

A primeira versão tinha pouco.

Mas aquele pouco foi suficiente para criar uma base.

O JLScript atual existe porque a versão 1.0.0 conseguiu fazer primeiro o mais importante:

**funcionar.**

Depois disso, cada nova versão teve espaço para transformar aquela pequena linguagem em algo cada vez maior.