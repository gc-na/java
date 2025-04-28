<!--
Meta Description: # Non-Sealed em Java: Entendendo a Classe Não Selada ## Sinopse O modificador "non-sealed" em Java, introduzido na versão 17, permite que uma classe s...
Meta Keywords: sealed, classe, uma, non, selada
-->

# Non-Sealed em Java: Entendendo a Classe Não Selada

## Sinopse
O modificador "non-sealed" em Java, introduzido na versão 17, permite que uma classe selada (sealed class) declare que suas subclasses podem ser estendidas por qualquer outra classe, promovendo uma maior flexibilidade na hierarquia de classes.

## Documentação
O modificador "non-sealed" é utilizado em conjunto com classes seladas (sealed classes) para indicar que uma subclasse não deve ser restringida na extensão. Quando uma classe é declarada como "sealed", isso significa que somente as classes especificadas podem herdar dela. No entanto, ao usar "non-sealed", a classe que estende a classe selada pode ser estendida por qualquer outra classe, permitindo um modelo mais aberto.

### Propósito
O principal objetivo do modificador "non-sealed" é permitir uma maior liberdade em uma hierarquia de classes que começa com uma classe selada. Isso é útil quando você deseja controlar quais classes podem herdar de uma classe base, mas ainda quer permitir que, em algum ponto, essa restrição seja relaxada.

### Uso
Para usar o modificador "non-sealed", você deve primeiro ter uma classe selada definida. Em seguida, ao definir uma subclasse, você pode declarar essa subclasse como "non-sealed".

### Detalhes
1. **Classes Seladas**: Para usar "non-sealed", a classe pai deve ser declarada como selada.
2. **Hierarquia Flexível**: Permite que desenvolvedores criem hierarquias de classes que podem ser mais ou menos restritivas conforme necessário.
3. **Compatibilidade**: O modificador "non-sealed" é compatível com as regras de herança e encapsulamento do Java.

## Exemplos
### Exemplo 1: Classe Selada e Subclasse Não Selada

```java
// Definindo uma classe selada
public sealed class Veiculo permits Carro, Moto {
}

// Definindo uma subclasse não selada
public non-sealed class Carro extends Veiculo {
}

// Definindo outra subclasse que pode estender Carro
public class Sedan extends Carro {
}
```

### Exemplo 2: Classe Selada com Subclasse Não Selada

```java
public sealed class Animal permits Mamifero, Reptil {
}

public non-sealed class Mamifero extends Animal {
}

public class Cachorro extends Mamifero {
}
```

## Explicação
Ao usar "non-sealed", é importante lembrar que:
- **Flexibilidade vs. Controle**: Embora a classe "non-sealed" permita que outras classes a estendam, você deve sempre considerar o design da aplicação, pois isso pode levar a uma hierarquia de classes complexa e difícil de manter.
- **Uso Adequado**: O uso inadequado de "non-sealed" em uma hierarquia de classes pode resultar em dificuldades para entender a estrutura de herança.
- **Limitações**: Uma classe não pode ser tanto "sealed" quanto "non-sealed"; você deve escolher uma abordagem clara para a sua hierarquia.

## Resumo em Uma Linha
O modificador "non-sealed" em Java permite que subclasses de uma classe selada sejam estendidas por qualquer outra classe, oferecendo flexibilidade na hierarquia de classes.