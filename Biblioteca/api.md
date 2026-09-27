# #api

A biblioteca nativa **`#api`** fornece as ferramentas HTTP do JLScript.

Com ela é possível tanto **criar servidores e APIs HTTP** quanto **realizar requisições para APIs e serviços externos**.

Ela pode ser utilizada para criar backends, conectar aplicações, enviar e receber dados, consumir APIs externas e construir serviços web diretamente em JLScript.

---

# Importação

Para utilizar a biblioteca:

```jls
import #api
```

Se ela for utilizada junto com outras bibliotecas:

```jls
import [#api, #database]
```

---

# Para que serve?

A `#api` possui dois lados principais:

```text
#api
│
├── Servidor HTTP
│   ├── criar servidor
│   ├── criar rotas
│   ├── receber requisições
│   ├── receber dados
│   └── enviar respostas
│
└── Cliente HTTP
    ├── GET
    ├── POST
    ├── PUT
    ├── PATCH
    ├── DELETE
    ├── headers
    └── envio de dados
```

Isso significa que o mesmo módulo pode ser utilizado tanto para **construir uma API** quanto para **se comunicar com outra API**.

---

# Criando uma API

Um servidor HTTP pode ser criado com:

```jls
import #api

va app = api.criarApi(3000)
```

A porta informada deve ser um número inteiro entre:

```text
1 - 65535
```

Se nenhuma porta for informada, a porta padrão é:

```text
3000
```

Portanto:

```jls
va app = api.criarApi()
```

utiliza a porta `3000`.

Também existem os nomes:

```jls
api.criarServidor(3000)
api.servidor(3000)
```

Os três criam um servidor HTTP.

---

# Criando uma rota GET

Depois de criar o servidor, podem ser registradas rotas.

```jls
app.get("/", func(req, res) {
    res.enviar("Olá, mundo!")
})
```

Quando alguém acessar `/`, o callback da rota será executado.

Ele recebe dois objetos:

```text
req → Request
res → Response
```

`req` contém informações sobre a requisição recebida.

`res` controla a resposta que será enviada.

---

# Iniciando o servidor

Depois de configurar as rotas:

```jls
app.iniciar()
```

O servidor começa a aceitar conexões.

Exemplo completo:

```jls
import #api

va app = api.criarApi(3000)

app.get("/", func(req, res) {
    res.enviar("Minha primeira API em JLScript!")
})

app.iniciar()
```

O servidor HTTP é executado sem bloquear diretamente a execução principal e permanece disponível para receber conexões.

---

# Métodos HTTP

O servidor suporta os principais métodos HTTP.

## GET

```jls
app.get("/usuarios", func(req, res) {
    res.enviar("Lista de usuários")
})
```

Também existe o alias em português:

```jls
app.pegar("/usuarios", func(req, res) {
    res.enviar("Lista de usuários")
})
```

---

## POST

```jls
app.post("/usuarios", func(req, res) {
    res.enviar("Usuário recebido")
})
```

Alias:

```jls
app.postar("/usuarios", func(req, res) {
    res.enviar("Usuário recebido")
})
```

---

## PUT

```jls
app.put("/usuarios", func(req, res) {
    res.enviar("Usuário atualizado")
})
```

Alias:

```jls
app.atualizar("/usuarios", func(req, res) {
    res.enviar("Usuário atualizado")
})
```

---

## PATCH

```jls
app.patch("/usuarios", func(req, res) {
    res.enviar("Usuário modificado")
})
```

Alias:

```jls
app.modificar("/usuarios", func(req, res) {
    res.enviar("Usuário modificado")
})
```

---

## DELETE

Para remover uma rota:

```jls
app.remover("/usuarios", func(req, res) {
    res.enviar("Usuário removido")
})
```

---

# Request

Toda rota recebe um objeto de requisição.

```jls
func(req, res) {
}
```

O `req` permite consultar informações enviadas pelo cliente.

---

## Corpo da requisição

Para acessar o corpo:

```jls
req.corpo()
```

Também existe:

