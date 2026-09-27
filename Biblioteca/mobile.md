# #mobile

A biblioteca nativa **`#mobile`** fornece acesso a informações de dispositivos móveis conectados ao JLScript.

Na implementação atual, `#mobile` possui suporte a **dispositivos Android através do ADB**.

Com ela é possível consultar informações reais do celular, como:

- marca;
- modelo;
- sistema;
- versão do Android;
- bateria;
- armazenamento;
- memória RAM;
- CPU;
- endereço IP;
- estado da conexão;
- capacidades disponíveis;
- estatísticas gerais do dispositivo.

---

# Importação

Para utilizar:

```jls id="mc7f41"
import #mobile
```

Porém, `#mobile` depende de uma conexão criada pelo `#connector`.

Por isso, normalmente as duas bibliotecas serão utilizadas juntas:

```jls id="hp3k6m"
import [#connector, #mobile]
```

---

# Como #mobile funciona?

O `#mobile` não cria sozinho a conexão com o celular.

Essa responsabilidade pertence ao `#connector`.

A estrutura é:

```text id="9y0u8d"
#connector
     ↓
Conexão ADB ou USB
     ↓
#mobile
     ↓
Android
     ↓
Informações do dispositivo
```

Primeiro o JLScript estabelece uma conexão válida com o Android.

Depois essa conexão é entregue ao `#mobile`.

---

# Conectando ao celular

Uma conexão Android pode ser criada utilizando `#connector`.

Por exemplo, através do ADB:

```jls id="80zqvp"
import [#connector, #mobile]

va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)

va celular = mobile.conectar(conexao)
```

Também existe:

```jls id="t71nrw"
mobile.connect(conexao)
```

`conectar()` recebe exatamente **um objeto de conexão válido** criado pelo `#connector`.

---

# ADB

Atualmente, `#mobile` utiliza o **Android Debug Bridge (ADB)** para obter informações do Android.

Isso significa que o dispositivo precisa estar corretamente conectado e autorizado.

Dependendo do tipo de conexão, isso pode envolver:

```text id="8pcxyn"
Android
   │
   ├── Depuração USB
   │
   └── Depuração sem fio
           │
           ▼
          ADB
           │
           ▼
       #connector
           │
           ▼
        #mobile
```

O computador também precisa possuir o ADB disponível.

---

# Conexões aceitas

`#mobile` exige uma conexão Android criada através de:

```jls id="9dbs5a"
connector.adb(...)
```

ou:

```jls id="u33mkw"
connector.usb(...)
```

Uma conexão TCP genérica não é suficiente.

Por exemplo, uma conexão criada apenas como TCP não identifica automaticamente aquele dispositivo como um Android.

O `#mobile` precisa ter acesso ao backend ADB associado à conexão.

---

# Marca

Para descobrir o fabricante:

```jls id="8eabmh"
va marca = celular.marca()

mostrar(marca)
```

Exemplo de resultado:

```text id="aym1kl"
Samsung
```

Também existe:

```jls id="4cij1n"
celular.brand()
```

---

# Modelo

Para consultar o modelo:

```jls id="xg69dd"
va modelo = celular.modelo()

mostrar(modelo)
```

Alias em inglês:

```jls id="iyq8l2"
celular.model()
```

O valor é obtido diretamente das propriedades do Android.

---

# Sistema

Para descobrir o sistema:

```jls id="q9k3od"
va sistema = celular.sistema()
```

Resultado:

```text id="19gk2a"
Android
```

Também existe:

```jls id="4nxk20"
celular.system()
```

Na implementação atual do `#mobile`, o dispositivo conectado é Android.

---

# Versão do Android

Para consultar a versão:

```jls id="dkch9e"
va versao = celular.versao()

mostrar(versao)
```

Alias:

```jls id="8d5xzw"
celular.version()
```

Um resultado pode ser semelhante a:

```text id="c4x5ru"
14
```

O valor depende do Android conectado.

---

# Bateria

Informações da bateria podem ser obtidas com:

```jls id="lf0jz1"
va bateria = celular.bateria()
```

O resultado é um objeto que pode conter:

```text id="byx64w"
nivel
carregando
status
temperatura
```

Exemplo de utilização:

```jls id="xt2m16"
va bateria = celular.bateria()

mostrar(bateria.nivel)
mostrar(bateria.carregando)
mostrar(bateria.status)
mostrar(bateria.temperatura)
```

---

# Nível da bateria

```jls id="w4iv5r"
mostrar(bateria.nivel)
```

Representa o nível atual da bateria.

Por exemplo:

```text id="qf7rc1"
82
```

---

# Carregando

```jls id="lzm7yc"
mostrar(bateria.carregando)
```

Retorna um booleano:

```text id="8cx5fr"
true
```

ou:

```text id="1fk0un"
false
```

---

# Status da bateria

O campo:

```jls id="42kbwj"
bateria.status
```

pode representar estados como:

```text id="87h0kn"
desconhecido
carregando
descarregando
sem_carregar
cheia
```

---

# Temperatura

