<!--
Meta Description: # Extends em Java: Compreendendo a Herança de Classes ## Sinopse O comando "extends" em Java é uma palavra-chave fundamental que permite a criação de ...
Meta Keywords: superclasse, extends, java, que, uma
-->

# Extends em Java: Compreendendo a Herança de Classes

## Sinopse
O comando "extends" em Java é uma palavra-chave fundamental que permite a criação de subclasses a partir de classes base, facilitando a reutilização de código e a implementação de herança.

## Documentação
A palavra-chave `extends` é utilizada em Java para indicar que uma classe está herdando características e comportamentos de outra classe. A herança é um dos pilares da programação orientada a objetos, permitindo que uma nova classe (subclasse) herde atributos e métodos de uma classe existente (superclasse).

### Propósito
O principal objetivo do `extends` é promover a reutilização de código, permitindo que os desenvolvedores criem novas classes que possam usar e, quando necessário, modificar o comportamento das classes existentes.

### Uso
A sintaxe básica para utilizar `extends` é a seguinte:

```java
class Subclasse extends Superclasse {
    // corpo da subclasse
}
```

Nesse contexto:
- `Superclasse` é a classe da qual a `Subclasse` está herdando.
- `Subclasse` pode acessar os métodos e atributos públicos e protegidos da `Superclasse`.

### Detalhes
- Uma classe pode estender apenas uma outra classe (herança simples), pois Java não suporta herança múltipla.
- A subclasse pode adicionar novos métodos e atributos, além de sobrescrever métodos da superclasse.
- O construtor da superclasse deve ser chamado explicitamente usando `super()` no construtor da subclasse, se necessário.

## Exemplos
### Exemplo Básico de Herança

```java
class Animal {
    void fazerSom() {
        System.out.println("O animal faz um som.");
    }
}

class Cachorro extends Animal {
    void fazerSom() {
        System.out.println("O cachorro late.");
    }
}

public class Teste {
    public static void main(String[] args) {
        Cachorro meuCachorro = new Cachorro();
        meuCachorro.fazerSom(); // Saída: O cachorro late.
    }
}
```

### Exemplo com Construtor

```java
class Veiculo {
    Veiculo() {
        System.out.println("Veículo criado.");
    }
}

class Carro extends Veiculo {
    Carro() {
        super(); // Chama o construtor da superclasse
        System.out.println("Carro criado.");
    }
}

public class Teste {
    public static void main(String[] args) {
        Carro meuCarro = new Carro(); // Saída: Veículo criado. Carro criado.
    }
}
```

## Explicação
Um erro comum ao utilizar `extends` é esquecer de chamar o construtor da superclasse. Isso resulta em um erro de compilação, pois o Java requer que a superclasse seja inicializada. Outro ponto a se considerar é a sobrescrita de métodos; ao sobrescrever, é importante manter a assinatura do método e, se necessário, usar a anotação `@Override` para garantir que você está realmente sobrescrevendo um método da superclasse.

Além disso, é importante lembrar que, ao herdar de uma classe, a subclasse não pode acessar métodos e atributos privados da superclasse, o que pode levar a confusões se não for bem compreendido.

## Resumo em Uma Linha
A palavra-chave `extends` em Java permite a criação de subclasses, promovendo a reutilização de código através da herança de classes.