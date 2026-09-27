# `jls new` e `jls create`

Criam projetos JLScript.

```powershell
jls new <nome>
jls new pacote <nome>
jls new folder <nome>
jls create app <nome>
jls create aplicativo <nome>
```

`new <nome>` cria um projeto básico com `app.jls`. `pacote`/`folder` cria o arquivo principal, `jls.json`, README, licença e `.gitignore`. `app`/`aplicativo` cria um projeto visual com `app.jls`, pasta `assets/` e `jls.project` configurado para desktop/windows.

O template de aplicativo realmente importa:

```jls
import [#ui, #style]
```

O nome não pode conter `\\ / : * ? " < > |` e a pasta de destino não pode já existir.
