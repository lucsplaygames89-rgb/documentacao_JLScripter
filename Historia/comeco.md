# Por que o JLScript foi criado?

O **JLScript** começou a ser desenvolvido em **julho de 2026**, criado por **Lucas Aguiel Dos Santos De Oliveira**.

A linguagem nasceu durante meu aprendizado de programação.

Enquanto estudava e utilizava outras linguagens, principalmente JavaScript, comecei a perceber algumas coisas que, na minha visão, poderiam ser mais simples.

Foi daí que surgiu uma ideia:

> E se eu criasse uma linguagem que fosse mais simples de escrever, mais fácil de entender e que tivesse algumas regras diferentes das linguagens que eu estava aprendendo?

No início, o JLScript era uma experiência pessoal. Eu queria entender como uma linguagem de programação funcionava por dentro e, ao mesmo tempo, criar minhas próprias soluções para coisas que eu não gostava ou achava desnecessariamente complicadas em outras linguagens.

## Código mais fácil de entender

Uma das ideias do JLScript é permitir uma sintaxe simples e próxima da leitura humana.

Um exemplo básico:

```jls
va nome = "Lucas"

se (nome == "Lucas") {
    mostrar("Olá, Lucas!")
}
```

A intenção não é remover a lógica da programação.

A lógica continua existindo. O que muda é a forma de escrevê-la.

## Português e inglês

Outra ideia importante foi não obrigar a linguagem a existir somente em inglês.

O JLScript foi pensado para permitir programação em português e inglês.

Em português:

```jls
se (idade >= 18) {
    mostrar("Maior de idade")
} senao {
    mostrar("Menor de idade")
}
```

A ideia é que uma pessoa que está começando possa aprender conceitos de programação sem depender imediatamente de conhecer todos os termos utilizados em inglês.

## Menos código desnecessário

O JLScript também tenta remover partes da sintaxe quando elas podem ser entendidas automaticamente pela própria linguagem.

Um exemplo é o `switch`.

Em várias linguagens, cada `case` normalmente precisa ser encerrado explicitamente com `break`.

No JLScript, a proposta é diferente.

```jls
switch (opcao) {
    case 1 {
        mostrar("Cadastrar")
    }

    case 2 {
        mostrar("Entrar")
    }

    default {
        mostrar("Opção inválida")
    }
}
```

Não é necessário escrever:

```jls
break
```

O próprio bloco:

```jls
{
    ...
}
```

delimita aquele `case`.

Quando o bloco termina, aquele caso também termina.

Isso evita escrever uma instrução apenas para informar algo que a própria estrutura do código já consegue representar.

## Uma linguagem criada enquanto eu aprendia

O JLScript não nasceu porque eu já sabia tudo sobre compiladores ou construção de linguagens.

Foi praticamente o contrário.

Eu comecei a criá-lo porque queria aprender.

Para implementar uma variável, precisei entender melhor como variáveis funcionam.

Para criar funções, precisei entender como chamadas, parâmetros, escopos e retornos funcionam.

Para criar condições e estruturas como `switch`, precisei entender como uma linguagem interpreta e controla o fluxo de execução.

Com isso, o JLScript passou a ter dois objetivos ligados entre si:

**facilitar a programação e aprender como a programação funciona por dentro.**

## O começo de algo maior

O que começou como uma experiência foi crescendo.

Novas estruturas foram adicionadas, o interpretador evoluiu e começaram a surgir ferramentas e bibliotecas ao redor da linguagem.

A ideia deixou de ser apenas:

> "Vou criar minha própria sintaxe."

E passou a ser:

> "Vou construir uma linguagem de programação completa."

O JLScript continua evoluindo com esse princípio: manter aquilo que é necessário para programar, mas procurar maneiras mais simples e naturais de representar essas ideias.