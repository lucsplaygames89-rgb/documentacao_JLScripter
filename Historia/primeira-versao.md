# JLScript 1.0.0 — A primeira versão

A primeira versão oficial do JLScript foi a **1.0.0**.

Comparada ao projeto atual, ela era extremamente pequena.

Não existiam dezenas de bibliotecas nativas, banco de dados, APIs, interfaces, bytecode, ferramentas avançadas ou grande parte da infraestrutura que posteriormente seria adicionada ao projeto.

Mas a versão 1.0.0 tinha algo muito mais importante:

**ela funcionava.**

Foi a primeira versão em que o JLScript começou a possuir uma identidade real como linguagem de programação.

---

# O que existia na 1.0.0?

A primeira versão possuía apenas uma parte relativamente pequena daquilo que existe atualmente.

Entre os principais recursos estavam:

- `if`;
- `else`;
- funções;
- `switch`;
- `for`;
- loops básicos;
- execução de arquivos JLScript;
- um CLI inicial.

Não era uma linguagem completa.

Também não tentava ser.

A versão 1.0.0 representava principalmente a primeira base funcional do projeto.

---

# Condições

O JLScript já conseguia tomar decisões utilizando estruturas condicionais.

```jls
if (condicao) {
    mostrar("Verdadeiro")
} else {
    mostrar("Falso")
}