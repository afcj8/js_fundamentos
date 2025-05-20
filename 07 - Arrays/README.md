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