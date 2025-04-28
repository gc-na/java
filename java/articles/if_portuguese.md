<!--
Meta Description: # Comando "if" em Java: Estruturas de Controle de Fluxo ## Sinopse O comando "if" em Java é uma estrutura de controle que permite a execução condicion...
Meta Keywords: java, else, código, condição, comando
-->

# Comando "if" em Java: Estruturas de Controle de Fluxo

## Sinopse
O comando "if" em Java é uma estrutura de controle que permite a execução condicional de um bloco de código, dependendo do resultado de uma expressão booleana. É fundamental para a implementação de lógica de decisão em programas Java.

## Documentação
O comando "if" é utilizado para executar um bloco de código quando uma condição específica é verdadeira. A sintaxe básica do comando "if" é a seguinte:

```java
if (condição) {
    // bloco de código a ser executado se a condição for verdadeira
}
```

### Estrutura Condicional
A estrutura "if" pode ser complementada com outros comandos para criar decisões mais complexas:

1. **if-else**: Executa um bloco de código se a condição for verdadeira e outro se for falsa.
   
   ```java
   if (condição) {
       // código se a condição for verdadeira
   } else {
       // código se a condição for falsa
   }
   ```

2. **if-else if-else**: Permite a verificação de várias condições em sequência.

   ```java
   if (condição1) {
       // código se condição1 for verdadeira
   } else if (condição2) {
       // código se condição2 for verdadeira
   } else {
       // código se nenhuma das condições for verdadeira
   }
   ```

3. **Operador Ternário**: Uma forma compacta de usar o "if" para atribuições.

   ```java
   resultado = (condição) ? valorSeVerdadeiro : valorSeFalso;
   ```

## Exemplos
### Exemplo Básico de Uso do "if"

```java
int numero = 10;

if (numero > 5) {
    System.out.println("O número é maior que 5.");
}
```

### Exemplo com "if-else"

```java
int numero = 3;

if (numero % 2 == 0) {
    System.out.println("O número é par.");
} else {
    System.out.println("O número é ímpar.");
}
```

### Exemplo com "if-else if-else"

```java
int nota = 85;

if (nota >= 90) {
    System.out.println("Aprovado com Distinção");
} else if (nota >= 60) {
    System.out.println("Aprovado");
} else {
    System.out.println("Reprovado");
}
```

### Exemplo com Operador Ternário

```java
int idade = 18;
String resultado = (idade >= 18) ? "Maior de idade" : "Menor de idade";
System.out.println(resultado);
```

## Explicação
Embora o comando "if" seja uma ferramenta poderosa, existem algumas armadilhas comuns:

- **Uso de Parênteses**: As condições devem sempre estar entre parênteses. Um erro comum é esquecer de usar os parênteses, resultando em erros de compilação.
  
- **Comparações de Tipos**: Certifique-se de que a condição seja do tipo booleano. Comparações incorretas podem levar a resultados inesperados.

- **Blocos de Código**: Em caso de um único comando, é opcional usar chaves `{}`. No entanto, é uma boa prática sempre usar chaves para evitar problemas futuros ao adicionar mais comandos.

- **Prioridade de Operadores**: Lembre-se da prioridade dos operadores. Condições complexas podem se comportar de maneira inesperada se a precedência não for considerada.

## Resumo em Uma Linha
O comando "if" em Java permite a execução condicional de blocos de código com base em expressões booleanas, facilitando a lógica de decisão em programas.