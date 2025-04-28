<!--
Meta Description: # O Uso da Palavra-Chave "super" em Java: Entenda suas Funcionalidades ## Sinopse A palavra-chave "super" em Java é utilizada para referenciar diretam...
Meta Keywords: superclasse, super, class, subclasse, construtor
-->

# O Uso da Palavra-Chave "super" em Java: Entenda suas Funcionalidades

## Sinopse
A palavra-chave "super" em Java é utilizada para referenciar diretamente a classe pai de uma classe derivada, permitindo o acesso a métodos e variáveis que foram herdados.

## Documentação
A palavra-chave "super" serve como um mecanismo de acesso na linguagem Java para interagir com membros da superclasse. Ela é especialmente útil em cenários de herança, onde uma classe (subclasse) estende outra (superclasse). "super" permite que a subclasse acesse métodos e variáveis da superclasse que foram ocultos ou sobrescritos.

### Propósito
- **Acesso a membros da superclasse**: Facilita a chamada de métodos e variáveis que pertencem à superclasse.
- **Chamada ao construtor da superclasse**: Permite que a subclasse invoque o construtor da superclasse para inicializar membros herdados.

### Uso
- **Acesso a variáveis**: `super.nomeDaVariavel` pode ser usado quando há um conflito de nomes entre a superclasse e a subclasse.
- **Chamada de métodos**: `super.nomeDoMetodo()` permite chamar um método da superclasse que foi sobrescrito na subclasse.
- **Construtores**: `super()` é utilizado para chamar o construtor da superclasse, devendo ser a primeira linha do construtor da subclasse.

## Exemplos

### Exemplo 1: Acesso a variáveis da superclasse
```java
class Animal {
    String tipo = "Animal";

    void mostrarTipo() {
        System.out.println("Tipo: " + tipo);
    }
}

class Cachorro extends Animal {
    String tipo = "Cachorro";

    void mostrarTipo() {
        System.out.println("Tipo: " + tipo);
        System.out.println("Tipo da superclasse: " + super.tipo); // Acessando a variável da superclasse
    }
}

public class Main {
    public static void main(String[] args) {
        Cachorro cachorro = new Cachorro();
        cachorro.mostrarTipo();
    }
}
```

### Exemplo 2: Chamada a métodos da superclasse
```java
class Veiculo {
    void mostrar() {
        System.out.println("Este é um veículo.");
    }
}

class Carro extends Veiculo {
    void mostrar() {
        super.mostrar(); // Chamando o método da superclasse
        System.out.println("Este é um carro.");
    }
}

public class Main {
    public static void main(String[] args) {
        Carro carro = new Carro();
        carro.mostrar();
    }
}
```

### Exemplo 3: Chamada ao construtor da superclasse
```java
class Pessoa {
    String nome;

    Pessoa(String nome) {
        this.nome = nome;
    }
}

class Estudante extends Pessoa {
    int matricula;

    Estudante(String nome, int matricula) {
        super(nome); // Chamando o construtor da superclasse
        this.matricula = matricula;
    }
}

public class Main {
    public static void main(String[] args) {
        Estudante estudante = new Estudante("Carlos", 12345);
        System.out.println("Nome: " + estudante.nome + ", Matrícula: " + estudante.matricula);
    }
}
```

## Explicação
Embora o uso de "super" seja simples, é importante estar atento a alguns pontos:
- **Confusão de nomes**: Ao usar "super", você pode evitar conflitos de nomes entre variáveis da superclasse e da subclasse.
- **Ordem da chamada ao construtor**: O `super()` deve ser a primeira linha no construtor da subclasse; caso contrário, o compilador gerará um erro.
- **Métodos não estáticos**: "super" não pode ser usado para acessar métodos da superclasse a partir de um contexto estático.

## Resumo em uma linha
A palavra-chave "super" em Java é utilizada para acessar membros da superclasse, facilitando a herança e a reutilização de código.