# 5. Repetição

As estruturas de repetição (ou laços de repetição) são usadas para executar um bloco de código várias vezes, com base em uma condição. JavaScript oferece diversas formas de fazer isso, cada uma adequada a diferentes situações.

## 5.1. for

A estrutura `for` é usada quando se sabe previamente quantas vezes o código deve ser executado. Sua sintaxe permite inicializar variáveis, definir a condição de execução e o incremento, tudo em uma única linha.

**Sintaxe**

```
for ([inicialização]; [condição]; [expressão final])
  declaração
```

- **inicialização:** Uma expressão executada uma única vez, antes do início do loop. Costuma ser usada para declarar e iniciar a variável de controle.

- **condição:** Avaliada antes de cada iteração. Se o resultado for `true`, o bloco será executado; se for `false`, o loop será encerrado.

- **expressão final:** Executada ao fim de cada iteração. Normalmente usada para atualizar o valor da variável de controle.

- **declaração:** O bloco de código a ser executado. Para incluir mais de uma instrução, deve-se usar chaves `{ ... }`.

**Exemplo**

```
for (let i = 0; i < 5; i++) {
  console.log("Valor de i:", i);
}

// Saída
// Valor de i: 0
// Valor de i: 1
// Valor de i: 2
// Valor de i: 3
// Valor de i: 4
```

## 5.2. while

A estrutura `while` executa um bloco de código enquanto a condição especificada for verdadeira. A verificação ocorre antes da execução, ou seja, o bloco pode não ser executado nenhuma vez, caso a condição já seja falsa no início.

**Sintaxe**

```
while (condição)
  declaração
```

- **condição:** Avaliada antes de cada repetição. O loop continua enquanto a condição for verdadeira.

- **declaração:** Código que será executado repetidamente. Se houver várias instruções, deve-se utilizar chaves `{ ... }`.

**Exemplo**

```
let i = 0;
while (i < 3) {
  console.log("Contando:", i);
  i++;
}

// Saída
// Contando: 0
// Contando: 1
// Contando: 2
```

## 5.3. do...while

A estrutura `do...while` é semelhante ao `while`, mas garante que o bloco de código será executado ao menos uma vez, pois a verificação da condição ocorre após a execução.

**Sintaxe**

```
do {
  declaração
} while (condição);
```

- **declaração:** Código executado antes da verificação da condição.

- **condição:** Avaliada após cada execução. Enquanto for verdadeira, o bloco continua a ser executado.

**Exemplo**

```
let i = 0;
do {
  console.log("Executando pelo menos uma vez:", i);
  i++;
} while (i < 2);

// Saída
// Executando pelo menos uma vez: 0
// Executando pelo menos uma vez: 1
```

## 5.4. for...in

A estrutura `for...in` percorre todas as propriedades enumeráveis de um objeto. É ideal para iterar sobre objetos, mas não é recomendada para arrays, pois a ordem dos índices nem sempre é garantida.

**Sintaxe**

```
for (variável in objeto)
  declaração
```

- **variável:** Recebe o nome da chave (propriedade) a cada iteração.

- **objeto:** Objeto cujas propriedades serão percorridas.

- **declaração:** Bloco de código executado para cada chave encontrada.

**Exemplo**

```
const pessoa = { nome: "Ana", idade: 30 };

for (let chave in pessoa) {
  console.log(chave + ":", pessoa[chave]);
}

// Saída
// nome: Ana
// idade: 30
```

## 5.5. for...of

A estrutura `for...of` percorre os valores de objetos iteráveis, como arrays, strings, Map, Set e outros. É ideal para percorrer arrays de forma clara e direta.

**Sintaxe**

```
for (variável of iterável)
  declaração
```

- **variável:** Recebe, a cada iteração, o valor atual do item do iterável.

- **iterável:** Objeto com suporte à iteração (como arrays e strings).

- **declaração:** Código executado para cada item do iterável.

**Exemplo**

```
const frutas = ["maçã", "banana", "uva"];

for (let fruta of frutas) {
  console.log(fruta);
}

// Saída
// maçã
// banana
// uva
```

## 5.6. forEach

O `forEach` é um método de arrays usado para executar uma função para cada item. É muito usado em situações em que se deseja aplicar uma função a todos os elementos de um array.

> ⚠️ **Importante:** `forEach` **não pode ser interrompido** com `break` ou `continue`.

**Sintaxe**

```
array.forEach(function(elemento, índice, array) {
  declaração
});
```

- **elemento:** O valor atual do array.

- **índice (opcional):** A posição do elemento atual.

- **array (opcional):** O próprio array sendo percorrido.

- **declaração:** Código que será executado para cada elemento.

**Exemplo**

```
const numeros = [10, 20, 30];

numeros.forEach(function(valor, indice) {
  console.log(`Índice ${indice}: ${valor}`);
});

// Saída
// Índice 0: 10
// Índice 1: 20
// Índice 2: 30
```