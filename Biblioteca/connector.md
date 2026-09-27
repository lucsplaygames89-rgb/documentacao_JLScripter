# #connector

A biblioteca nativa **`#connector`** é responsável por criar e gerenciar conexões entre aplicações JLScript e outros dispositivos ou serviços.

Ela funciona como uma camada de conexão do ecossistema.

Outras bibliotecas podem utilizar uma conexão criada pelo `#connector` para acessar funcionalidades específicas de determinado dispositivo.

Um exemplo é `#mobile`:

```text
#connector
     ↓
cria a conexão
     ↓
#mobile
     ↓
utiliza a conexão Android
```

Isso mantém duas responsabilidades separadas:

> **`#connector` conecta. A outra biblioteca utiliza a conexão.**

---

# Importação

Para utilizar:

```jls
import #connector
```

Quando outra biblioteca depender da conexão:

```jls
import [#connector, #mobile]
```

---

# Como funciona?

Uma conexão normalmente segue esta estrutura:

```text
JLScript
   │
   ▼
#connector
   │
   ├── protocolo
   ├── endereço
   ├── porta
   ├── timeout
   └── estado
          │
          ▼
      Dispositivo
```

Depois que a conexão é criada, o objeto retornado pode ser utilizado diretamente ou entregue a outra biblioteca.

Por exemplo:

```jls
va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)

va celular = mobile.conectar(conexao)
```

Nesse exemplo:

```text
connector.adb()
```

é responsável pela conexão.

Já:

```text
mobile.conectar()
```

interpreta essa conexão como um dispositivo Android.

---

# Conexão ADB

Para conectar a um Android através do ADB:

```jls
va conexao = connector.adb(
    "192.168.1.2",
    38472
)
```

Também é possível definir um timeout:

```jls
va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)
```

A estrutura é:

```jls
connector.adb(
    endereco,
    porta,
    timeout = duracao
)
```

---

# Endereço

O primeiro argumento representa o endereço do dispositivo.

Exemplo:

```jls
"192.168.1.2"
```

Normalmente será o endereço IP exibido pelo Android durante a utilização da depuração sem fio.

---

# Porta

O segundo argumento representa a porta utilizada pela conexão.

Exemplo:

```jls
38472
```

A porta não deve ser escolhida aleatoriamente quando o dispositivo ou protocolo já determina qual porta está aceitando conexões.

No caso da depuração sem fio do Android, deve ser utilizada a porta fornecida pelo próprio sistema.

---

# Timeout

O terceiro argumento pode controlar quanto tempo o JLScript deve esperar pela conexão.

```jls
timeout = 20 seg
```

O JLScript utiliza seu próprio sistema de duração, portanto o valor pode ser escrito de forma legível.

Por exemplo:

```jls
timeout = 5 seg
```

ou:

```jls
timeout = 20 seg
```

Isso significa:

> tente realizar a conexão e espere no máximo esse período antes de considerar que ela falhou.

---

# Por que `timeout = 20 seg`?

O JLScript utiliza argumentos nomeados para deixar claro o significado de determinados valores.

Por isso:

```jls
connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)
```

é preferível a algo como:

```jls
connector.adb(
    "192.168.1.2",
    38472,
    20
)
```

No primeiro exemplo, fica imediatamente claro que `20 seg` representa o tempo limite da conexão.

---

# Conexão USB

Também existe suporte para criar uma conexão Android através de USB:

```jls
va conexao = connector.usb(...)
```

Essa conexão pode posteriormente ser utilizada por bibliotecas compatíveis, como `#mobile`.

A ideia permanece a mesma:

```text
Android
   │
   │ USB
   ▼
#connector
   │
   ▼
conexão
   │
   ▼
#mobile
```

---

# Conexões genéricas

Nem toda conexão representa automaticamente um celular.

Uma conexão de rede genérica pode simplesmente representar comunicação com determinado endereço e porta.

Isso é importante porque:

```text
conectou via TCP
```

não significa:

```text
é um Android
```

Uma conexão genérica conhece informações sobre transporte e destino.

Uma conexão especializada pode carregar informações adicionais sobre o protocolo e o dispositivo.

---

# Por que isso importa?

Considere uma conexão TCP genérica:

```text
192.168.1.2:5555
```

O JLScript pode conseguir estabelecer comunicação com aquele endereço.

Mas isso sozinho não prova que existe um Android controlado por ADB naquele destino.

Por isso, bibliotecas especializadas validam o tipo da conexão antes de utilizá-la.

`#mobile`, por exemplo, exige uma conexão Android criada através de um mecanismo compatível, como:

```jls
connector.adb(...)
```

ou:

```jls
connector.usb(...)
```

---

# Objeto de conexão

Quando uma conexão é criada, `#connector` retorna um objeto representando aquela comunicação.

Conceitualmente:

```text
Connection
│
├── tipo
├── estado
├── endereço
├── porta
└── backend
```

Esse objeto pode ser entregue para outras partes do programa.

---

# Tipo da conexão

Uma conexão possui um tipo que identifica como ela foi criada.

Isso permite diferenciar, por exemplo:

```text
ADB
USB
TCP
```

Essa informação é importante para bibliotecas que exigem determinado protocolo.

---

# Estado da conexão

A conexão também possui um estado.

Isso permite distinguir situações como:

```text
conectado
offline
não autorizado
falha
```

O estado real depende do protocolo utilizado.

No ADB, por exemplo, o dispositivo pode existir mas ainda não estar autorizado para comunicação.

