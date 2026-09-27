# #log

A biblioteca **`#log`** fornece registro de mensagens por nível, com suporte a console, arquivo e formatos configuráveis.

```jls
import #log
```

## Níveis

```jls
log.debug("Valor calculado")
log.info("Servidor iniciado")
log.aviso("Configuração ausente")
log.erro("Falha ao conectar")
```

Os níveis, do menor para o maior, são:

```text
debug → info → aviso → erro
```

## Arquivo

```jls
log.arquivo("app.log")
```

Depois disso, os registros podem ser gravados no arquivo configurado.

## Nível mínimo

```jls
log.nivel("info")
```

Com `info`, mensagens `debug` ficam abaixo do nível configurado.

## Formato

```jls
log.formato("texto")
```

A implementação atual também possui suporte ao formato estruturado aceito pelo módulo.

Cada chamada de log recebe a mensagem e pode receber um segundo valor de contexto conforme o contrato do módulo.

| Método | Função |
|---|---|
| `debug` | Registro de depuração |
| `info` | Informação |
| `aviso` | Aviso |
| `erro` | Erro |
| `arquivo` | Define arquivo de saída |
| `nivel` | Define nível mínimo |
| `formato` | Define formato |
