<!--
Meta Description: # Sealed Classes no Java: Entenda a Nova Abordagem de Hierarquia de Classes ## Sinopse As classes seladas (sealed classes) no Java representam uma nov...
Meta Keywords: classes, public, sealed, classe, uma
-->

# Sealed Classes no Java: Entenda a Nova Abordagem de Hierarquia de Classes

## Sinopse
As classes seladas (sealed classes) no Java representam uma nova maneira de controlar a herança e a extensão de classes, introduzida no Java 15 como uma prévia e estabilizada no Java 17. Essa funcionalidade permite que desenvolvedores definam uma hierarquia de classes mais segura e previsível.

## Documentação
### O que são Classes Seladas?
Classes seladas são uma nova forma de definir classes que limitam as classes que podem estendê-las. Com isso, você pode controlar de forma precisa quais classes podem herdar de uma classe selada, aumentando a segurança do código e a manutenibilidade.

### Propósito
O principal objetivo das classes seladas é fornecer um controle mais rigoroso sobre a herança. Isso é especialmente útil em sistemas onde você deseja garantir que a API não seja extensível de maneira não intencional.

### Uso
Para definir uma classe selada, você deve utilizar a palavra-chave `sealed` antes da declaração da classe. As classes que podem estender a classe selada devem ser declaradas como `final`, `sealed` ou `non-sealed`.

```java
public sealed class Veiculo permits Carro, Moto {
    // Código da classe
}

public final class Carro extends Veiculo {
    // Código da classe
}

public final class Moto extends Veiculo {
    // Código da classe
}
```

### Detalhes
- **Permissões**: A palavra-chave `permits` é utilizada para listar as classes que podem estender a classe selada.
- **Modificadores**: As subclasses podem ser `final` (não podem ser estendidas), `sealed` (podem ter suas próprias subclasses) ou `non-sealed` (podem ser estendidas livremente).

## Exemplos
### Exemplo Básico

```java
public sealed class Animal permits Cachorro, Gato {
    public void fazerSom() {
        System.out.println("Som do animal");
    }
}

public final class Cachorro extends Animal {
    @Override
    public void fazerSom() {
        System.out.println("Au Au");
    }
}

public final class Gato extends Animal {
    @Override
    public void fazerSom() {
        System.out.println("Miau");
    }
}
```

### Exemplo com Subclasse Selada

```java
public sealed class Forma permits Circulo, Quadrado {
}

public final class Circulo extends Forma {
}

public sealed class Quadrado extends Forma permits Retangulo {
}

public final class Retangulo extends Quadrado {
}
```

## Explicação
### Armadilhas Comuns
- **Falta de Permissão**: Se uma classe não for listada no modificador `permits`, o compilador não permitirá que a classe seja estendida, resultando em um erro.
- **Hierarquia Complexa**: O uso de classes seladas pode complicar a hierarquia de classes se não for bem planejado, pois a estrutura precisa ser bem compreendida para evitar ciclos e confusões.

### Notas Adicionais
- As classes seladas são uma excelente opção para projetos onde a segurança e a previsibilidade são cruciais.
- É importante planejar cuidadosamente quais classes devem ser seladas e quais subclasses devem ser permitidas para manter a clareza no design do sistema.

## Resumo em Uma Linha
As classes seladas no Java permitem um controle rigoroso sobre a herança, garantindo que apenas classes específicas possam estender uma classe base, aumentando a segurança e manutenibilidade do código.