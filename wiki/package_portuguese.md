<!--
Meta Description: # Pacote em JAVA: Estrutura e Organização de Código ## Sinopse Os pacotes em Java são uma maneira de agrupar classes relacionadas, facilitando a organ...
Meta Keywords: java, pacote, exemplo, classes, pacotes
-->

# Pacote em JAVA: Estrutura e Organização de Código

## Sinopse
Os pacotes em Java são uma maneira de agrupar classes relacionadas, facilitando a organização do código e evitando conflitos de nomes.

## Documentação
Em Java, um pacote é um namespace que organiza um conjunto de classes e interfaces. Os pacotes ajudam a estruturar o projeto, proporcionando uma hierarquia que torna o código mais modular e reutilizável. Além disso, o uso de pacotes permite que desenvolvedores compartilhem suas classes sem o risco de colisão de nomes.

### Propósito
- **Organização**: Agrupa classes relacionadas, facilitando a navegação e manutenção do código.
- **Controle de Acesso**: Permite especificar níveis de acesso entre diferentes classes.
- **Reutilização**: Facilita a reutilização de classes em diferentes projetos.

### Uso
Para criar um pacote, você deve declarar o pacote no início do arquivo Java utilizando a palavra-chave `package`, seguida do nome do pacote. O nome deve ser único e geralmente é escrito em letras minúsculas, utilizando a convenção de nomenclatura reversa de domínios.

```java
package com.exemplo.projeto;
```

### Estrutura de Pacotes
Os pacotes podem ser aninhados, criando uma estrutura hierárquica. Por exemplo, `com.exemplo.projeto` pode conter subpacotes como `com.exemplo.projeto.util` ou `com.exemplo.projeto.model`.

## Exemplos
### Exemplo 1: Criando um Pacote
```java
package com.exemplo.calculadora;

public class Soma {
    public int adicionar(int a, int b) {
        return a + b;
    }
}
```

### Exemplo 2: Usando um Pacote
Para usar uma classe de um pacote diferente, você deve importá-la. No exemplo a seguir, importamos a classe `Soma`:

```java
import com.exemplo.calculadora.Soma;

public class Teste {
    public static void main(String[] args) {
        Soma soma = new Soma();
        System.out.println("Resultado: " + soma.adicionar(5, 10));
    }
}
```

## Explicação
### Armadilhas Comuns
- **Declaração de Pacote**: A declaração do pacote deve ser a primeira linha do arquivo, exceto por comentários. Se não for declarada corretamente, o compilador não reconhecerá a classe como parte do pacote.
- **Conflitos de Nome**: Ao importar classes de pacotes diferentes, pode ocorrer conflitos de nomes. É importante usar a declaração `import` corretamente ou usar o nome completo da classe (ex: `com.exemplo.calculadora.Soma`).

### Notas Adicionais
- Os pacotes padrão em Java incluem `java.lang`, `java.util`, entre outros. Você pode usar classes desses pacotes sem a necessidade de importação explícita, exceto para classes que não estão dentro de `java.lang`.

## Resumo em Uma Linha
Os pacotes em Java organizam classes e interfaces em namespaces, promovendo a modularidade e evitando conflitos de nomes.