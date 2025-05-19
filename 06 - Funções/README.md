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

````
function ola(nome, sobrenome) {
  console.log('Olá', nome, sobrenome)
}

ola('Fulano', 'Silva') // Olá Fulano Silva
ola('Silva', 'Fulano') // Olá Silva Fulano
```