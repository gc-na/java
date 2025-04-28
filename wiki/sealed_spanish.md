<!--
Meta Description: # Cláusula "sealed" en Java: Una Nueva Forma de Controlar la Herencia ## Sinopsis La cláusula "sealed" en Java es una característica introducida en Ja...
Meta Keywords: clases, sealed, una, las, public
-->

# Cláusula "sealed" en Java: Una Nueva Forma de Controlar la Herencia

## Sinopsis
La cláusula "sealed" en Java es una característica introducida en Java 15 que permite a los desarrolladores restringir la herencia de clases y la implementación de interfaces, proporcionando un control más preciso sobre la jerarquía de clases.

## Documentación
La cláusula "sealed" se utiliza en la declaración de clases e interfaces para limitar qué otras clases pueden extender o implementar la clase o interfaz sellada. Esto es particularmente útil en el diseño de API y sistemas complejos, donde se desea mantener un control estricto sobre la evolución de las jerarquías de tipos.

### Propósito
- **Control de Herencia**: Permite a los desarrolladores definir una jerarquía de clases más controlada y predecible.
- **Seguridad**: Aumenta la seguridad del código al restringir qué clases pueden ser subclases, evitando la creación accidental de jerarquías no deseadas.

### Uso
Para declarar una clase o interfaz sellada, se utiliza la palabra clave `sealed` seguida de la palabra clave `permits`, que especifica qué clases están permitidas para extender la clase sellada.

```java
public sealed class Forma permits Circulo, Cuadrado {
    // Implementación de la clase
}

public final class Circulo extends Forma {
    // Implementación de Circulo
}

public final class Cuadrado extends Forma {
    // Implementación de Cuadrado
}
```

### Detalles
- Una clase o interfaz sellada debe tener al menos una subclase permitida.
- Las subclases de una clase sellada pueden ser declaradas como `final`, `sealed` o `non-sealed`.
- Las clases `final` no pueden ser extendidas, las clases `sealed` pueden tener su propia lista de permitidos y las `non-sealed` pueden ser extendidas sin restricciones.

## Ejemplos
### Ejemplo 1: Clase Sellada Simple
```java
public sealed class Vehiculo permits Coche, Moto {
    // Campos y métodos
}

public final class Coche extends Vehiculo {
    // Implementación de Coche
}

public final class Moto extends Vehiculo {
    // Implementación de Moto
}
```

### Ejemplo 2: Uso de Clases No Selladas
```java
public sealed class Animal permits Perro, Gato {}

public final class Perro extends Animal {}

public non-sealed class Gato extends Animal {
    // Gato puede ser extendido
}
```

## Explicación
Al implementar la cláusula "sealed", los desarrolladores deben tener en cuenta lo siguiente:
- **Restricciones de Herencia**: Todos los desarrolladores que trabajen con clases selladas deben estar al tanto de las restricciones impuestas.
- **Mantenimiento de Código**: Las clases selladas pueden hacer que el mantenimiento del código sea más sencillo, pero también pueden complicar la extensibilidad si no se planifican adecuadamente.

### Errores Comunes
- **Olvidar la palabra clave `permits`**: Asegúrese de especificar las clases permitidas al declarar una clase sellada.
- **No utilizar subclases**: Las clases selladas deben tener al menos una subclase permitida, de lo contrario, se generará un error de compilación.

## Resumen en Una Línea
La cláusula "sealed" en Java permite a los desarrolladores restringir la herencia de clases e interfaces, proporcionando un control más riguroso sobre la jerarquía de tipos.