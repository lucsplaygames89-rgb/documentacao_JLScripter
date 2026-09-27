# Comandos do JLScript

Esta pasta documenta os comandos realmente implementados no JLShell/CLI no `src` analisado em 26/09/2026.

## Formas básicas

```powershell
jls
jls <arquivo.jls> [-- argumentos]
jls <comando> [opções]
```

Executar `jls` sem argumentos abre o REPL. Um arquivo `.jls` também pode ser executado diretamente com `jls app.jls`.

## Opções globais

| Opção | Função |
|---|---|
| `-h`, `--help`, `help` | Mostra ajuda |
| `-v`, `--version`, `version` | Mostra a versão do JLScript |
| `--no-color` | Desativa cores ANSI |
| `--verbose` | Exibe diagnóstico interno adicional |

`--no-color` e `--verbose` são processados antes do comando.

## Comandos implementados

### Execução e projeto
- [`run`](execucao/run.md)
- [`repl`](execucao/repl.md)
- [`new` / `create`](projeto/new-create.md)
- [`init`](projeto/init.md)
- [`preview`](projeto/preview.md)

### Build e bytecode
- [`targets`](build/targets.md)
- [`build`](build/build.md)
- [`clean`](build/clean.md)
- [`compile`](build/compile.md)
- [`verify-bytecode`](build/verify-bytecode.md)

### Qualidade
- [`test`](qualidade/test.md) — relacionado a `#test`
- [`fmt`](qualidade/fmt.md)
- [`lint`](qualidade/lint.md)
- [`fix`](qualidade/fix.md)

### Ambiente e configuração
- [`doctor`](ambiente/doctor.md)
- [`config`](ambiente/config.md)
- [`update`](ambiente/update.md)

### JLS AI
- [`ai`](ai/ai.md)

### Desenvolvimento de linguagens
- [`language`](compiler/language.md) — depende de definições criadas com `#compiler`

### Desenvolvimento do próprio JLScript
- [`dev`](desenvolvimento/dev.md)
- [`selfhost`](desenvolvimento/selfhost.md)

### Pacotes
- [`<pacote> update`](pacotes/pacotes.md)
- [`<pacote> publish`](pacotes/pacotes.md)
- [`<pacote> --version`](pacotes/pacotes.md)

### Biblioteca `#cli`
- [`#cli`](bibliotecas/cli.md) permite que um programa JLScript crie seus próprios comandos e opções. Ela não adiciona novos comandos globais ao `jls`.

## Comandos que dependem de biblioteca

Nem todo comando do terminal exige `import`.

| Comando | Dependência comprovada no código |
|---|---|
| `jls test` | Descobre apenas `tests/**/*.test.jls` cujo fonte contém `#test` |
| `jls language ...` | Carrega definição criada pelo LDK; a própria ajuda informa `import #compiler` + `lang.build()` |
| `jls run ... -- ...` + programa com `#cli` | Os argumentos após `--` são entregues ao `#cli` do programa |

Os demais comandos desta documentação são recursos do próprio JLShell, salvo indicação específica.
