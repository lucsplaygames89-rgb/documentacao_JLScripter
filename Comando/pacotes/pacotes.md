# Comandos de pacote

O JLShell possui uma forma especial de comando em que o **primeiro argumento é o nome do pacote**.

## Atualizar metadados

```powershell
jls <pacote> update
```

Localiza o fonte do pacote, lê seus metadados e grava/atualiza `pacote.json`. Depois tenta atualizar o conhecimento da JLS AI.

## Publicar/validar

```powershell
jls <pacote> publish
```

Na implementação atual, `publish`:

1. localiza o pacote;
2. atualiza `pacote.json`;
3. executa o lint do fonte;
4. compila bytecode `.jlb` em `build/`;
5. informa que o pacote foi validado e compilado.

Não há envio para um registry remoto nessa rotina atual.

## Ver versão/metadados

```powershell
jls <pacote> --version
```

Mostra nome, versão, autor e descrição lidos do fonte.

## Como o pacote é localizado

Para `<pacote>`, o JLShell procura formas como:

```text
<pacote>/<pacote-em-minusculo>.jls
<pacote>/<pacote>.jls
<pacote-em-minusculo>.jls
```
