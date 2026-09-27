# `jls preview`

Abre o **JLScript Device Preview** para um aplicativo.

```powershell
jls preview [app.jls] [opções]
```

## Opções implementadas

| Inglês | Português | Valor |
|---|---|---|
| `--device` | `--dispositivo` | tipo de dispositivo |
| `--platform` | `--sistema` | plataforma |
| `--orientation` | `--orientacao` | orientação |
| `--width` | `--largura` | largura |
| `--height` | `--altura` | altura |
| `-w`, `--watch` | — | reconhecido, mas indisponível atualmente |

Exemplo:

```powershell
jls preview app.jls --device mobile --platform android --orientation portrait --width 390 --height 844
```

O preview não é um emulador Android/iOS. Quando opções não são informadas, o comando pode aproveitar valores de `jls.project`.

`--watch` existe no parser, mas atualmente retorna `PreviewWatchUnavailable` porque a janela ainda não é preservada/recriada com segurança.
