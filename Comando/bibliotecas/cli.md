# `#cli` e os argumentos do terminal

`#cli` é uma biblioteca nativa para um **programa JLScript criar sua própria interface de linha de comando**.

Ela não registra novos comandos globais como `jls build` ou `jls test`.

## Importação

```jls
import #cli
```

## Criar aplicativo CLI

A função disponível no módulo é:

```jls
va app = cli.criar("meuapp")
```

O objeto criado possui os métodos:

```text
comando
arg
flag
versao
executar
```

## Como recebe argumentos

Os argumentos são passados pelo `jls run` depois do separador `--`:

```powershell
jls run app.jls -- comando --porta 3000
```

O JLShell guarda `comando --porta 3000` e o `#cli` lê esses valores quando `app.executar()` é chamado.

## Comandos

`app.comando(nome, callback)` registra um comando. O callback recebe um objeto com as opções processadas e uma lista `posicionais`.

## Argumentos e flags

```text
app.arg(nome, configuração)
app.flag(nome, configuração)
```

A configuração de `arg` pode usar:

```text
tipo
descricao
padrao
```

Tipos convertidos explicitamente pela implementação:

```text
int
float
bool
str (padrão)
```

`bool` considera verdadeiros `true`, `1` e `sim`.

## Recursos automáticos

Um app `#cli` reconhece automaticamente:

```text
--help
--version
```

`--version` exige que uma versão tenha sido configurada com `app.versao(...)`.

As opções do app usam formato longo `--nome`; a implementação também aceita `--nome=valor` para argumentos que recebem valor.