A temperatura pode ser consultada através de:

```jls id="qfys11"
bateria.temperatura
```

O valor é convertido para graus Celsius.

---

# battery()

A versão inglesa:

```jls id="fy23te"
va bateria = celular.battery()
```

utiliza propriedades em inglês:

```text id="3qq80p"
level
charging
status
temperature
```

Por exemplo:

```jls id="x58xqn"
va battery = celular.battery()

mostrar(battery.level)
mostrar(battery.charging)
mostrar(battery.temperature)
```

---

# Armazenamento

Para consultar o armazenamento interno:

```jls id="5cgtmb"
va armazenamento = celular.armazenamento()
```

O objeto retornado contém:

```text id="6j8hy0"
total
usado
livre
unidade
```

Exemplo:

```jls id="m6xk98"
va armazenamento = celular.armazenamento()

mostrar(armazenamento.total)
mostrar(armazenamento.usado)
mostrar(armazenamento.livre)
```

Os valores são retornados em:

```text id="y23d7c"
bytes
```

---

# storage()

A versão inglesa é:

```jls id="8j52bv"
va storage = celular.storage()
```

O resultado utiliza:

```text id="ll0f02"
total
used
free
unit
```

---

# Memória RAM

Para consultar a memória:

```jls id="35v49q"
va memoria = celular.memoria()
```

O resultado possui:

```text id="2ctklz"
total
usada
livre
unidade
```

Exemplo:

```jls id="qtd2m3"
va memoria = celular.memoria()

mostrar(memoria.total)
mostrar(memoria.usada)
mostrar(memoria.livre)
```

Assim como o armazenamento, os valores são retornados em bytes.

---

# memory()

A versão inglesa:

```jls id="2ew2sk"
va memory = celular.memory()
```

retorna:

```text id="04ln1j"
total
used
free
unit
```

---

# CPU

Para consultar a arquitetura da CPU:

```jls id="ur51ne"
va cpu = celular.cpu()

mostrar(cpu)
```

Um Android ARM64, por exemplo, pode retornar algo semelhante a:

```text id="81ctsy"
arm64-v8a
```

O valor vem diretamente da propriedade de arquitetura do Android.

---

# Endereço IP

Para consultar o IP:

```jls id="4dj3tw"
va endereco = celular.ip()

mostrar(endereco)
```

O `#mobile` tenta primeiro obter o endereço diretamente das propriedades de rede do Android.

Caso isso não esteja disponível, ele tenta descobrir o endereço através das rotas de rede do dispositivo.

---

# Estado

O estado da conexão pode ser consultado com:

```jls id="o22ly9"
va estado = celular.estado()
```

Também existe:

```jls id="n7zkt1"
va state = celular.state()
```

Isso permite verificar o estado atual da conexão utilizada pelo dispositivo.

---

# Capacidades

Nem todo dispositivo Android necessariamente fornece todas as informações da mesma maneira.

Por isso, `#mobile` possui:

```jls id="nj35wt"
celular.capacidades()
```

O método testa quais informações estão realmente disponíveis naquele dispositivo.

Exemplo conceitual:

```text id="asqh0j"
[
    "marca",
    "modelo",
    "sistema",
    "versao",
    "bateria",
    "armazenamento",
    "memoria",
    "cpu",
    "ip"
]
```

Isso permite descobrir recursos disponíveis antes de depender deles.

---

# capabilities()

A versão inglesa:

```jls id="45ocg7"
celular.capabilities()
```

retorna os nomes correspondentes em inglês quando aplicável:

```text id="t3zpyb"
brand
model
system
version
battery
storage
memory
cpu
ip
```

---

# Estatísticas completas

Quando várias informações são necessárias ao mesmo tempo:

```jls id="ut2a6h"
va dados = celular.estatisticas()
```

O `#mobile` tenta reunir as informações disponíveis em um único objeto.

Ele pode conter:

```text id="t1qiyq"
marca
modelo
sistema
versao
bateria
armazenamento
memoria
cpu
ip
conexao
```

Exemplo:

```jls id="k9n8su"
va dados = celular.estatisticas()

mostrar(dados.marca)
mostrar(dados.modelo)
mostrar(dados.bateria)
mostrar(dados.memoria)
```

Se determinada informação não for suportada pelo dispositivo, `estatisticas()` tenta continuar coletando as outras informações disponíveis.

---

# Informações da conexão

Dentro das estatísticas também existe:

```jls id="05kuxr"
dados.conexao
```

Esse objeto contém:

```text id="egp3bs"
tipo
estado
endereco
porta
```

Por exemplo:

```jls id="xqk2cp"
mostrar(dados.conexao.tipo)
mostrar(dados.conexao.estado)
mostrar(dados.conexao.endereco)
mostrar(dados.conexao.porta)
```

Isso permite observar tanto o celular quanto a conexão utilizada para acessá-lo.

---

# stats()

A versão inglesa:

```jls id="0a43xm"
va dados = celular.stats()
```

utiliza propriedades em inglês:

