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
```

## 7.2. Tamanho do Array

O comprimento de um array pode ser obtido com a propriedade `.length`, da mesma forma que se obtém o número de caracteres de uma string:

```
var array = [1, 1, 2, 3, 5, 8, 13];
for (var i = 0; i < array.length; i++) {
  console.log(array[i]);
}
```