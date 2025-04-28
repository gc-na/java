<!--
Meta Description: # Interface em JAVA: Entendendo os Fundamentos e a Aplicação ## Sinopse Uma interface em Java é um tipo de referência que pode conter apenas constante...
Meta Keywords: interface, uma, métodos, que, interfaces
-->

# Interface em JAVA: Entendendo os Fundamentos e a Aplicação

## Sinopse
Uma interface em Java é um tipo de referência que pode conter apenas constantes, métodos abstratos, métodos padrão, métodos estáticos e tipos aninhados. Interfaces são uma forma essencial de implementar a programação orientada a objetos e a herança múltipla em Java.

## Documentação
### O que é uma Interface?
Uma interface em Java define um contrato que outras classes podem implementar. Ela permite que diferentes classes compartilhem um conjunto de métodos sem a necessidade de herança de uma classe base. As interfaces são utilizadas para alcançar a abstração e a separação de responsabilidades em um sistema.

### Propósito
O principal objetivo de usar interfaces é permitir a implementação de métodos que podem ser utilizados em diferentes classes, promovendo a reutilização de código e a flexibilidade. Interfaces são fundamentais para a programação orientada a objetos, pois permitem a implementação de polimorfismo.

### Uso
Para declarar uma interface, utiliza-se a palavra-chave `interface`. As classes que implementam essa interface devem fornecer a implementação de todos os métodos declarados. Uma classe pode implementar múltiplas interfaces, o que não é possível com classes.

### Estrutura Básica de uma Interface
```java
public interface NomeDaInterface {
    // Métodos abstratos
    void metodo1();
    int metodo2(String parametro);
}
```

## Exemplos
### Exemplo 1: Interface Simples
```java
public interface Animal {
    void fazerSom(); // método abstrato
}

public class Cachorro implements Animal {
    @Override
    public void fazerSom() {
        System.out.println("Au Au");
    }
}

public class Gato implements Animal {
    @Override
    public void fazerSom() {
        System.out.println("Miau");
    }
}
```

### Exemplo 2: Interface com Métodos Padrão
```java
public interface Veiculo {
    void acelerar();

    default void parar() {
        System.out.println("O veículo parou.");
    }
}

public class Carro implements Veiculo {
    @Override
    public void acelerar() {
        System.out.println("Carro acelerando.");
    }
}
```

## Explicação
### Armadilhas Comuns
1. **Métodos Não Implementados**: Se uma classe não implementar todos os métodos de uma interface, ela deve ser declarada como abstrata.
2. **Interfaces e Herança**: Uma classe pode implementar várias interfaces, mas não pode herdar de mais de uma classe. Isso permite a flexibilidade na modelagem de hierarquias.
3. **Métodos Estáticos**: As interfaces podem conter métodos estáticos, mas esses métodos não podem ser sobrescritos por classes que implementam a interface.

### Notas Adicionais
- Interfaces são uma forma eficaz de garantir que uma classe siga um determinado contrato, facilitando a manutenção e a escalabilidade do código.
- A partir do Java 8, métodos padrão e estáticos podem ser adicionados às interfaces, trazendo mais funcionalidades e flexibilidade.

## Resumo em Uma Linha
Interfaces em Java são contratos que definem métodos que classes podem implementar, permitindo a reutilização de código e a programação orientada a objetos.