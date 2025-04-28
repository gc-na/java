<!--
Meta Description: # Enum en Java: Todo lo que necesitas saber sobre enumeraciones en Java ## Sinopsis El tipo de dato `enum` en Java permite crear un conjunto de consta...
Meta Keywords: enum, java, public, color, constantes
-->

# Enum en Java: Todo lo que necesitas saber sobre enumeraciones en Java

## Sinopsis
El tipo de dato `enum` en Java permite crear un conjunto de constantes, facilitando la definición de variables que pueden tomar un valor entre un número limitado de opciones predefinidas. Esto mejora la legibilidad del código y reduce el riesgo de errores.

## Documentación
El uso de `enum` en Java se introdujo en la versión 5 del lenguaje. Su propósito principal es representar un grupo de constantes relacionadas. Un `enum` se define utilizando la palabra clave `enum`, seguida por el nombre del enumerado y una lista de los valores permitidos.

### Propósito
- Facilitar la agrupación de constantes relacionadas.
- Proporcionar una forma más legible y segura de manejar un conjunto fijo de valores.
- Permitir la adición de métodos y atributos a las constantes enumeradas.

### Uso
Para declarar un `enum`, se utiliza la siguiente sintaxis:

```java
public enum NombreEnum {
    CONSTANTE1,
    CONSTANTE2,
    CONSTANTE3;
}
```

### Detalles
- Un `enum` en Java hereda de la clase `java.lang.Enum`.
- Cada constante de un `enum` es un objeto único y se pueden agregar métodos y atributos.
- Se pueden usar en estructuras de control como `switch`.
- Los `enum` pueden implementar interfaces, pero no pueden extender otras clases.

## Ejemplos

### Ejemplo básico de `enum`
```java
public enum Color {
    ROJO,
    VERDE,
    AZUL;
}

public class Main {
    public static void main(String[] args) {
        Color color = Color.ROJO;

        switch (color) {
            case ROJO:
                System.out.println("El color es rojo.");
                break;
            case VERDE:
                System.out.println("El color es verde.");
                break;
            case AZUL:
                System.out.println("El color es azul.");
                break;
        }
    }
}
```

### Ejemplo con métodos
```java
public enum Dia {
    LUNES("Lunes"),
    MARTES("Martes"),
    MIERCOLES("Miércoles");

    private String nombre;

    Dia(String nombre) {
        this.nombre = nombre;
    }

    public String getNombre() {
        return nombre;
    }
}

public class Main {
    public static void main(String[] args) {
        for (Dia dia : Dia.values()) {
            System.out.println(dia.getNombre());
        }
    }
}
```

## Explicación
Al trabajar con `enum`, es importante tener en cuenta lo siguiente:
- **Comparación**: Utiliza `==` para comparar constantes de un `enum`, en lugar de `equals()`.
- **Orden**: Los `enum` tienen un orden natural basado en el orden de declaración.
- **No se pueden instanciar**: No puedes crear instancias de un `enum` usando el operador `new`.

### Problemas comunes
- Intentar extender un `enum` generará un error de compilación, ya que los `enum` no pueden heredar de otras clases.
- Al agregar constantes en un `enum`, es crucial que cada constante sea única.

## Resumen en una línea
El `enum` en Java permite definir un conjunto de constantes relacionadas, mejorando la legibilidad y la seguridad del código.