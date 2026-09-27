# #database

A biblioteca nativa **`#database`** fornece acesso a banco de dados diretamente pelo JLScript.

Na implementação atual, `#database` possui suporte nativo ao **SQLite**, permitindo criar e abrir bancos locais, executar comandos SQL, realizar consultas, utilizar parâmetros preparados e controlar transações.

Ela é útil para aplicações que precisam armazenar informações de forma permanente, como:

- usuários;
- produtos;
- configurações;
- pedidos;
- sessões;
- históricos;
- dados de aplicações;
- informações locais.

---

# Importação

Para utilizar:

```jls id="z29cj7"
import #database
```

Junto de outras bibliotecas:

```jls id="bx97gq"
import [#api, #database]
```

---

# SQLite

Atualmente, o banco implementado nativamente em `#database` é o **SQLite**.

Para abrir ou criar um banco:

```jls id="3a7u81"
va db = database.sqlite("app.db")
```

Se o arquivo não existir, o SQLite pode criá-lo automaticamente.

Se já existir, ele será aberto.

Por exemplo:

```jls id="ah6s78"
va db = database.sqlite("usuarios.db")
```

O objeto retornado representa a conexão com aquele banco.

---

# Por que SQLite?

SQLite é um banco de dados baseado em arquivo.

Isso significa que uma aplicação pode ter:

```text id="3twl75"
meu-app/
├── app.jls
└── dados.db
```

sem precisar manter um servidor de banco separado apenas para armazenar informações locais.

Isso torna `#database` especialmente útil para aplicações desktop, ferramentas, pequenos serviços, protótipos e programas que precisam de armazenamento persistente.

---

# Criando uma tabela

Com o banco aberto, comandos SQL podem ser executados utilizando:

```jls id="hn0me3"
db.executar("...")
```

Por exemplo:

```jls id="pkgl4f"
import #database

va db = database.sqlite("app.db")

db.executar("
    CREATE TABLE IF NOT EXISTS usuarios (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        nome TEXT,
        idade INTEGER
    )
")
```

`executar()` deve ser utilizado principalmente para comandos que modificam o banco.

Entre eles:

```text id="f95f8r"
CREATE
INSERT
UPDATE
DELETE
ALTER
DROP
```

---

# executar()

Executa um comando SQL.

```jls id="d60r2u"
db.executar(sql)
```

Também pode receber parâmetros:

```jls id="j1ugpb"
db.executar(sql, parametros)
```

Exemplo:

```jls id="mv9fsc"
va alterados = db.executar(
    "DELETE FROM usuarios WHERE id = ?",
    [10]
)
```

O método retorna a quantidade de registros alterados pela operação.

---

# Inserindo dados

Uma inserção simples pode ser feita com:

```jls id="38f7ma"
db.executar(
    "INSERT INTO usuarios (nome, idade) VALUES ('Lucas', 20)"
)
```

Porém, quando os valores vêm de variáveis ou do usuário, é melhor utilizar **parâmetros SQL**.

```jls id="hm87rr"
va nome = "Lucas"
va idade = 20

db.executar(
    "INSERT INTO usuarios (nome, idade) VALUES (?, ?)",
    [nome, idade]
)
```

Os `?` representam os valores que serão vinculados posteriormente.

---

# Parâmetros SQL

O `#database` possui suporte a parâmetros preparados.

Exemplo:

```jls id="w43n4a"
db.executar(
    "INSERT INTO usuarios (nome, idade) VALUES (?, ?)",
    ["Lucas", 20]
)
```

Cada `?` corresponde a uma posição da lista:

```text id="jqxm0q"
SQL                     Lista

primeiro ?    ←→        "Lucas"
segundo ?     ←→        20
```

A quantidade precisa corresponder.

Este código:

```jls id="5tf77r"
db.executar(
    "INSERT INTO usuarios (nome, idade) VALUES (?, ?)",
    ["Lucas"]
)
```

é inválido porque existem dois parâmetros SQL e apenas um valor.

---

# Tipos aceitos como parâmetros

A implementação atual permite vincular:

```text id="bf1gpp"
null
números
booleanos
duração
texto
```

Números inteiros são enviados ao SQLite como inteiros.

Números decimais são enviados como valores de ponto flutuante.

Booleanos são representados no banco como:

```text id="snpz6n"
true  → 1
false → 0
```

Valores de duração são armazenados utilizando seu valor em milissegundos.

---

# Segurança dos parâmetros