---

# Endereço e porta

Conexões de rede podem manter:

```text
endereço
porta
```

Por exemplo:

```text
endereço: 192.168.1.2
porta:    38472
```

Essas informações também podem ser utilizadas por outras bibliotecas que recebem o objeto de conexão.

---

# ADB e Android

Uma das principais utilizações atuais do `#connector` é estabelecer comunicação com dispositivos Android.

O fluxo completo fica:

```text
Android
   │
   │ Depuração USB
   │ ou
   │ Depuração sem fio
   ▼
ADB
   │
   ▼
#connector
   │
   ▼
Connection
   │
   ▼
#mobile
   │
   ├── marca
   ├── modelo
   ├── bateria
   ├── memória
   ├── armazenamento
   ├── CPU
   └── IP
```

O `#connector` não precisa conhecer todas essas informações.

Ele apenas fornece a conexão necessária para que `#mobile` faça esse trabalho.

---

# Depuração sem fio

Em dispositivos Android compatíveis, uma conexão pode ser realizada utilizando ADB pela rede.

O Android fornece informações semelhantes a:

```text
IP
porta
```

Esses valores podem então ser utilizados:

```jls
va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)
```

É necessário que o dispositivo esteja autorizado corretamente.

---

# Autorização ADB

O Android possui um sistema de autorização para impedir que qualquer computador simplesmente consiga acessar o dispositivo.

Durante a primeira conexão, pode ser necessário aceitar uma solicitação de depuração no celular.

Sem autorização, o dispositivo pode aparecer como:

```text
unauthorized
```

Nesse caso, o `#connector` não trata aquela conexão como um dispositivo Android pronto para utilização.

---

# Dispositivo offline

Também pode ocorrer:

```text
offline
```

Isso significa que o ADB conhece o dispositivo, mas ele não está disponível corretamente para comunicação naquele momento.

Pode ser necessário reconectar o dispositivo ou verificar a configuração de depuração.

---

# Connection refused

Um dos erros possíveis é:

```text
Connection refused
```

Isso significa que o endereço foi encontrado, mas não existe um serviço aceitando aquela conexão na porta informada.

Por exemplo:

```jls
connector.adb(
    "192.168.1.2",
    5555
)
```

não funcionará simplesmente porque `5555` parece uma porta bonita.

A porta precisa corresponder àquela realmente utilizada pelo ADB no dispositivo.

---

# Timeout

Outro problema possível é o timeout.

```jls
va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)
```

Se a conexão não puder ser estabelecida dentro desse período, o JLScript encerra a tentativa.

Isso evita que uma aplicação fique esperando indefinidamente por um dispositivo que talvez nem esteja disponível.

---

# ADB instalado

Conexões ADB dependem da disponibilidade do Android Debug Bridge no computador.

O JLScript precisa conseguir localizar o executável responsável pela comunicação ADB.

Também pode ser utilizado o caminho configurado através da variável:

```text
JLS_ADB_PATH
```

Isso permite indicar explicitamente onde o ADB está instalado.

---

# Utilizando com #mobile

O exemplo mais comum atualmente é:

```jls
import [#connector, #mobile]

va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)

va celular = mobile.conectar(conexao)

mostrar(celular.marca())
mostrar(celular.modelo())
mostrar(celular.bateria())
```

Observe que:

```jls
connector.adb(...)
```

não retorna diretamente um celular.

Ele retorna uma **conexão**.

Depois:

```jls
mobile.conectar(conexao)
```

transforma essa conexão em uma interface de acesso ao Android.

---

# Separação entre conexão e dispositivo

Essa separação é intencional.

Seria possível colocar tudo dentro de:

```jls
mobile.conectar(...)
```

mas isso misturaria duas responsabilidades diferentes.

O JLScript utiliza:

```text
#connector
    ↓
como conectar?

#mobile
    ↓
o que fazer com o celular?
```

Isso permite que o sistema de conexões possa futuramente ser reutilizado por outras bibliotecas sem duplicar toda a lógica de comunicação.

---

# Exemplo completo

```jls
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

O fluxo é:

```text
connector.adb()
       │
       ▼
    conexão
       │
       ▼
mobile.conectar()
       │
       ▼
    celular
       │
       ▼
estatisticas()
```

---

# Responsabilidade do #connector

O `#connector` existe para centralizar a criação e gerenciamento de conexões.

Isso evita que cada biblioteca precise implementar novamente:

```text
endereços
portas
timeouts
protocolos
estado
autorização
conexão
```

Em vez disso:

```text
                #connector
                    │
              cria conexões
                    │
        ┌───────────┼───────────┐
        ▼           ▼           ▼
     #mobile      outros      futuras
                  módulos     bibliotecas
```

---

# Por que usar #connector?

O objetivo do `#connector` é separar **comunicação** de **funcionalidade**.

Um módulo não deveria precisar reconstruir toda a lógica necessária para encontrar e conectar a um dispositivo sempre que quiser utilizá-lo.

A biblioteca centraliza essa responsabilidade.

Assim:

```jls
va conexao = connector.adb(
    "192.168.1.2",
    38472,
    timeout = 20 seg
)
```

representa apenas:

> **Conecte-me a este dispositivo utilizando ADB.**

Depois disso, outras bibliotecas decidem o que fazer com essa conexão.

Essa arquitetura permite que o sistema de dispositivos do JLScript cresça mantendo protocolos, conexões e funcionalidades separados.