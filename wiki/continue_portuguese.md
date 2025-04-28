<!--
Meta Description: # Comando "continue" em Java: Controle de Fluxo Eficiente ## Sinopse O comando `continue` em Java é utilizado dentro de loops para pular a iteração at...
Meta Keywords: continue, loops, loop, java, para
-->

# Comando "continue" em Java: Controle de Fluxo Eficiente

## Sinopse
O comando `continue` em Java é utilizado dentro de loops para pular a iteração atual e continuar com a próxima. Este comando é essencial para o controle de fluxo, permitindo uma execução mais eficiente de laços de repetição.

## Documentação
### Propósito
O `continue` é um comando que altera o fluxo de execução dentro de estruturas de repetição, como `for`, `while` e `do-while`. Quando o Java encontra o comando `continue`, ele interrompe a execução do bloco de código atual e inicia a próxima iteração do loop.

### Uso
O `continue` pode ser usado em loops que são controlados por uma condição. Ao ser invocado, ele pode ser aplicado a loops com ou sem condição, dependendo de onde ele é posicionado.

#### Sintaxe
```java
continue; // para loops sem rótulo
```
ou
```java
continue nomeDoRotulo; // para loops com rótulo
```

### Detalhes
- **Loops suportados**: O `continue` pode ser usado em loops `for`, `while`, e `do-while`.
- **Rótulos**: É possível usar o `continue` com rótulos para afetar loops aninhados, permitindo que você controle qual loop deve continuar.

## Exemplos
### Exemplo 1: Usando `continue` em um loop `for`
```java
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        continue; // pula números pares
    }
    System.out.println(i); // imprime números ímpares
}
```

### Exemplo 2: Usando `continue` em um loop `while`
```java
int j = 0;
while (j < 10) {
    j++;
    if (j % 2 == 0) {
        continue; // pula números pares
    }
    System.out.println(j); // imprime números ímpares
}
```

### Exemplo 3: Usando `continue` com rótulos
```java
externo: for (int k = 0; k < 3; k++) {
    for (int l = 0; l < 3; l++) {
        if (l == 1) {
            continue externo; // pula para a próxima iteração do laço externo
        }
        System.out.println("k: " + k + ", l: " + l);
    }
}
```

## Explicação
### Armadilhas Comuns
- **Uso excessivo**: O uso excessivo do `continue` pode tornar o código menos legível. É importante usá-lo com moderação para manter a clareza.
- **Loops aninhados**: Quando usado em loops aninhados, é crucial entender qual loop está sendo afetado, especialmente ao usar rótulos. Um erro comum é esquecer de especificar o rótulo, fazendo com que o `continue` afete o loop errado.

### Observações Adicionais
- O `continue` não finaliza o loop, apenas salta a execução para a próxima iteração.
- É essencial garantir que a condição de saída do loop seja atingida, caso contrário, o loop pode se tornar infinito.

## Resumo em Uma Linha
O comando `continue` em Java permite pular a iteração atual de um loop e continuar com a próxima, melhorando o controle de fluxo do código.