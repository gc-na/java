<!--
Meta Description: # Comando "else" em JAVA: Estruturas de Controle de Fluxo ## Sinopse O comando "else" em Java é uma estrutura de controle que permite executar um bloc...
Meta Keywords: else, código, java, para, nota
-->

# Comando "else" em JAVA: Estruturas de Controle de Fluxo

## Sinopse
O comando "else" em Java é uma estrutura de controle que permite executar um bloco de código alternativo quando uma condição especificada em um comando "if" não é satisfeita. Essa funcionalidade é fundamental para a tomada de decisões em programas Java.

## Documentação
O "else" é utilizado em conjunto com a instrução "if" para criar uma estrutura condicional. A sintaxe básica é a seguinte:

```java
if (condicao) {
    // bloco de código se a condição for verdadeira
} else {
    // bloco de código se a condição for falsa
}
```

### Propósito
O comando "else" é essencial para o controle de fluxo em um programa, permitindo que o desenvolvedor especifique o que deve acontecer quando a condição do "if" não for atendida. Isso facilita a criação de lógicas mais complexas e melhora a legibilidade do código.

### Uso
O "else" pode ser utilizado de forma isolada ou em combinação com outras instruções "if" e "else if" para avaliar múltiplas condições. A estrutura pode ser expandida para lidar com diferentes cenários:

```java
if (condicao1) {
    // código para a condição 1
} else if (condicao2) {
    // código para a condição 2
} else {
    // código se nenhuma das condições anteriores for verdadeira
}
```

## Exemplos
### Exemplo 1: Uso básico do "else"
```java
int numero = 10;

if (numero > 0) {
    System.out.println("O número é positivo.");
} else {
    System.out.println("O número é negativo ou zero.");
}
```

### Exemplo 2: Uso de "else if"
```java
int nota = 75;

if (nota >= 90) {
    System.out.println("Nota A");
} else if (nota >= 80) {
    System.out.println("Nota B");
} else if (nota >= 70) {
    System.out.println("Nota C");
} else {
    System.out.println("Nota D");
}
```

## Explicação
Um erro comum ao usar "else" é esquecer de incluir chaves `{}` ao definir blocos de código, especialmente quando mais de uma linha de código precisa ser executada. O uso de chaves é uma boa prática, pois melhora a legibilidade e evita comportamentos inesperados.

Outro ponto importante é que as condições devem ser bem definidas para evitar que o código entre em um estado indesejado. Um "else" sempre captura todas as situações não tratadas anteriormente, então, é crucial que ele seja usado com cuidado.

## Resumo em Uma Linha
O comando "else" em Java permite a execução de um bloco de código alternativo quando a condição de um "if" não é atendida, facilitando o controle de fluxo nas aplicações.