# 1. Variáveis

Variáveis são usadas para armazenar dados que podem ser utilizados e manipulados ao longo do programa. Em JavaScript, é possível declarar variáveis usando três palavras-chave principais: `var`, `let` e `const`. Cada uma possui características específicas quanto ao escopo, à possibilidade de alteração do valor e ao comportamento durante a execução do código.

## 1.1. var

A palavra-chave `var` foi a forma tradicional de declarar variáveis desde as primeiras versões do JavaScript. As variáveis declaradas com `var` possuem escopo de função, ou seja, elas são visíveis dentro da função onde foram definidas, independentemente do bloco em que se encontram. Além disso, podem ser redeclaradas e têm seu comportamento influenciado pelo _hoisting_, que move a declaração para o topo do escopo, atribuindo automaticamente o valor `undefined` até que seja inicializada.

```
function exemploVar() {
  if (true) {
    var linguagem = "JavaScript";
  }
  console.log(linguagem); // JavaScript
}
```