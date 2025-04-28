<!--
Meta Description: # int en Java: Tipos de Datos y Usos ## Sinopsis El tipo de dato `int` en Java es una de las principales características del lenguaje, utilizada para ...
Meta Keywords: int, java, tipo, que, enteros
-->

# int en Java: Tipos de Datos y Usos

## Sinopsis
El tipo de dato `int` en Java es una de las principales características del lenguaje, utilizada para representar números enteros en un rango específico. Es fundamental en la programación para realizar operaciones matemáticas y lógicas.

## Documentación
El tipo `int` en Java es un tipo de dato primitivo que ocupa 32 bits (4 bytes) en memoria. Los valores que puede almacenar van desde -2,147,483,648 hasta 2,147,483,647. Este rango permite representar una amplia variedad de números enteros con eficiencia.

### Propósito
El propósito del tipo `int` es proporcionar una forma de almacenar y manipular números enteros en las aplicaciones de Java. Se utiliza comúnmente en ciclos, contadores, y cualquier operación que requiera números enteros.

### Uso
Para declarar una variable de tipo `int`, se utiliza la siguiente sintaxis:

```java
int nombreVariable;
```

También se pueden inicializar en la misma línea:

```java
int contador = 0;
```

Los números enteros se pueden operar utilizando los operadores aritméticos estándar como `+`, `-`, `*`, y `/`.

## Ejemplos
### Ejemplo 1: Declaración y Inicialización
```java
int edad = 25;
System.out.println("La edad es: " + edad);
```

### Ejemplo 2: Operaciones Aritméticas
```java
int a = 10;
int b = 5;
int suma = a + b;
int resta = a - b;
System.out.println("Suma: " + suma);
System.out.println("Resta: " + resta);
```

### Ejemplo 3: Uso en un Ciclo
```java
for (int i = 0; i < 5; i++) {
    System.out.println("Número: " + i);
}
```

## Explicación
Al utilizar el tipo `int`, hay algunas consideraciones importantes:

1. **Desbordamiento**: Si se intenta almacenar un valor que excede el límite superior o inferior, se producirá un desbordamiento, lo que puede causar resultados inesperados. Por ejemplo, sumar 1 a `Integer.MAX_VALUE` resultará en `Integer.MIN_VALUE`.

2. **División**: En operaciones de división, si ambos operandes son enteros, el resultado también será un entero, lo que significa que se truncará cualquier parte decimal. Por ejemplo, `5 / 2` resulta en `2`, no en `2.5`.

3. **Conversión de Tipos**: Al trabajar con otros tipos de datos, como `double` o `float`, es importante realizar conversiones adecuadas para evitar la pérdida de precisión.

## Resumen en una Línea
El tipo `int` en Java es un tipo de dato primitivo que permite almacenar números enteros en un rango de -2,147,483,648 a 2,147,483,647, siendo fundamental para operaciones matemáticas y lógicas en la programación.