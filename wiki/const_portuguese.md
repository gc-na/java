<!--
Meta Description: # Constantes em Java: Entendendo o Uso de "final" ## Sinopse Em Java, o uso da palavra-chave "final" permite a definição de constantes, que são variáv...
Meta Keywords: final, que, ser, não, variáveis
-->

# Constantes em Java: Entendendo o Uso de "final"

## Sinopse
Em Java, o uso da palavra-chave "final" permite a definição de constantes, que são variáveis cujo valor não pode ser alterado após a sua inicialização. Este conceito é fundamental para garantir a imutabilidade em certas partes do código.

## Documentação
### Propósito
A palavra-chave "final" é utilizada para declarar variáveis, métodos e classes que não podem ser alterados ou sobrescritos. Quando aplicada a variáveis, ela indica que o valor atribuído a essa variável não pode ser modificado.

### Uso
1. **Variáveis**: Ao declarar uma variável como `final`, você está especificando que ela deve ser inicializada uma única vez e que seu valor não pode ser alterado posteriormente.
2. **Métodos**: Um método declarado como `final` não pode ser sobrescrito em subclasses, garantindo que a implementação original permaneça inalterada.
3. **Classes**: Uma classe declarada como `final` não pode ser estendida, o que é útil para evitar herança indesejada.

### Detalhes
- **Inicialização**: Variáveis finais devem ser inicializadas no momento da declaração ou dentro de um construtor. Não é permitido deixá-las sem inicialização.
- **Constantes de Classe**: É comum utilizar `final` em conjunto com `static` para definir constantes de classe, que são acessíveis sem a necessidade de criar uma instância da classe.

## Exemplos
### Exemplo 1: Variável Final
```java
final int numeroMaximo = 100;
// numeroMaximo = 200; // Isso causará um erro de compilação
```

### Exemplo 2: Método Final
```java
class Animal {
    final void emitirSom() {
        System.out.println("Som do Animal");
    }
}

class Cachorro extends Animal {
    // void emitirSom() { // Isso causará um erro de compilação
    //     System.out.println("Au Au");
    // }
}
```

### Exemplo 3: Classe Final
```java
final class Utilitario {
    // Métodos e variáveis da classe
}

// class NovoUtilitario extends Utilitario { // Isso causará um erro de compilação
// }
```

## Explicação
Um erro comum entre programadores iniciantes é tentar alterar o valor de uma variável final após sua inicialização, o que resulta em um erro de compilação. Além disso, tentar sobrescrever um método final ou estender uma classe final também resultará em erros. É importante lembrar que o uso de `final` pode melhorar a legibilidade do código, pois os outros desenvolvedores saberão que certas partes do código não podem ser modificadas.

## Resumo em Uma Linha
A palavra-chave `final` em Java é utilizada para declarar variáveis, métodos e classes que não podem ser alterados ou sobrescritos, promovendo a imutabilidade no código.