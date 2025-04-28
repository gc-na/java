<!--
Meta Description: # Registros en Java: Características y Uso ## Sinopsis Los registros (records) en Java son una nueva característica introducida en Java 14 como una vi...
Meta Keywords: los, registros, punto, java, public
-->

# Registros en Java: Características y Uso

## Sinopsis
Los registros (records) en Java son una nueva característica introducida en Java 14 como una vista previa y estabilizada en Java 16. Su propósito es simplificar la creación de clases que son principalmente contenedores de datos.

## Documentación
### Propósito
Los registros en Java permiten a los desarrolladores definir clases de datos inmutables de manera concisa y legible, eliminando la necesidad de escribir código boilerplate para métodos como `equals()`, `hashCode()`, y `toString()`. Esto resulta en un código más limpio y mantenible.

### Uso
Un registro se define utilizando la palabra clave `record`, seguido del nombre del registro y los parámetros que contendrá. La sintaxis básica es la siguiente:

```java
public record NombreRegistro(TipoCampo1 campo1, TipoCampo2 campo2) {}
```

#### Ejemplo de Definición
```java
public record Persona(String nombre, int edad) {}
```

### Detalles
- Los registros son inmutables, lo que significa que una vez creados, sus campos no pueden ser modificados.
- Cada registro automáticamente genera los métodos `equals()`, `hashCode()`, y `toString()` basados en los campos definidos.
- Los registros no pueden extenderse, pero pueden implementar interfaces.
- Los registros pueden tener métodos adicionales y pueden contener lógica, pero no pueden tener un constructor público explícito.

## Ejemplos
### Ejemplo Básico
Definamos un registro simple para representar un punto en un plano cartesiano:

```java
public record Punto(int x, int y) {}

public class Main {
    public static void main(String[] args) {
        Punto punto = new Punto(3, 4);
        System.out.println(punto); // Salida: Punto[x=3, y=4]
    }
}
```

### Ejemplo con Métodos Adicionales
Podemos agregar un método adicional para calcular la distancia desde el origen:

```java
public record Punto(int x, int y) {
    public double distanciaDesdeOrigen() {
        return Math.sqrt(x * x + y * y);
    }
}

public class Main {
    public static void main(String[] args) {
        Punto punto = new Punto(3, 4);
        System.out.println(punto.distanciaDesdeOrigen()); // Salida: 5.0
    }
}
```

## Explicación
### Errores Comunes
1. **Intentar Modificar Campos**: Dado que los registros son inmutables, cualquier intento de modificar un campo después de la creación del objeto resultará en un error de compilación.
2. **Extender Registros**: Los registros no pueden extender otras clases, lo que puede ser confuso para aquellos acostumbrados a la herencia en Java.

### Notas Adicionales
- Los registros son particularmente útiles en arquitecturas basadas en datos, como DTOs (Data Transfer Objects) o en la programación funcional.
- Aunque los registros simplifican la creación de clases de datos, es importante recordar que no son adecuados para todas las situaciones, especialmente donde se requiere herencia compleja.

## Resumen en Una Línea
Los registros en Java son una forma concisa y eficiente de definir clases inmutables que representan datos, generando automáticamente métodos útiles.