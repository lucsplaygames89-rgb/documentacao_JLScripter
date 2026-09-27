# #json

A biblioteca nativa **`#json`** converte dados entre JSON e valores do JLScript. Ela é útil para APIs, configurações, arquivos e qualquer integração que troque dados estruturados.

## Importação

```jls
import #json
```

## `json.parsear()` / `json.parse()`

Recebem exatamente um texto JSON e retornam o valor equivalente no JLScript.

```jls
va usuario = json.parse("{\"nome\":\"Lucas\",\"idade\":20}")
mostrar(usuario.nome)
```

Objetos viram objetos JLScript, arrays viram listas, strings viram textos, números viram números, booleanos continuam booleanos e `null` continua `null`.

## `json.stringificar()` / `json.stringify()`

Fazem o caminho inverso: recebem um valor JLScript e devolvem texto JSON.

```jls
va dados = { nome: "Lucas", linguagem: "JLScript" }
va texto = json.stringify(dados)
mostrar(texto)
```

## `json.validar()`

Verifica se um texto contém JSON válido e retorna um booleano.

```jls
mostrar(json.validar("{\"ok\":true}"))
```

## Métodos

| Método | Função |
|---|---|
| `parsear(texto)` | Analisa JSON e retorna um valor JLScript |
| `parse(texto)` | Alias de `parsear` |
| `stringificar(valor)` | Serializa um valor para JSON |
| `stringify(valor)` | Alias de `stringificar` |
| `validar(texto)` | Retorna se o JSON é válido |

## Exemplo com #api

```jls
import [#api, #json]

va resposta = api.consultar("https://exemplo.com/dados")

se (json.validar(resposta.corpo)) {
    va dados = json.parse(resposta.corpo)
    mostrar(dados)
}
```

`#json` tem uma responsabilidade pequena e direta: **JSON ↔ JLScript**. Isso é uma vantagem, não falta de função enfeitada.
