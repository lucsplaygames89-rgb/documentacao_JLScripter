# #env

A biblioteca **`#env`** trabalha com variáveis de ambiente do processo e também pode carregar arquivos no formato `.env`.

```jls
import #env
```

## Ler uma variável

```jls
va valor = env.get("APP_ENV")
```

Se a variável não existir, `get()` retorna `null`.

## Verificar existência

```jls
se (env.tem("TOKEN")) {
    mostrar("TOKEN configurado")
}
```

## Definir e remover

```jls
env.set("APP_ENV", "development")
env.remover("APP_ENV")
```

As duas operações retornam `true` quando concluídas.

## Carregar `.env`

```jls
va quantidade = env.carregar(".env")
```

O arquivo pode conter:

```text
APP_ENV=development
PORT=3000
TOKEN="abc123"
```

Linhas vazias e linhas iniciadas por `#` são ignoradas. `carregar()` retorna quantas variáveis foram carregadas.

| Método | Função |
|---|---|
| `get(nome)` | Lê uma variável |
| `tem(nome)` | Verifica se existe |
| `set(nome, valor)` | Define ou substitui |
| `remover(nome)` | Remove |
| `carregar(caminho)` | Carrega um arquivo `.env` |
