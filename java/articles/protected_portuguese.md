<!--
Meta Description: # Modificador de Acesso "protected" em Java: Entenda Seu Funcionamento e Aplicações ## Sinopse O modificador de acesso "protected" em Java é uma palav...
Meta Keywords: protected, acesso, que, classes, class
-->

# Modificador de Acesso "protected" em Java: Entenda Seu Funcionamento e Aplicações

## Sinopse
O modificador de acesso "protected" em Java é uma palavra-chave que controla a visibilidade de classes, métodos e variáveis, permitindo o acesso a subclasses e classes no mesmo pacote, promovendo a reutilização de código e a encapsulação.

## Documentação
O modificador "protected" é um dos quatro modificadores de acesso em Java, sendo os outros "public", "private" e o modificador padrão (package-private). Ao utilizar "protected", você define que um membro (variável ou método) de uma classe pode ser acessado:

- Por outras classes no mesmo pacote.
- Por subclasses, mesmo que estejam em pacotes diferentes.

### Propósito
O objetivo principal do "protected" é permitir que subclasses tenham acesso a membros da superclasse, facilitando a herança e a extensão de funcionalidades sem expor esses membros a todas as outras classes.

### Uso
O uso do modificador "protected" é bastante comum em hierarquias de classes onde se deseja manter a encapsulação, mas ao mesmo tempo permitir que subclasses acessem métodos e variáveis necessárias para sua funcionalidade.

```java
class SuperClasse {
    protected int numero;

    protected void exibirNumero() {
        System.out.println("Número: " + numero);
    }
}

class SubClasse extends SuperClasse {
    void mostrar() {
        numero = 10; // Acesso permitido
        exibirNumero(); // Acesso permitido
    }
}
```

## Exemplos

### Exemplo Básico de Uso
```java
class Animal {
    protected void fazerSom() {
        System.out.println("Som de animal");
    }
}

class Cachorro extends Animal {
    void emitirSom() {
        fazerSom(); // Acesso permitido
        System.out.println("Au Au");
    }
}

public class Main {
    public static void main(String[] args) {
        Cachorro cachorro = new Cachorro();
        cachorro.emitirSom();
    }
}
```

### Exemplo com Pacotes
```java
package meuPacote;

class Veiculo {
    protected String tipo;

    protected void mostrarTipo() {
        System.out.println("Tipo: " + tipo);
    }
}

package outroPacote;

import meuPacote.Veiculo;

class Carro extends Veiculo {
    void definirTipo() {
        tipo = "SUV"; // Acesso permitido
        mostrarTipo(); // Acesso permitido
    }
}

public class Main {
    public static void main(String[] args) {
        Carro carro = new Carro();
        carro.definirTipo();
    }
}
```

## Explicação
Embora o modificador "protected" seja útil, há algumas considerações a serem feitas:

1. **Acesso Limitado**: Membros "protected" não são acessíveis por classes que não sejam subclasses ou que não estejam no mesmo pacote, o que pode levar a confusões se não for entendido corretamente.

2. **Evitar Exposição Desnecessária**: Usar "protected" pode levar a uma exposição desnecessária de implementação. Sempre que possível, prefira encapsular membros e usar métodos públicos para acesso.

3. **Considerações de Design**: Ao projetar hierarquias de classes, considere cuidadosamente onde usar "protected" para não criar dependências indesejadas entre classes.

## Resumo em Uma Linha
O modificador "protected" em Java permite que membros de uma classe sejam acessíveis por subclasses e classes do mesmo pacote, promovendo a reutilização e a encapsulação do código.