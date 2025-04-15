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

## 1.2. let

Com a chegada do ES6, a palavra-chave `let` foi introduzida para permitir declarações com escopo de bloco, ou seja, a variável só existe dentro do par de chaves `{}` onde foi definida. Isso evita comportamentos inesperados, especialmente em estruturas como `for`, `if` e funções anônimas. Diferente do `var`, o `let` não permite que a variável seja redeclarada no mesmo escopo.

```
if (true) {
  let linguagem = "JavaScript";
  console.log(linguagem); // JavaScript
}
// console.log(linguagem); // Erro: linguagem is not defined
```

## 1.3. const

Também introduzido no ES6, o `const` serve para declarar variáveis cujo valor não pode ser reatribuído. Assim como o `let`, possui escopo de bloco. No entanto, quando `const` é usado para declarar objetos ou arrays, suas propriedades internas ainda podem ser modificadas, desde que a referência original não mude.

```
const linguagem = "JavaScript";
// linguagem = "Python"; // Erro: Assignment to constant variable

const pessoa = { nome: "João" };
pessoa.nome = "Maria"; // Isso é permitido
```

Por fim, é importante lembrar que JavaScript é uma linguagem case-sensitive, o que significa que diferencia letras maiúsculas de minúsculas. Assim, variáveis chamadas `nome`, `Nome` e `NOME` são distintas entre si. Além disso, por utilizar o conjunto de caracteres Unicode, é possível usar acentos e até caracteres de outros idiomas ou alfabetos nos nomes de variáveis, como no caso da palavra `Früh`, que significa “cedo” em alemão:

```
let Früh = "Bom dia";
let fruh = "Boa tarde";

console.log(Früh); // Bom dia
console.log(fruh); // Boa tarde
```

Essa flexibilidade amplia a expressividade do código, mas requer atenção para evitar erros causados por nomes semelhantes.