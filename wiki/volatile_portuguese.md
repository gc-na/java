<!--
Meta Description: # Volatile em Java: Entendendo a Palavra-Chave e Seu Uso ## Sinopse A palavra-chave `volatile` em Java é utilizada para garantir a visibilidade de mud...
Meta Keywords: volatile, que, uma, para, variável
-->

# Volatile em Java: Entendendo a Palavra-Chave e Seu Uso

## Sinopse
A palavra-chave `volatile` em Java é utilizada para garantir a visibilidade de mudanças em variáveis entre threads. Ela é essencial em ambientes multithread, onde diferentes threads podem acessar e modificar variáveis simultaneamente.

## Documentação
A palavra-chave `volatile` em Java é um modificador de variável que assegura que as alterações feitas em uma variável por uma thread sejam visíveis para outras threads. Ao declarar uma variável como `volatile`, você garante que:

1. **Visibilidade**: Quando uma thread modifica uma variável `volatile`, essa alteração é imediatamente visível para outras threads. Isso evita que uma thread leia uma versão desatualizada do valor de uma variável.

2. **Ordenação**: O uso de `volatile` também impede a reordenação de instruções, garantindo que as operações sejam executadas na ordem esperada.

### Uso
Para declarar uma variável como `volatile`, basta usar a palavra-chave antes do tipo da variável na declaração. Por exemplo:
```java
volatile int contador;
```

## Exemplos
### Exemplo Básico de Uso do Volatile
```java
public class ExemploVolatile {
    private volatile boolean ativo = true;

    public void executar() {
        while (ativo) {
            // Realiza alguma operação
        }
    }

    public void parar() {
        ativo = false; // Essa alteração será visível para a thread que executa executar()
    }
}
```
Neste exemplo, a variável `ativo` é declarada como `volatile`, garantindo que a mudança feita na thread que chama `parar()` seja imediatamente percebida pela thread que está executando `executar()`.

### Exemplo de Visibilidade
```java
public class ExemploVisibilidade {
    private volatile int numero = 0;

    public void incrementar() {
        numero++;
    }

    public int obterNumero() {
        return numero;
    }
}
```
Neste caso, mesmo que `incrementar()` seja chamado por diferentes threads, a variável `numero` sempre terá o valor mais atualizado para qualquer thread que a acesse.

## Explicação
Embora `volatile` trate da visibilidade e da ordenação das operações, ele não fornece atomicidade. Operações que não são atômicas, como incrementos, podem ainda apresentar problemas se não forem sincronizadas adequadamente. 

### Armadilhas Comuns
- **Não é substituto para sincronização**: `volatile` não pode ser usado como um substituto para `synchronized` em situações que requerem atomicidade, como operações de leitura-modificação-escrita.
- **Comportamento inesperado em estruturas complexas**: O uso de `volatile` em estruturas de dados complexas pode levar a comportamentos inesperados, já que a visibilidade não garante que a operação completa seja atômica.

## Resumo em Uma Frase
A palavra-chave `volatile` em Java é utilizada para garantir a visibilidade de variáveis entre threads, evitando que uma thread veja uma versão desatualizada do valor.