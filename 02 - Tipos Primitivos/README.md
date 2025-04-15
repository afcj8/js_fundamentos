# 2. Tipos Primitivos

Em JavaScript, os tipos primitivos são os tipos de dados mais básicos e fundamentais. Eles representam valores simples e imutáveis, ou seja, não são objetos e não possuem métodos ou propriedades mutáveis (embora possam temporariamente se comportar como objetos). Esses tipos são armazenados diretamente na variável, diferentemente dos tipos por referência, como objetos e arrays. JavaScript possui sete tipos primitivos: `string`, `number`, `bigint`, `boolean`, `undefined`, `null` e `symbol`.

## 2.1. string

O tipo `string` representa uma sequência de caracteres usada para armazenar texto. Pode ser definida com aspas simples (`'...'`), duplas (`"..."`) ou crases (<code>&#96;...&#96;</code>) para permitir template literals (interpolação de variáveis).

```
let nome = "João";
let saudacao = `Olá, ${nome}!`; // Olá, João!
```

A interpolação de variáveis permite inserir o valor de uma variável ou expressão dentro de uma `string`. Para isso, utiliza-se a sintaxe `${...}` dentro de uma `string` com crases. No exemplo acima, `${nome}` é substituído pelo valor da variável `nome`.

## 2.2. number

O tipo `number` representa números inteiros e de ponto flutuante. JavaScript não diferencia entre inteiros e decimais: ambos são do tipo `number`.

```
let idade = 30;
let altura = 1.75;
```