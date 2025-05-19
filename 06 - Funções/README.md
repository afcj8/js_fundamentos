# 6. Funções

Funções são blocos de código reutilizáveis que podem receber entradas (parâmetros) e retornar saídas. Elas ajudam a organizar melhor o código, evitar repetições e tornar a programação mais modular.

## 6.1. Função Declarada (Function Declaration)

A forma mais básica de definir funções em JavaScript é por meio da function declaration. Esse tipo de função começa com a palavra reservada obrigatória `function`, seguida por um nome (também obrigatório), uma lista de parâmetros (opcional) entre parênteses, e um bloco de código entre chaves que define o corpo da função.

**Sintaxe básica**

```
function nomeDaFuncao() {
  // instruções
}
```

Funções declaradas podem receber parâmetros, separados por vírgula, dentro dos parênteses. Esses parâmetros tornam a função mais flexível e reutilizável:

```
function ola(nome) {
  console.log('Olá', nome)
}
ola('Fulano')
```

É possível declarar uma função dentro de outra. Nesse caso, a função interna só estará disponível dentro do escopo (bloco `{}`) da função onde foi declarada:

```
function ola() {
  function mensagem() {
    return 'Olá'
  }
  console.log(mensagem())
}
ola()
```

Tentar acessar a função interna fora do escopo da função pai resultará em erro:

```
console.log(mensagem()) 
// Erro: mensagem is not defined
// A função "mensagem" só existe dentro do escopo da função "ola"
```

A ordem dos parâmetros influencia diretamente o resultado da função. Por exemplo:

```
function ola(nome, sobrenome) {
  console.log('Olá', nome, sobrenome)
}

ola('Fulano', 'Silva') // Olá Fulano Silva
ola('Silva', 'Fulano') // Olá Silva Fulano
```

## 6.2. Função Anônima (Function Expression)

Uma função anônima é uma função sem nome atribuída a uma variável. Essa abordagem é chamada de function expression, e sua principal característica é que a função só pode ser utilizada após sua definição, ao contrário da declaração de função tradicional, que pode ser chamada antes.

```
const saudacao = function(nome) {
  return `Olá, ${nome}`
}

console.log(saudacao('Fulano')) // Olá, Fulano
```

A expressão `function(nome) {...}` representa uma função anônima, ou seja, uma função que não possui nome declarado. Nesse caso, ela é atribuída à variável `saudacao`, que passa a se comportar como uma função. Para utilizá-la, basta invocar o nome da variável seguido por parênteses.

**Diferenças em relação à declaração de função**

- Funções declaradas (function declaration) são elevadas pelo mecanismo de hoisting, ou seja, podem ser chamadas antes mesmo de sua definição no código.
- Já as expressões de função (function expression), inclusive as funções anônimas atribuídas a variáveis, não são elevadas. Nesse caso, a função só pode ser utilizada após a linha em que foi definida:

```
teste() // Erro: Cannot access 'teste' before initialization

const teste = function() {
  console.log('Função anônima')
}
```