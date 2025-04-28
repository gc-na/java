<!--
Meta Description: # Java: Uso de "non-sealed" en Clases y Interfaces ## Sinopsis La palabra clave "non-sealed" en Java permite que las subclases de una clase sellada (s...
Meta Keywords: sealed, clase, que, sellada, non
-->

# Java: Uso de "non-sealed" en Clases y Interfaces

## Sinopsis
La palabra clave "non-sealed" en Java permite que las subclases de una clase sellada (sealed class) sean abiertas a la herencia, facilitando una estructura de jerarquía más flexible en la programación orientada a objetos.

## Documentación
La característica "non-sealed" fue introducida en Java 17 como parte de las mejoras en el sistema de tipos y herencia. Esta palabra clave se utiliza en el contexto de clases y interfaces selladas, que limitan qué otras clases pueden extenderlas. Al aplicar "non-sealed", se indica que la clase o interfaz puede ser extendida sin restricciones adicionales.

### Propósito
- **Flexibilidad en la Herencia**: Permite que las clases que son parte de una jerarquía sellada tengan una subclase que no esté sujeta a las restricciones de la clase sellada, promoviendo una mayor flexibilidad en el diseño del software.
- **Control de Acceso**: Mantiene el control sobre qué clases pueden extender una clase sellada, mientras que todavía permite la extensión en ciertos casos.

### Uso
Para utilizar "non-sealed", se debe declarar una clase o interfaz como "non-sealed" dentro de una jerarquía de clases selladas. Un ejemplo básico de su implementación es el siguiente:

```java
// Clase sellada
public sealed class Vehiculo permits Coche, Moto {
}

// Clase no sellada que extiende la clase sellada
public non-sealed class Coche extends Vehiculo {
}

// Clase que extiende Coche
public class CocheDeCarrera extends Coche {
}
```

## Ejemplos
### Ejemplo 1: Clase sellada y clase no sellada

```java
// Clase sellada
public sealed class Animal permits Perro, Gato {
}

// Clase no sellada
public non-sealed class Perro extends Animal {
}

// Clase que extiende Perro
public class PerroDeCaza extends Perro {
}
```

### Ejemplo 2: Uso de interfaces selladas

```java
// Interfaz sellada
public sealed interface Transporte permits Coche, Bicicleta {
}

// Interfaz no sellada
public non-sealed interface Coche extends Transporte {
}
```

## Explicación
Al utilizar "non-sealed", es importante recordar que:
- **Subclases Ilimitadas**: Las clases o interfaces no selladas pueden ser extendidas por cualquier otra clase, lo que puede llevar a un diseño menos controlado si no se maneja adecuadamente.
- **Compatibilidad con Clases Selladas**: Solo se puede aplicar "non-sealed" a clases e interfaces que están en una jerarquía sellada, y no puede ser utilizada de forma aislada.
- **Estrategia de Diseño**: Se debe considerar cuidadosamente cuándo usar "non-sealed" para mantener un equilibrio entre flexibilidad y control.

## Resumen en una línea
La palabra clave "non-sealed" en Java permite que las clases e interfaces selladas sean extendidas sin restricciones adicionales, promoviendo una mayor flexibilidad en la herencia.