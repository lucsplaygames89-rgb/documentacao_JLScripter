# #crypto

A biblioteca **`#crypto`** reúne hashes, geração aleatória criptográfica, UUID, Base64, HMAC e criptografia AES.

```jls
import #crypto
```

## Hashes

```jls
va a = crypto.sha1("JLScript")
va b = crypto.sha256("JLScript")
va c = crypto.sha512("JLScript")
```

Os hashes são retornados em hexadecimal.

## UUID

```jls
va id = crypto.uuid()
```

A implementação gera UUID versão 4 usando bytes aleatórios.

## Bytes aleatórios

```jls
va aleatorio = crypto.random(32)
```

O tamanho precisa ser inteiro entre `0` e `1048576`. O resultado é codificado em Base64.

## Base64

```jls
va codificado = crypto.base64.codificar("Olá")
va original = crypto.base64.decodificar(codificado)
```

## HMAC SHA-256

```jls
va assinatura = crypto.hmac.sha256("mensagem", "segredo")
```

O resultado é hexadecimal.

## AES

Primeiro gere uma chave:

```jls
va chave = crypto.aes.chave()
```

Depois:

```jls
va pacote = crypto.aes.criptografar("mensagem secreta", chave)
va texto = crypto.aes.descriptografar(pacote, chave)
```

A chave gerada contém 32 bytes aleatórios codificados em Base64. A implementação valida a chave e o pacote antes de descriptografar.

| Recurso | Função |
|---|---|
| `sha1` | Hash SHA-1 |
| `sha256` | Hash SHA-256 |
| `sha512` | Hash SHA-512 |
| `uuid` | UUID v4 |
| `random` | Dados aleatórios seguros |
| `base64.codificar` | Codifica Base64 |
| `base64.decodificar` | Decodifica Base64 |
| `hmac.sha256` | HMAC SHA-256 |
| `aes.chave` | Gera chave AES |
| `aes.criptografar` | Criptografa |
| `aes.descriptografar` | Descriptografa |
