# 7. Arrays

Arrays são estruturas de dados utilizadas para armazenar e organizar coleções de elementos. Cada elemento ocupa uma posição na memória e pode ser acessado por um número denominado índice, que inicia em zero. Os elementos de um array podem ser modificados, adicionados ou removidos conforme necessário.

Existem diferentes formas de declarar um array em JavaScript, sendo a mais comum a forma literal, como no exemplo:

```
var listaDeFrutas = ['Maçãs', 'Uvas', 'Bananas', 'Abacaxi', 'Morangos'];
```

Cada item é separado por vírgulas e sua posição no array é definida pelo índice, que começa em `0`. 

## 7.1. Acessando Elementos

Os elementos de um array podem ser acessados diretamente por seu índice:

```
var primeiroItem = listaDeFrutas[0]; // 'Maçãs'
var segundoItem = listaDeFrutas[1];  // 'Uvas'
```

Também é possível percorrer todos os elementos de um array utilizando estruturas de repetição, como `for`, `while` ou o método `forEach()`:

```
listaDeFrutas.forEach(function (item, indice) {
  console.log(item, indice);
});

// Maçãs 0
// Uvas 1
// Bananas 2
// Abacaxi 3
// Morangos 4
```

## 7.2. Tamanho do Array

O comprimento de um array pode ser obtido com a propriedade `.length`, da mesma forma que se obtém o número de caracteres de uma string:

```
for (var i = 0; i < listaDeFrutas.length; i++) {
  console.log(listaDeFrutas[i]);
}

// Maçãs
// Uvas
// Bananas
// Abacaxi
// Morangos
```

## 7.3. Conversão Entre Strings e Arrays

Em algumas situações, pode ser necessário converter uma string em um array, ou vice-versa.

**De string para array: `split()`**

O método `split()` separa uma string em partes, de acordo com um delimitador, no exemplo a seguir o delimitador utilizado é a vírgula:

```
var cidades = "Manchester,London,Liverpool,Birmingham,Leeds,Carlisle";
var separacao = cidades.split(",");
// ['Manchester', 'London', 'Liverpool', 'Birmingham', 'Leeds', 'Carlisle']
```

**De array para string: `join()` e `toString()`**

O método `join()` junta os elementos de um array em uma string, podendo especificar o separador:

```
var novaString = separacao.join(",");
// "Manchester,London,Liverpool,Birmingham,Leeds,Carlisle"
```

O método `toString()` também realiza essa conversão, mas utiliza vírgula como separador padrão e não aceita parâmetros:

```
var nomes = ["Rocket", "Flash", "Bella", "Slugger"];
nomes.toString(); // "Rocket,Flash,Bella,Slugger"
```

## 7.4. Adicionando e Removendo Elementos

Arrays permitem a adição e remoção de elementos tanto no início quanto no final da lista.

**Final do array**

- `push()`: adiciona um ou mais elementos ao final:

```
cidades.push("Cardiff", "Brighton");
```

- `pop()`: remove o último elemento:

```
var removeUltimo = cidades.pop();
```

**Início do array**

- `unshift()`: adiciona elementos no início:

```
cidades.unshift("Edinburgh");
```

- `shift()`: remove o primeiro elemento:

```
var removePrimeiro = cidades.shift();
```

**Localizando e removendo elementos por índice**

Para localizar o índice de um elemento específico, utiliza-se o método `indexOf()`:

```
var pos = listaDeFrutas.indexOf('Bananas'); // pos = 2
```

Para remover elementos com base no índice, utiliza-se o método `splice()`, onde o primeiro parâmetro é a posição inicial e o segundo, a quantidade de elementos a serem removidos:

```
listaDeFrutas.splice(pos, 1);
// Remove 'Bananas'
```

## 7.5. Métodos de Manipulação

A manipulação de arrays pode ser realizada de forma eficiente e legível por meio dos métodos `filter()`, `map()` e `reduce()`. Esses métodos pertencem ao paradigma da programação funcional e são amplamente utilizados para processar e transformar coleções de dados.

Para os exemplos a seguir, será utilizado o seguinte array de objetos, que representa informações sobre algumas `empresas`:

```
const empresas = [
  { nome: 'Samsung', valorDeMercado: 50, CEO: 'Kim Hyun Suk', anoDeCriacao: 1938 },
  { nome: 'Facebook', valorDeMercado: 383, CEO: 'Mark Zuckerberg', anoDeCriacao: 2004 },
  { nome: 'Spotify', valorDeMercado: 30, CEO: 'Daniel Ek', anoDeCriacao: 2006 },
];
```

**`filter()`**

O método `filter()` é utilizado para gerar um novo array contendo apenas os elementos que atendem a uma determinada condição. O array original permanece inalterado.

**Exemplo:** Filtrar as empresas fundadas após o ano 2000.

```
const recentes = empresas.filter(empresa => empresa.anoDeCriacao > 2000);
```

O array `recentes` conterá apenas os objetos correspondentes às empresas criadas após o ano de 2000: `Facebook` e `Spotify`.

**`map()`**

O método `map()` é utilizado para transformar os elementos de um array, aplicando uma função a cada item e retornando um novo array com os valores resultantes. O array original também não é modificado.

**Exemplo:** Gerar um array de strings contendo o nome da empresa e o nome de seu CEO.

```
const informacoes = empresas.map(empresa => `${empresa.nome} CEO: ${empresa.CEO}`);
```

**Resultado**

```
[
  'Samsung CEO: Kim Hyun Suk',
  'Facebook CEO: Mark Zuckerberg',
  'Spotify CEO: Daniel Ek'
]
```

**`reduce()`**

O método `reduce()` permite reduzir um array a um único valor, por meio da aplicação de uma função que opera sobre um acumulador e cada elemento do array. Esse valor pode ser numérico, textual, booleano, entre outros.

**Exemplo:** Calcular o valor total de mercado das empresas.:

```
const totalValorMercado = empresas.reduce((acumulador, empresa) => {
  return acumulador + empresa.valorDeMercado;
}, 0);
```

Nesse caso, `totalValorMercado` será igual a `463`, que corresponde à soma dos valores de mercado de todas as empresas.