<!--
Meta Description: # Synchronized em JAVA: Sincronização de Threads para Concorrência Segura ## Sinopse O `synchronized` em JAVA é uma palavra-chave que permite a sincro...
Meta Keywords: synchronized, que, para, java, métodos
-->

# Synchronized em JAVA: Sincronização de Threads para Concorrência Segura

## Sinopse
O `synchronized` em JAVA é uma palavra-chave que permite a sincronização de métodos e blocos de código, garantindo que apenas uma thread tenha acesso a um recurso compartilhado em um dado momento. Isso é crucial para prevenir condições de corrida e garantir a integridade dos dados em aplicações multithreaded.

## Documentação
### Propósito
O modificador `synchronized` é utilizado para controlar o acesso a um método ou bloco de código por múltiplas threads. Quando um método ou bloco é marcado como `synchronized`, ele adquire um bloqueio (lock) no objeto que o contém, impedindo que outras threads acessem o mesmo recurso até que o bloqueio seja liberado.

### Uso
Existem duas formas principais de utilizar o `synchronized`:

1. **Métodos Synchronized**:
   - Um método pode ser declarado como `synchronized`, o que significa que o bloqueio é aplicado ao objeto da instância (`this`) para métodos de instância ou à classe (`ClassName.class`) para métodos estáticos.

   ```java
   public synchronized void metodoSynchronized() {
       // Código que acessa recursos compartilhados
   }
   ```

2. **Blocos Synchronized**:
   - Um bloco de código dentro de um método pode ser sincronizado, permitindo controle mais granular sobre o acesso a recursos. Isso pode ser feito utilizando um objeto como monitor.

   ```java
   public void metodoComBlocoSynchronized() {
       synchronized (this) {
           // Código que acessa recursos compartilhados
       }
   }
   ```

### Detalhes
- O `synchronized` pode ser aplicado a métodos de instância e estáticos.
- O bloqueio é adquirido no objeto que está sendo referenciado (no caso de métodos de instância) ou na classe (para métodos estáticos).
- É importante evitar o uso excessivo de `synchronized`, pois pode levar a problemas de desempenho, como deadlocks e diminuição da concorrência.

## Exemplos
### Exemplo de Método Synchronized
```java
public class Contador {
    private int contagem = 0;

    public synchronized void incrementar() {
        contagem++;
    }

    public synchronized int getContagem() {
        return contagem;
    }
}
```

### Exemplo de Bloco Synchronized
```java
public class Banco {
    private int saldo = 1000;

    public void sacar(int valor) {
        synchronized (this) {
            if (valor <= saldo) {
                saldo -= valor;
            }
        }
    }

    public int getSaldo() {
        return saldo;
    }
}
```

## Explicação
### Armadilhas Comuns
- **Deadlocks**: Ocorrências em que duas ou mais threads ficam esperando mutuamente para liberar recursos, levando o sistema a um estado de inatividade.
- **Desempenho Reduzido**: O uso excessivo de `synchronized` pode causar contenção de threads e reduzir o desempenho geral da aplicação.
- **Visibilidade de Dados**: O `synchronized` garante que as mudanças feitas por uma thread se tornem visíveis para outras threads, mas isso não aplica para variáveis que não estão sendo acessadas de forma sincronizada.

### Notas Adicionais
- Para resolver problemas de concorrência mais complexos, considere usar classes do pacote `java.util.concurrent`, como `ReentrantLock` ou `CountDownLatch`, que oferecem mais flexibilidade e controle sobre a sincronização.

## Resumo em Uma Linha
O `synchronized` em JAVA é uma palavra-chave utilizada para controlar o acesso a métodos e blocos de código por múltiplas threads, garantindo a integridade dos dados em aplicações concorrentes.