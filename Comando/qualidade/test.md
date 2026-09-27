# `jls test`

Executa os testes oficiais do projeto.

```powershell
jls test
```

## Dependência de `#test`

Este é um caso em que a biblioteca importa diretamente para o comportamento do terminal.

O runner procura recursivamente dentro de:

```text
tests/
```

por arquivos terminados em:

```text
.test.jls
```

Porém, **só executa o arquivo se o próprio fonte contiver `#test`**. Isso evita executar fixtures auxiliares que tenham o mesmo sufixo.

Exemplo de arquivo descoberto:

```jls
import #test
```

Se `tests/` não existir, o comando encerra sem erro. Se nenhum `*.test.jls` com `#test` for encontrado, também encerra normalmente.
