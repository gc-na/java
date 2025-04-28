<!--
Meta Description: # O tipo de dado "int" em Java: Tudo o que você precisa saber ## Sinopse O tipo de dado primitivo `int` em Java é utilizado para representar números i...
Meta Keywords: int, java, que, para, tipo
-->

# O tipo de dado "int" em Java: Tudo o que você precisa saber

## Sinopse
O tipo de dado primitivo `int` em Java é utilizado para representar números inteiros, sendo uma das formas mais comuns de manipulação de dados numéricos em aplicações Java.

## Documentação
O `int` é um dos oito tipos de dados primitivos em Java, designado para armazenar valores inteiros de 32 bits, com um intervalo que varia de -2.147.483.648 a 2.147.483.647. Ele é amplamente utilizado devido à sua eficiência e simplicidade.

### Propósito
O `int` é utilizado quando se necessita de uma representação numérica sem casas decimais, ideal para contagens, índices, e cálculos que não requerem precisão decimal.

### Uso
Para declarar uma variável do tipo `int`, utiliza-se a seguinte sintaxe:

```java
int nomeDaVariavel;
```

Você pode inicializar a variável no momento da declaração:

```java
int idade = 30;
```

O `int` também suporta operações aritméticas como adição, subtração, multiplicação e divisão. 

### Detalhes
- O `int` é mais eficiente em termos de performance em comparação com tipos de dados como `Integer` (que é um wrapper para `int`).
- O uso do `int` é apropriado em situações onde a memória é uma preocupação, já que um `int` ocupa 4 bytes de memória.

## Exemplos
### Exemplo 1: Declaração e Inicialização
```java
int numero = 10;
System.out.println("O número é: " + numero);
```

### Exemplo 2: Operações Aritméticas
```java
int a = 5;
int b = 10;
int soma = a + b;
System.out.println("A soma é: " + soma);
```

### Exemplo 3: Uso em Estruturas de Controle
```java
for (int i = 0; i < 5; i++) {
    System.out.println("Número: " + i);
}
```

## Explicação
Ao utilizar `int`, é importante estar ciente de algumas limitações e armadilhas comuns:

- **Overflow**: Ao tentar armazenar um valor que excede o limite máximo ou mínimo do `int`, ocorre um overflow. Por exemplo, se você tentar armazenar 2.147.483.649 em uma variável `int`, isso resultará em um valor incorreto.
  
- **Divisão Inteira**: Quando você divide dois inteiros, o resultado também será um inteiro. Por exemplo, `5 / 2` resulta em `2`, não `2.5`. Para obter um resultado decimal, pelo menos um dos operandos deve ser um tipo de dado que suporte casas decimais, como `double` ou `float`.

- **Conversão**: Ao interagir com outros tipos de dados, pode ser necessário converter explicitamente entre `int` e outros tipos, como `double`.

## Resumo em uma linha
O tipo `int` em Java é um tipo primitivo que representa números inteiros de 32 bits, amplamente utilizado para cálculos e contagens em aplicações de software.