```text id="r61sfv"
brand
model
system
version
battery
storage
memory
cpu
ip
connection
```

E `connection` possui:

```text id="w55t22"
type
state
address
port
```

---

# Métodos disponíveis

| Português | Inglês | Função |
|---|---|---|
| `mobile.conectar()` | `mobile.connect()` | Cria um dispositivo Android a partir de uma conexão |
| `marca()` | `brand()` | Retorna o fabricante |
| `modelo()` | `model()` | Retorna o modelo |
| `sistema()` | `system()` | Retorna o sistema |
| `versao()` | `version()` | Retorna a versão do Android |
| `bateria()` | `battery()` | Retorna informações da bateria |
| `armazenamento()` | `storage()` | Retorna informações de armazenamento |
| `memoria()` | `memory()` | Retorna informações da RAM |
| `cpu()` | `cpu()` | Retorna a arquitetura da CPU |
| `ip()` | `ip()` | Retorna o endereço IP |
| `estado()` | `state()` | Retorna o estado da conexão |
| `capacidades()` | `capabilities()` | Lista informações suportadas |
| `estatisticas()` | `stats()` | Reúne informações do dispositivo |

---

# Os métodos não recebem argumentos

Depois que o dispositivo é conectado, os métodos de consulta não precisam receber parâmetros.

Correto:

```jls id="k7g73j"
celular.marca()
celular.bateria()
celular.memoria()
```

Não é necessário informar novamente IP, porta ou conexão.

Essas informações já pertencem ao objeto `celular`.

---

# Erros de conexão

`#mobile` verifica vários problemas antes de permitir acesso ao Android.

## Dispositivo não autorizado

Se o Android ainda não autorizou o computador, a conexão é rejeitada.

É necessário confirmar a autorização ADB exibida no aparelho.

---

## Dispositivo offline

Se o ADB identificar o Android como offline, `#mobile` gera um erro.

Na depuração sem fio, uma porta antiga pode deixar de aceitar conexões.

Nesse caso, pode ser necessário verificar novamente a porta exibida pelo Android.

---

## Timeout

Se o dispositivo não responder dentro do tempo definido na conexão:

```jls id="6qvyjr"
timeout = 20 seg
```

a operação é encerrada com erro de timeout.

---

## ADB indisponível

Se o JLScript não conseguir encontrar o ADB, `#mobile` não consegue consultar o Android.

A implementação também permite configurar o caminho do ADB através de:

```text id="sz1f2b"
JLS_ADB_PATH
```

---

# Exemplo completo

```jls id="72kafw"
import [#connector, #mobile]

va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)

va celular = mobile.conectar(conexao)

mostrar("Dispositivo:")
mostrar(celular.marca())
mostrar(celular.modelo())

mostrar("Sistema:")
mostrar(celular.sistema())
mostrar(celular.versao())

va bateria = celular.bateria()

mostrar("Bateria:")
mostrar(bateria.nivel)
mostrar(bateria.carregando)
mostrar(bateria.temperatura)

va memoria = celular.memoria()

mostrar("Memória:")
mostrar(memoria.total)
mostrar(memoria.usada)
mostrar(memoria.livre)

va armazenamento = celular.armazenamento()

mostrar("Armazenamento:")
mostrar(armazenamento.total)
mostrar(armazenamento.usado)
mostrar(armazenamento.livre)

mostrar("CPU:")
mostrar(celular.cpu())

mostrar("IP:")
mostrar(celular.ip())
```

---

# Exemplo usando estatísticas

Quando o objetivo for obter praticamente tudo de uma vez:

```jls id="s9gj6o"
import [#connector, #mobile]

va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)

va celular = mobile.conectar(conexao)

va dados = celular.estatisticas()

mostrar(dados)
```

Isso evita realizar manualmente cada chamada quando a aplicação precisa de uma visão geral do dispositivo.

---

# #connector e #mobile

As responsabilidades das duas bibliotecas são diferentes:

```text id="xg07f5"
#connector
     │
     ├── encontra
     ├── conecta
     └── mantém a conexão
             │
             ▼
          #mobile
             │
             ├── identifica o Android
             ├── consulta propriedades
             ├── consulta bateria
             ├── consulta armazenamento
             ├── consulta RAM
             ├── consulta CPU
             ├── consulta rede
             └── reúne estatísticas
```

`#connector` responde:

> **Como chegar ao dispositivo?**

`#mobile` responde:

> **O que posso descobrir sobre esse dispositivo?**

---

# Por que usar #mobile?

Sem `#mobile`, uma aplicação teria que conhecer comandos específicos do ADB e interpretar manualmente cada resposta produzida pelo Android.

A biblioteca faz essa tradução.

Por exemplo, internamente informações de bateria precisam ser consultadas no Android, interpretadas e convertidas.

Para quem programa em JLScript, isso se transforma simplesmente em:

```jls id="e6jpxx"
va bateria = celular.bateria()

mostrar(bateria.nivel)
```

Essa é a função principal do `#mobile`: esconder a complexidade da comunicação com o Android atrás de uma API simples e integrada à linguagem.