Sempre que dados externos forem utilizados dentro de SQL, prefira parâmetros:

```jls id="mrh6q4"
db.buscar(
    "SELECT * FROM usuarios WHERE nome = ?",
    [nome]
)
```

em vez de construir manualmente o SQL misturando valores dentro do texto.

Além de deixar o código mais organizado, parâmetros preparados ajudam a separar **o comando SQL** dos **dados enviados ao banco**.

---

# buscar()

`buscar()` executa uma consulta e retorna todas as linhas encontradas.

```jls id="tovx96"
va usuarios = db.buscar(
    "SELECT * FROM usuarios"
)
```

O resultado é uma lista.

Conceitualmente:

```text id="25ajcv"
[
    {
        id: 1,
        nome: "Lucas",
        idade: 20
    },

    {
        id: 2,
        nome: "Ana",
        idade: 19
    }
]
```

Cada linha retornada pelo SQLite é transformada em um objeto JLScript.

O nome da coluna se torna a propriedade do objeto.

---

# Busca com parâmetros

`buscar()` também aceita parâmetros:

```jls id="o1u0kl"
va usuarios = db.buscar(
    "SELECT * FROM usuarios WHERE idade >= ?",
    [18]
)
```

Sua estrutura é:

```jls id="n9z4en"
db.buscar(sql)
```

ou:

```jls id="wtbdpd"
db.buscar(sql, parametros)
```

---

# buscarUm()

Quando apenas um registro é necessário, utilize:

```jls id="l9wmn6"
db.buscarUm(
    "SELECT * FROM usuarios WHERE id = ?",
    [1]
)
```

Exemplo:

```jls id="94p5m2"
va usuario = db.buscarUm(
    "SELECT * FROM usuarios WHERE nome = ?",
    ["Lucas"]
)

mostrar(usuario.nome)
```

Ao contrário de `buscar()`, que retorna uma lista, `buscarUm()` retorna diretamente o primeiro objeto encontrado.

```text id="ck54ux"
buscar()

[
    { ... },
    { ... },
    { ... }
]
```

```text id="4o54ll"
buscarUm()

{ ... }
```

Se nenhuma linha for encontrada:

```jls id="vbwmnx"
null
```

é retornado.

---

# Atualizando dados

Para atualizar:

```jls id="guyewm"
va alterados = db.executar(
    "UPDATE usuarios SET idade = ? WHERE id = ?",
    [21, 1]
)
```

`alterados` recebe a quantidade de linhas modificadas.

---

# Removendo dados

```jls id="e3qx4h"
va alterados = db.executar(
    "DELETE FROM usuarios WHERE id = ?",
    [1]
)
```

Novamente, o retorno indica quantos registros foram afetados.

---

# ultimoId()

Depois de uma inserção, é possível consultar o último ID criado:

```jls id="gtif10"
db.executar(
    "INSERT INTO usuarios (nome) VALUES (?)",
    ["Lucas"]
)

va id = db.ultimoId()

mostrar(id)
```

`ultimoId()` utiliza o último identificador de inserção gerado pela conexão SQLite.

Isso é especialmente útil com tabelas que utilizam:

```sql id="uj3c5h"
INTEGER PRIMARY KEY AUTOINCREMENT
```

---

# alterados()

Também é possível consultar posteriormente quantas linhas foram modificadas pela operação SQL mais recente:

```jls id="81cwha"
db.executar(
    "UPDATE usuarios SET idade = ? WHERE id = ?",
    [21, 1]
)

va quantidade = db.alterados()
```

---

# Transações

`#database` possui suporte nativo a transações.

Uma transação permite agrupar várias alterações.

A estrutura é:

```text id="bjtrga"
iniciar
   ↓
operações
   ↓
confirmar
```

ou, caso algo dê errado:

```text id="b93ocq"
iniciar
   ↓
operações
   ↓
cancelar
```

---

# iniciar()

Para iniciar:

```jls id="0v5f19"
db.iniciar()
```

Internamente, a implementação atual utiliza uma transação SQLite:

```sql id="vk75p1"
BEGIN IMMEDIATE
```

---

# confirmar()

Quando todas as operações forem concluídas:

```jls id="89w0l9"
db.confirmar()
```

As alterações são confirmadas no banco.

Equivale ao conceito de:

```sql id="44x8jd"
COMMIT
```

---

# cancelar()

Se as alterações não devem ser mantidas:

```jls id="spqgjf"
db.cancelar()
```

Isso executa o equivalente a:

```sql id="4sk1mn"
ROLLBACK
```

e desfaz as alterações realizadas dentro da transação.

---

# Exemplo de transação

```jls id="iv8e57"
import #database

va db = database.sqlite("loja.db")

db.iniciar()

db.executar(
    "UPDATE contas SET saldo = saldo - ? WHERE id = ?",
    [100, 1]
)

db.executar(
    "UPDATE contas SET saldo = saldo + ? WHERE id = ?",
    [100, 2]
)

db.confirmar()
```

As duas operações fazem parte da mesma transação.

Se for necessário desistir das alterações antes da confirmação:

```jls id="f4vrsq"
db.cancelar()
```

---

# fechar()

Quando a conexão não for mais necessária:

```jls id="1amypm"
db.fechar()
```

Depois disso, o objeto não pode continuar executando operações no banco.

Por exemplo:

```jls id="nn9n09"
db.fechar()

db.buscar("SELECT * FROM usuarios")
```

gera erro porque a conexão já foi fechada.

O banco também é fechado automaticamente quando o objeto nativo é destruído.

---

# Valores retornados pelo SQLite

Ao realizar uma consulta, os valores do SQLite são convertidos para valores do JLScript.

```text id="g50ykb"
SQLite INTEGER → número
SQLite FLOAT   → número
SQLite TEXT    → texto
SQLite BLOB    → texto/binário
SQLite NULL    → null
```

As colunas são organizadas dentro de objetos.

Por exemplo, uma linha SQL:

```text id="dz1h76"
id | nome  | idade
1  | Lucas | 20
```

se torna conceitualmente:

```jls id="gb6kyb"
{
    id: 1,
    nome: "Lucas",
    idade: 20
}
```

---

# Métodos disponíveis

| Método | Função |
|---|---|
| `database.sqlite(caminho)` | Abre ou cria um banco SQLite |
| `db.executar(sql)` | Executa um comando SQL |
| `db.executar(sql, parametros)` | Executa SQL utilizando parâmetros |
| `db.buscar(sql)` | Retorna todas as linhas encontradas |
| `db.buscar(sql, parametros)` | Busca utilizando parâmetros |
| `db.buscarUm(sql)` | Retorna somente a primeira linha |
| `db.buscarUm(sql, parametros)` | Busca uma linha utilizando parâmetros |
| `db.iniciar()` | Inicia uma transação |
| `db.confirmar()` | Confirma uma transação |
| `db.cancelar()` | Cancela uma transação |
| `db.ultimoId()` | Retorna o último ID inserido |
| `db.alterados()` | Retorna a quantidade de linhas alteradas |
| `db.fechar()` | Fecha o banco |

---

# Exemplo completo

```jls id="stoxmy"
import #database

va db = database.sqlite("usuarios.db")

db.executar("
    CREATE TABLE IF NOT EXISTS usuarios (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        nome TEXT NOT NULL,
        idade INTEGER
    )
")

db.executar(
    "INSERT INTO usuarios (nome, idade) VALUES (?, ?)",
    ["Lucas", 20]
)

va id = db.ultimoId()

mostrar("Usuário criado:")
mostrar(id)

va usuario = db.buscarUm(
    "SELECT * FROM usuarios WHERE id = ?",
    [id]
)

mostrar(usuario)

va usuarios = db.buscar(
    "SELECT * FROM usuarios"
)

mostrar(usuarios)

db.fechar()
```

---

# Como #database funciona

A estrutura atual pode ser resumida assim:

```text id="vwn2mn"
#database
    │
    └── SQLite
         │
         ├── abrir/criar banco
         │
         ├── executar SQL
         │
         ├── parâmetros preparados
         │
         ├── buscar registros
         │
         ├── buscar um registro
         │
         ├── transações
         │
         ├── último ID
         │
         ├── linhas alteradas
         │
         └── fechar
```

---

# Por que usar #database?

`#database` permite adicionar persistência a uma aplicação JLScript sem precisar implementar manualmente um sistema de armazenamento.

Um programa pode começar trabalhando apenas com variáveis:

```jls id="7ggt9z"
va nome = "Lucas"
```

mas esse valor existe apenas durante a execução.

Com um banco:

```text id="i3c81g"
JLScript
    ↓
#database
    ↓
SQLite
    ↓
arquivo .db
    ↓
dados persistentes
```

as informações podem continuar armazenadas mesmo depois que o programa for encerrado.

Isso permite utilizar JLScript para aplicações que precisam trabalhar com dados reais e permanentes.