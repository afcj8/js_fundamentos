# 3. Operadores

Em JavaScript, operadores são usados para executar operações sobre valores, variáveis ou expressões. Eles permitem desde cálculos matemáticos até comparações lógicas e atribuição de valores. 

## 3.1. Operadores Aritméticos

Os operadores aritméticos são utilizados para realizar operações matemáticas simples, como soma, subtração e multiplicação. Esses operadores sempre retornam um novo valor com base na operação realizada.

| Operador | Descrição              | Exemplo         | Resultado     |
| -------- | ---------------------- | --------------- | ------------- |
| +        | Adição ou concatenação | 5 + 3           | 8             |
| -        | Subtração              | 10 - 4          | 6             |
| *        | Multiplicação          | 6 * 7           | 42            |
| /        | Divisão                | 20 / 4          | 5             |
| %        | Módulo (resto)         | 10 % 3          | 1             |
| **       | Exponenciação          | 2 ** 3          | 8             |

## 3.2. Operadores de Atribuição

Os operadores de atribuição são usados para atribuir valores a variáveis. O mais comum é o sinal de igual (`=`), mas também existem formas encurtadas para aplicar operações aritméticas junto da atribuição.

| Operador | Descrição                  | Exemplo       | Equivale a     |
| -------- | -------------------------- | ------------- | -------------- |
| =        | Atribuição simples         | x = 10        | x = 10         |
| +=       | Soma e atribuição          | x += 5        | x = x + 5      |
| -=       | Subtração e atribuição     | x -= 3        | x = x - 3      |
| *=       | Multiplicação e atribuição | x *= 2        | x = x * 2      |
| /=       | Divisão e atribuição       | x /= 4        | x = x / 4      |
| %=       | Módulo e atribuição        | x %= 2        | x = x % 2      |
| **=      | Exponenciação e atribuição | x **= 2       | x = x ** 2     |

## 3.3. Operadores de Comparação

Os operadores de comparação comparam dois valores e retornam um resultado booleano: `true` ou `false`. São comumente usados em instruções `if`, `while`, expressões ternárias, etc.

| Operador | Descrição                              | Exemplo       | Resultado |
| -------- | -------------------------------------- | ------------- | --------- |
| ==       | Igualdade de valor (com conversão)     | 5 == "5"      | true      |
| ===      | Igualdade estrita (valor e tipo)       | 5 === "5"     | false     |
| !=       | Diferença de valor (com conversão)     | 10 != "10"    | false     |
| !==      | Diferença estrita                      | 10 !== "10"   | true      |
| >        | Maior que                              | 8 > 5         | true      |
| <        | Menor que                              | 3 < 9         | true      |
| >=       | Maior ou igual                         | 7 >= 7        | true      |
| <=       | Menor ou igual                         | 4 <= 5        | true      |

A diferença entre `==` e `===` é essencial em JavaScript. O operador `==` compara apenas o valor, convertendo os tipos automaticamente (por exemplo, número e string), enquanto o `===` compara valor e tipo, sem realizar conversões.