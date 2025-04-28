<!--
Meta Description: # Classe em Java: Estruturas e Funcionalidades ## Sinopse A classe em Java é um dos pilares da programação orientada a objetos (POO) e serve como um m...
Meta Keywords: classe, uma, public, java, que
-->

# Classe em Java: Estruturas e Funcionalidades

## Sinopse
A classe em Java é um dos pilares da programação orientada a objetos (POO) e serve como um molde para a criação de objetos, permitindo encapsular dados e comportamentos.

## Documentação
Em Java, uma classe é uma estrutura que define um novo tipo de dado. As classes são fundamentais na POO, pois permitem organizar e manipular dados de forma eficiente. Cada classe pode conter atributos (variáveis) e métodos (funções) que definem o comportamento dos objetos criados a partir dessa classe.

### Propósito
O principal objetivo de uma classe é encapsular dados e comportamentos, promovendo a reutilização de código e a organização lógica de programas complexos. Ao criar uma classe, o programador pode instanciar múltiplos objetos que herdam a mesma estrutura e funcionalidade definida na classe.

### Uso
Para declarar uma classe em Java, utiliza-se a palavra-chave `class`, seguida do nome da classe. O nome da classe deve começar com uma letra maiúscula, conforme a convenção de nomenclatura Java. Uma classe pode incluir modificadores de acesso como `public`, `private`, e `protected`, que definem a visibilidade da classe e de seus membros.

Exemplo básico de declaração de classe:
```java
public class Carro {
    // Atributos
    private String modelo;
    private int ano;

    // Construtor
    public Carro(String modelo, int ano) {
        this.modelo = modelo;
        this.ano = ano;
    }

    // Métodos
    public void exibirInfo() {
        System.out.println("Modelo: " + modelo + ", Ano: " + ano);
    }
}
```

## Exemplos
### Exemplo 1: Criando e utilizando uma classe simples
```java
public class Main {
    public static void main(String[] args) {
        Carro meuCarro = new Carro("Fusca", 1976);
        meuCarro.exibirInfo(); // Saída: Modelo: Fusca, Ano: 1976
    }
}
```

### Exemplo 2: Classe com métodos adicionais
```java
public class Pessoa {
    private String nome;
    private int idade;

    public Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    public void aniversario() {
        idade++;
        System.out.println(nome + " agora tem " + idade + " anos.");
    }
}

// Uso
public class Main {
    public static void main(String[] args) {
        Pessoa pessoa = new Pessoa("João", 30);
        pessoa.aniversario(); // Saída: João agora tem 31 anos.
    }
}
```

## Explicação
Um erro comum ao trabalhar com classes em Java é a tentativa de acessar atributos privados diretamente de fora da classe. Para interagir com esses atributos, é recomendável usar métodos públicos (getters e setters). Além disso, é importante lembrar que uma classe pode herdar propriedades de outra classe, o que permite a criação de hierarquias e a reutilização de código.

Outro ponto a se considerar é a inicialização de variáveis. Se um atributo não for inicializado, ele pode conter valores nulos ou padrão, o que pode levar a erros em tempo de execução se não for tratado adequadamente.

## Resumo em uma linha
Uma classe em Java é uma estrutura fundamental da programação orientada a objetos que define um tipo de dado e encapsula atributos e métodos, promovendo a organização e a reutilização de código.