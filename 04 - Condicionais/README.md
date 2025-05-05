# 4. Condicionais

Estruturas condicionais são usadas para executar diferentes blocos de código com base em condições. As principais são `if` e `else`.

A sintaxe básica consiste em testar uma condição com `if`; se ela for verdadeira, um bloco de código é executado. Caso contrário, o código dentro do `else` é executado. No exemplo abaixo, a variável `idade` armazena o valor 18. O programa verifica se `idade` é maior ou igual a 18. Como essa condição é verdadeira, a mensagem "Você é maior de idade." será exibida no console. Caso o valor fosse menor, a mensagem "Você é menor de idade." seria exibida.

```
let idade = 18;

if (idade >= 18) {
  console.log("Você é maior de idade.");
} else {
  console.log("Você é menor de idade.");
}
```

Também é possível testar várias condições usando `else if`. No exemplo a seguir, a variável `nota` recebe o valor 7. O programa primeiro verifica se a nota é maior ou igual a 9; como não é, ele passa para a próxima condição, que verifica se a nota é maior ou igual a 6. Essa condição é verdadeira, então a mensagem "Aprovado." será exibida. Se nenhuma das condições fosse satisfeita, a mensagem "Reprovado." seria mostrada.

```
let nota = 7;

if (nota >= 9) {
  console.log("Excelente!");
} else if (nota >= 6) {
  console.log("Aprovado.");
} else {
  console.log("Reprovado.");
}
```

Essas estruturas permitem que o programa tome decisões com base em valores e condições lógicas.