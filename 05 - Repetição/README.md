# 5. Repetição

As estruturas de repetição (ou laços de repetição) são usadas para executar um bloco de código várias vezes, com base em uma condição. JavaScript oferece diversas formas de fazer isso, cada uma adequada a diferentes situações.

## 5.1. for

Usado quando se sabe exatamente quantas vezes o bloco deve ser executado.

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