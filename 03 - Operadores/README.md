# 3. Operadores

Em JavaScript, operadores são usados para executar operações sobre valores, variáveis ou expressões. Eles permitem desde cálculos matemáticos até comparações lógicas e atribuição de valores. 

## 3.1. Operadores Aritméticos

Os operadores aritméticos são utilizados para realizar operações matemáticas simples, como soma, subtração e multiplicação. Esses operadores sempre retornam um novo valor com base na operação realizada.

- `+` → adição (ou concatenação de strings)

```
let soma = 5 + 3; // 8
let texto = "Olá, " + "mundo!"; // "Olá, mundo!"
```

- `-` → subtração

```
let resultado = 10 - 4; // 6
```

- `*` → multiplicação

```
let produto = 6 * 7; // 42
```

- `/` → divisão

```
let divisao = 20 / 4; // 5
```

- `%` → módulo (resto da divisão)

```
let resto = 10 % 3; // 1
```

- `**` → exponenciação

```
let potencia = 2 ** 3; // 8 (2 elevado à 3ª potência)
```

## 3.2. Operadores de Atribuição

Os operadores de atribuição são usados para atribuir valores a variáveis. O mais comum é o sinal de igual (`=`), mas também existem formas encurtadas para aplicar operações aritméticas junto da atribuição.

- `=` → atribuição simples

```
let x = 10;
```

- `+=` → soma e atribuição

```
x += 5; // equivale a x = x + 5
```

- `-=` → subtração e atribuição

```
x -= 3; // equivale a x = x - 3
```

- `*=` → multiplicação e atribuição

```
x *= 2; // equivale a x = x * 2
```

- `/=` → divisão e atribuição

```
x /= 4; // equivale a x = x / 4
```

- `%=` → módulo e atribuição

```
x %= 2; // equivale a x = x % 2
```

- `**=` → exponenciação e atribuição

```
x **= 2; // equivale a x = x ** 2
```

## 3.3. Operadores de Comparação

Os operadores de comparação comparam dois valores e retornam um resultado booleano: `true` ou `false`. São comumente usados em instruções `if`, `while`, expressões ternárias, etc.

- `==` → igualdade de valor, com conversão de tipo (coerção implícita)

```
5 == "5" // true
```

- `===` → igualdade estrita (valor e tipo)

```
5 === "5" // false
```

- `!=` → diferença de valor, com conversão de tipo

```
10 != "10" // false
```

- `!==` → diferença estrita

```
10 !== "10" // true
```

- `>` → maior que

```
8 > 5 // true
```

- `<` → menor que

```
3 < 9 // true
```

- `>=` → maior ou igual

```
7 >= 7 // true
```

- `<=` → menor ou igual

```
4 <= 5 // true
```