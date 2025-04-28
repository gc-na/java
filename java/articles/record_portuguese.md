<!--
Meta Description: # Registros em Java: Entenda o Novo Tipo de Dados ## Sinopse Os registros (records) em Java são uma forma concisa de criar classes imutáveis que atuam...
Meta Keywords: que, registros, java, dados, são
-->

# Registros em Java: Entenda o Novo Tipo de Dados

## Sinopse
Os registros (records) em Java são uma forma concisa de criar classes imutáveis que atuam principalmente como transportadores de dados, simplificando o código e melhorando a legibilidade.

## Documentação
Os registros foram introduzidos no Java 14 como uma funcionalidade preview e se tornaram uma característica oficial na versão 16. Eles são projetados para reduzir a quantidade de código boilerplate necessário para criar classes que são essencialmente apenas contêineres de dados.

### Propósito
Os registros são úteis para modelar dados que não precisam de lógica complexa, permitindo que os desenvolvedores se concentrem na definição de dados em vez de na implementação de getters, setters, `equals()`, `hashCode()`, e `toString()`.

### Uso
Para definir um registro, utiliza-se a palavra-chave `record`, seguida pelo nome do registro e os componentes entre parênteses. Veja a estrutura básica:

```java
public record NomeDoRegistro(tipoComponente1 componente1, tipoComponente2 componente2) { }
```

Os componentes do registro são automaticamente tratados como campos finais e imutáveis. Além disso, o compilador gera automaticamente os métodos `equals()`, `hashCode()`, e `toString()`.

### Detalhes
- Os registros não podem estender outras classes, mas podem implementar interfaces.
- A imutabilidade é garantida, ou seja, uma vez que um objeto registro é criado, seus valores não podem ser alterados.
- Registros podem ser usados em padrões de correspondência com o `instanceof` a partir do Java 16.

## Exemplos
### Exemplo Básico de Registro
```java
public record Pessoa(String nome, int idade) { }

public class Main {
    public static void main(String[] args) {
        Pessoa pessoa = new Pessoa("João", 30);
        System.out.println(pessoa.nome()); // Saída: João
        System.out.println(pessoa.idade()); // Saída: 30
        System.out.println(pessoa); // Saída: Pessoa[nome=João, idade=30]
    }
}
```

### Exemplo com Métodos Adicionais
```java
public record Retangulo(double largura, double altura) {
    public double area() {
        return largura * altura;
    }
}

public class Main {
    public static void main(String[] args) {
        Retangulo retangulo = new Retangulo(5, 3);
        System.out.println("Área: " + retangulo.area()); // Saída: Área: 15.0
    }
}
```

## Explicação
### Armadilhas Comuns e Notas
- **Imutabilidade**: Como os registros são imutáveis, qualquer tentativa de alterar um componente após a criação resultará em erro de compilação.
- **Limitações de Herança**: Registros não suportam herança de classe, o que pode ser um obstáculo se você precisar de uma hierarquia de classes.
- **Componentes**: É importante notar que não é possível adicionar métodos de instância que alterem o estado dos componentes.

### Notas Adicionais
Registros podem ser utilizados em conjunto com `pattern matching` para simplificar a verificação e extração de dados. Além disso, eles são particularmente eficazes em aplicações que lidam com grandes volumes de dados ou que exigem facilidade de serialização.

## Resumo em Uma Linha
Os registros em Java são uma forma concisa e imutável de modelar dados, simplificando a criação de classes que apenas transportam informações.