```jls
req.body()
```

Exemplo:

```jls
app.post("/dados", func(req, res) {
    va dados = req.corpo()

    mostrar(dados)

    res.enviar("Dados recebidos")
})
```

---

# Método HTTP recebido

É possível descobrir qual método foi utilizado:

```jls
req.metodo()
```

ou:

```jls
req.method()
```

Por exemplo:

```jls
va metodo = req.metodo()
```

Pode retornar:

```text
GET
POST
PUT
PATCH
DELETE
```

---

# Caminho da requisição

O caminho acessado pode ser obtido com:

```jls
req.caminho()
```

ou:

```jls
req.path()
```

Exemplo:

```jls
va caminho = req.caminho()
```

---

# Headers recebidos

Um header pode ser consultado utilizando:

```jls
req.cabecalho("Authorization")
```

ou:

```jls
req.header("Authorization")
```

A busca pelo nome do header não diferencia letras maiúsculas de minúsculas.

---

# Response

O objeto `res` representa a resposta HTTP que será enviada ao cliente.

Com ele é possível controlar:

```text
conteúdo
JSON
status HTTP
headers
```

---

# Enviando uma resposta

A forma mais simples é:

```jls
res.enviar("Olá!")
```

Também existe:

```jls
res.send("Olá!")
```

---

# Enviando JSON

Para retornar JSON:

```jls
res.json({
    mensagem: "Olá",
    sucesso: true
})
```

A resposta será tratada como conteúdo JSON pelo servidor.

Por exemplo:

```jls
app.get("/usuario", func(req, res) {
    res.json({
        nome: "Lucas",
        linguagem: "JLScript"
    })
})
```

---

# Status HTTP

O código HTTP pode ser definido utilizando:

```jls
res.status(201)
```

Exemplo:

```jls
app.post("/usuario", func(req, res) {
    res.status(201)

    res.json({
        sucesso: true
    })
})
```

O status atual também pode ser consultado:

```jls
va codigo = res.status()
```

Por padrão, uma resposta começa com:

```text
200
```

O JLScript aceita códigos HTTP entre:

```text
100 - 599
```

Um valor inválido é convertido para `500`.

---

# Headers da resposta

Headers personalizados podem ser adicionados com:

```jls
res.cabecalho("X-App", "JLScript")
```

Também existe:

```jls
res.header("X-App", "JLScript")
```

Por segurança, nomes e valores de headers passam por validação antes de serem adicionados à resposta.

---

# Parando o servidor

Um servidor em execução pode ser encerrado utilizando:

```jls
app.parar()
```

Isso encerra o servidor e sua thread de aceitação de conexões.

---

# Consultando uma API externa

A `#api` também possui um cliente HTTP.

Uma requisição GET pode ser realizada com:

```jls
import #api

va resposta = api.consultar("https://exemplo.com")
```

Também existem:

```jls
api.obter("https://exemplo.com")
```

e:

```jls
api.api("https://exemplo.com")
```

Essas operações realizam uma requisição GET.

---

# Resultado de uma requisição

Uma requisição HTTP retorna um objeto contendo informações sobre a operação.

A estrutura possui:

```text
sucesso
status
corpo
conteudo
cabecalhos
tempoMs
bytes
erro
```

Exemplo:

```jls
va resposta = api.consultar("https://exemplo.com")

mostrar(resposta.status)
mostrar(resposta.corpo)
```

### `sucesso`

Indica se a operação HTTP foi considerada bem-sucedida.

### `status`

Código HTTP retornado.

Exemplo:

```text
200
404
500
```

### `corpo`

Conteúdo retornado pelo servidor.

### `conteudo`

Alias para o conteúdo da resposta.

### `cabecalhos`

Objeto contendo os headers recebidos.

### `tempoMs`

Tempo utilizado pela requisição em milissegundos.

### `bytes`

Quantidade de bytes presentes no corpo da resposta.

### `erro`

Mensagem de erro caso a operação não consiga ser realizada corretamente.

---

# Requisições personalizadas

Quando for necessário escolher manual