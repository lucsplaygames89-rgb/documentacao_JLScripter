# `jls update`

Verifica e instala atualizações oficiais do JLScript.

```powershell
jls update
jls update check
jls update --check
```

`check`/`--check` apenas verifica. Sem esse modo, uma instalação completa pode baixar e instalar a nova release.

Em uma cópia de desenvolvimento, o comando avisa que o executável local deve ser atualizado com:

```powershell
jls dev build
```

Existe ainda `--background`, utilizado internamente pela verificação em segundo plano.
