<!--
Meta Description: # O Que É "default" em Java: Compreendendo o Modificador e Seus Usos ## Sinopse O modificador "default" em Java é utilizado para definir métodos padrã...
Meta Keywords: default, que, métodos, interfaces, com
-->

# O Que É "default" em Java: Compreendendo o Modificador e Seus Usos

## Sinopse
O modificador "default" em Java é utilizado para definir métodos padrão em interfaces, permitindo que estas incluam implementações concretas, facilitando a evolução de APIs sem quebrar a compatibilidade com versões anteriores.

## Documentação
### Propósito
O modificador "default" foi introduzido no Java 8 com o objetivo de permitir que as interfaces tenham métodos com implementações. Isso possibilita que os desenvolvedores adicionem novos métodos às interfaces existentes, sem a necessidade de alterar todas as classes que já implementam essa interface.

### Uso
Para declarar um método como "default" dentro de uma interface, você deve preceder a assinatura do método com a palavra-chave `default`. Os métodos padrão podem ser sobrescritos nas classes que implementam a interface.

### Detalhes
- **Compatibilidade**: O uso de métodos `default` garante que as interfaces possam evoluir sem quebrar a compatibilidade com classes que já as implementam.
- **Multidimensionalidade**: É possível que uma classe implemente múltiplas interfaces que contenham métodos com o mesmo nome. Nesse caso, a classe deve fornecer uma implementação específica para evitar ambiguidades.
- **Uso em Interfaces Funcionais**: Embora métodos `default` sejam uma adição poderosa, eles não devem ser usados em interfaces que são consideradas completamente funcionais (interfaces que contêm apenas um método abstrato).

## Exemplos
### Exemplo 1: Método Default em uma Interface

```java
interface Animal {
    void fazerSom();

    default void dormir() {
        System.out.println("O animal está dormindo.");
    }
}

class Cachorro implements Animal {
    @Override
    public void fazerSom() {
        System.out.println("O cachorro late.");
    }
}

public class Main {
    public static void main(String[] args) {
        Cachorro cachorro = new Cachorro();
        cachorro.fazerSom(); // Saída: O cachorro late.
        cachorro.dormir(); // Saída: O animal está dormindo.
    }
}
```

### Exemplo 2: Sobrescrevendo um Método Default

```java
interface Veiculo {
    default void mover() {
        System.out.println("O veículo está se movendo.");
    }
}

class Carro implements Veiculo {
    @Override
    public void mover() {
        System.out.println("O carro está se movendo rapidamente.");
    }
}

public class Main {
    public static void main(String[] args) {
        Carro carro = new Carro();
        carro.mover(); // Saída: O carro está se movendo rapidamente.
    }
}
```

## Explicação
### Armadilhas Comuns
- **Ambiguidade de Métodos**: Se uma classe implementar várias interfaces que definem métodos `default` com o mesmo nome, essa classe deve implementar o método para resolver a ambiguidade. Ignorar isso resultará em um erro de compilação.
- **Excesso de Implementações**: Embora seja tentador usar métodos `default` para adicionar lógica complexa nas interfaces, isso pode tornar a interface menos clara e mais difícil de entender. É aconselhável manter a lógica simples e direta.

### Notas Adicionais
Os métodos `default` são uma ferramenta poderosa e devem ser usados de forma criteriosa. Eles permitem que as bibliotecas Java evoluam sem quebrar a compatibilidade, mas também podem levar a um design confuso se não forem utilizados com cuidado.

## Resumo em Uma Linha
O modificador "default" em Java permite a implementação de métodos padrão em interfaces, facilitando a evolução de APIs sem quebrar a compatibilidade.