<!--
Meta Description: # "provides" em Java: Entendendo a Palavra-Chave e Sua Aplicação ## Sinopse A palavra-chave `provides` em Java, introduzida no Java 9, é utilizada no ...
Meta Keywords: java, que, provides, interface, serviço
-->

# "provides" em Java: Entendendo a Palavra-Chave e Sua Aplicação

## Sinopse
A palavra-chave `provides` em Java, introduzida no Java 9, é utilizada no contexto do sistema de módulos, permitindo que um módulo declare a implementação de uma interface de serviço. Essa funcionalidade é essencial para a modularização de aplicações, facilitando a manutenção e a escalabilidade do código.

## Documentação
O comando `provides` é parte do sistema de módulos do Java, que se concentra na definição de módulos e suas interações. Um módulo pode fornecer implementações para interfaces de serviço, permitindo que outros módulos as utilizem. A sintaxe básica do `provides` é:

```java
provides <interface> with <implementation>;
```

### Propósito
O propósito do `provides` é especificar que um determinado módulo fornece uma implementação de uma interface de serviço. Isso permite que outros módulos que dependem dessa interface possam consumir a implementação sem precisar conhecer detalhes sobre como ela é feita.

### Uso
Para utilizar o `provides`, você deve seguir algumas etapas:

1. **Definir um Módulo**: Primeiro, você precisa ter um arquivo `module-info.java` em seu módulo.
2. **Criar Interfaces de Serviço**: As interfaces que você deseja disponibilizar devem ser definidas.
3. **Implementar a Interface**: Você deve ter uma ou mais classes que implementam a interface de serviço.
4. **Declarar no Módulo**: Use a palavra-chave `provides` para declarar a implementação no `module-info.java`.

### Exemplo de `module-info.java`
```java
module meu.modulo {
    provides com.exemplo.Servico with com.exemplo.impl.ServicoImpl;
}
```

## Exemplos
Aqui está um exemplo básico que ilustra o uso do `provides`:

### Definição da Interface e Implementação
```java
// Interface de Serviço
package com.exemplo;

public interface Servico {
    void executar();
}

// Implementação do Serviço
package com.exemplo.impl;

import com.exemplo.Servico;

public class ServicoImpl implements Servico {
    @Override
    public void executar() {
        System.out.println("Serviço executado!");
    }
}
```

### Arquivo `module-info.java`
```java
module meu.modulo {
    provides com.exemplo.Servico with com.exemplo.impl.ServicoImpl;
}
```

### Consumo do Serviço em Outro Módulo
```java
module consumidor.modulo {
    requires meu.modulo;
}

// Classe que consome o serviço
package consumidor;

import com.exemplo.Servico;
import java.util.ServiceLoader;

public class Main {
    public static void main(String[] args) {
        ServiceLoader<Servico> loader = ServiceLoader.load(Servico.class);
        for (Servico servico : loader) {
            servico.executar();
        }
    }
}
```

## Explicação
Embora o uso do `provides` traga muitos benefícios, existem algumas armadilhas comuns e pontos a serem observados:

- **Interface Não Pública**: A interface que você está tentando fornecer deve ser pública. Caso contrário, outras partes do seu aplicativo não conseguirão acessá-la.
- **Implementação Não Pública**: Similarmente, a implementação deve ser pública, ou não será acessível para os módulos que tentam consumi-la.
- **Módulos Não Especificados**: Certifique-se de que todos os módulos que precisam do serviço estão corretamente especificados no `module-info.java`.

## Resumo em Uma Linha
A palavra-chave `provides` em Java permite que um módulo declare a implementação de uma interface de serviço, facilitando a modularização e a reutilização do código.