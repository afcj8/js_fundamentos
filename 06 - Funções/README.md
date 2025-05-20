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

## 6.3. Função de Seta (Arrow Function)

As arrow functions foram introduzidas no ES6 e oferecem uma forma mais concisa de declarar funções. Elas utilizam o símbolo `=>` no lugar da palavra-chave `function` e não possuem seu próprio `this`, herdando o contexto léxico onde foram definidas.

```
const saudacao = (nome) => {
  return `Olá, ${nome}`
}
```

Essa sintaxe é especialmente útil para funções curtas, como callbacks e funções simples de transformação. Em expressões de linha única, onde a função retorna algo diretamente, as chaves `{}` e a palavra `return` podem ser omitidas:

```
const quadrado = x => x * x;
console.log(quadrado(4)) // 16
```

**Regras e observações**

- Se houver apenas um parâmetro, os parênteses podem ser omitidos.
- Se nenhum parâmetro for passado, os parênteses são obrigatórios:

```
const ola = () => 'Olá!';
```

- Para retornar um objeto literal, é necessário envolvê-lo entre parênteses, evitando ambiguidade com o corpo da função:

```
const criarUsuario = () => ({ nome: 'Fulano', idade: 30 });
```

## 6.4. Função Construtora (Functions constructor)

Funções construtoras são usadas para criar múltiplos objetos com a mesma estrutura. Por convenção, seus nomes começam com letra maiúscula, e devem ser chamadas com a palavra-chave `new`.

```
function Pessoa(nome, idade) {
  this.nome = nome;
  this.idade = idade;
}
```

Ao utilizar `new Pessoa(...)`, um novo objeto é criado, e o this dentro da função passa a se referir a esse novo objeto. Isso permite definir propriedades e comportamentos específicos para cada instância criada:

```
const pessoa1 = new Pessoa('Fulano', 25)
console.log(pessoa1.nome) // Fulano
```

## 6.5. Função Geradora (Generator Function)

Funções geradoras são uma forma especial de função que podem pausar e retomar sua execução. Sua sintaxe se assemelha à de funções normais, com a diferença de que é necessário adicionar um asterisco (`*`) logo após a palavra-chave `function`:

```
function* ola(p1, p2) {}
```

Assim como nas funções tradicionais, os parênteses e chaves são obrigatórios. Os parâmetros continuam sendo opcionais e separados por vírgula.

A principal característica das funções geradoras é o uso da palavra-chave `yield`, que define os pontos de pausa na execução da função. Cada vez que a função é chamada usando `.next()`, ela continua a partir do último `yield`.

```
function* ola() {
    yield 'Olá'
    yield 'Fulano'
    yield 'Silva'
}
```

Ao invocar uma função geradora, ela não executa imediatamente. Em vez disso, retorna um objeto do tipo Generator, que implementa o protocolo de iteração com o método `.next()`:

```
const nome = ola();

const n1 = nome.next();
console.log(n1); // { value: 'Olá', done: false }
```

Cada chamada a `.next()` retorna um objeto com duas propriedades:

- `value`: o valor retornado pelo `yield`.
- `done`: um booleano que indica se a função já terminou sua execução.

Como a função `ola()` possui três `yield`, podemos chamá-la três vezes:

```
const nome = ola();

console.log(nome.next()); // { value: 'Olá', done: false }
console.log(nome.next()); // { value: 'Fulano', done: false }
console.log(nome.next()); // { value: 'Silva', done: false }
console.log(nome.next()); // { value: undefined, done: true }
```

Caso não precise controlar a execução manualmente, é possível percorrer todos os valores usando o `for...of`. Esse laço já lida com o `done` internamente:

```
function* ola() {
  yield 'Olá';
  yield 'Fulano';
  yield 'Silva';
}

for (const n of ola()) {
  console.log(n);
}
```

O `for...of` percorre automaticamente todos os valores gerados até o fim da função, tornando o código mais simples e legível.

As generator functions são úteis em situações que exigem controle sobre o fluxo da execução, como no caso de percorrer listas grandes sob demanda ou implementar iteradores personalizados.