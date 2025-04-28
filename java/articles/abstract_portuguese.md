<!--
Meta Description: # Abstract em Java: Entendendo Classes e Métodos Abstratos ## Sinopse O termo "abstract" em Java refere-se a um modificador que permite a criação de c...
Meta Keywords: métodos, que, abstract, abstratos, não
-->

# Abstract em Java: Entendendo Classes e Métodos Abstratos

## Sinopse
O termo "abstract" em Java refere-se a um modificador que permite a criação de classes e métodos abstratos. Classes abstratas não podem ser instanciadas diretamente e podem conter métodos que não possuem uma implementação concreta, forçando subclasses a fornecerem uma implementação específica.

## Documentação
Em Java, o modificador `abstract` pode ser aplicado a classes e métodos. O principal objetivo de uma classe abstrata é servir como um modelo para outras classes. Uma classe abstrata pode conter métodos abstratos, que são definidos sem corpo, exigindo que as subclasses implementem esses métodos.

### Classes Abstratas
- **Definição**: Uma classe que é declarada com o modificador `abstract`.
- **Características**:
  - Não pode ser instanciada diretamente.
  - Pode conter métodos abstratos e não abstratos.
  - Pode ter construtores e atributos.

### Métodos Abstratos
- **Definição**: Um método declarado com o modificador `abstract` que não possui implementação.
- **Requisitos**:
  - Subclasses são obrigadas a implementar métodos abstratos.
  - Não podem ter um corpo (ou seja, não têm chaves `{}`).

### Exemplo de Uso
```java
abstract class Animal {
    abstract void fazerSom(); // Método abstrato

    void dormir() { // Método não abstrato
        System.out.println("O animal está dormindo.");
    }
}

class Cachorro extends Animal {
    @Override
    void fazerSom() {
        System.out.println("O cachorro late.");
    }
}

class Gato extends Animal {
    @Override
    void fazerSom() {
        System.out.println("O gato mia.");
    }
}
```

## Exemplos
### Exemplo 1: Classe Abstrata com Método Abstrato
```java
abstract class Veiculo {
    abstract void mover();

    void parar() {
        System.out.println("O veículo parou.");
    }
}

class Carro extends Veiculo {
    @Override
    void mover() {
        System.out.println("O carro está se movendo.");
    }
}
```

### Exemplo 2: Instanciação de Subclasse
```java
public class Main {
    public static void main(String[] args) {
        Veiculo meuCarro = new Carro();
        meuCarro.mover();
        meuCarro.parar();
    }
}
```

## Explicação
Um erro comum ao trabalhar com classes e métodos abstratos é tentar instanciar uma classe abstrata diretamente, o que resultará em um erro de compilação. Além disso, é importante lembrar que, mesmo que uma classe contenha métodos não abstratos, ela ainda é considerada abstrata se pelo menos um de seus métodos for abstrato.

Outro ponto a considerar é que as classes abstratas podem ter construtores, que podem ser utilizados por subclasses para inicializar atributos comuns.

## Resumo em Uma Linha
O modificador `abstract` em Java permite a criação de classes e métodos que não podem ser instanciados diretamente, servindo como um modelo para subclasses que devem implementar métodos abstratos.