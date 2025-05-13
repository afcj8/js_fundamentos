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

## 5.2. while

Executa o bloco enquanto a condição for verdadeira. A verificação é feita antes de cada execução.

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

Semelhante ao `while`, mas executa o bloco pelo menos uma vez, pois a condição é verificada depois da execução.

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

Percorre as propriedades enumeráveis de um objeto. Ideal para objetos, não arrays.

```
const pessoa = { nome: "Ana", idade: 30 };

for (let chave in pessoa) {
  console.log(chave + ":", pessoa[chave]);
}

// Saída
// nome: Ana
// idade: 30
```