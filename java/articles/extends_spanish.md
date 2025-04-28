<!--
Meta Description: # La palabra clave "extends" en Java: Herencia y Polimorfismo ## Sinopsis La palabra clave "extends" en Java se utiliza para establecer una relación d...
Meta Keywords: una, extends, que, superclase, java
-->

# La palabra clave "extends" en Java: Herencia y Polimorfismo

## Sinopsis
La palabra clave "extends" en Java se utiliza para establecer una relación de herencia entre clases, permitiendo que una clase herede las propiedades y métodos de otra. Esta característica es fundamental para la programación orientada a objetos, facilitando la reutilización del código y la creación de jerarquías de clases.

## Documentación
La palabra clave "extends" permite que una clase (subclase) herede de otra clase (superclase). Esta relación permite que la subclase adquiera todos los atributos y métodos de la superclase, lo que fomenta la reutilización del código y la organización lógica del mismo.

### Propósito
El propósito principal de "extends" es permitir que los desarrolladores creen nuevas clases basadas en clases existentes, aprovechando sus funcionalidades y extendiéndolas si es necesario. Es una herramienta clave para implementar el polimorfismo y facilitar la creación de estructuras de datos complejas.

### Uso
Para utilizar "extends", se define una clase que hereda de otra utilizando la siguiente sintaxis:

```java
class Subclase extends Superclase {
    // Cuerpo de la subclase
}
```

### Detalles
- Una clase puede extender solo una superclase, ya que Java no permite la herencia múltiple de clases. Sin embargo, una clase puede implementar múltiples interfaces.
- Los constructores de la superclase no se heredan, pero la subclase puede invocar el constructor de la superclase utilizando `super()`.
- Los métodos de la superclase pueden ser sobrescritos en la subclase para proporcionar implementaciones específicas.

## Ejemplos
### Ejemplo básico de herencia

```java
class Animal {
    void hacerSonido() {
        System.out.println("El animal hace un sonido.");
    }
}

class Perro extends Animal {
    void hacerSonido() {
        System.out.println("El perro ladra.");
    }
}

public class Main {
    public static void main(String[] args) {
        Perro miPerro = new Perro();
        miPerro.hacerSonido(); // Salida: El perro ladra.
    }
}
```

### Ejemplo con constructor

```java
class Vehiculo {
    Vehiculo() {
        System.out.println("Vehículo creado.");
    }
}

class Coche extends Vehiculo {
    Coche() {
        super(); // Llama al constructor de Vehiculo
        System.out.println("Coche creado.");
    }
}

public class Main {
    public static void main(String[] args) {
        Coche miCoche = new Coche(); // Salida: Vehículo creado. Coche creado.
    }
}
```

## Explicación
Al utilizar "extends", es importante recordar que:
- La herencia puede complicar la jerarquía de clases si no se gestiona adecuadamente. Es recomendable mantener una jerarquía clara y lógica.
- Evitar el uso excesivo de la herencia puede prevenir problemas como el "Fragile Base Class Problem", donde los cambios en la superclase pueden afectar inesperadamente a las subclases.
- En Java, los métodos y atributos de la superclase pueden ser accesibles en la subclase dependiendo de su modificador de acceso (public, protected, private).

## Resumen en una línea
La palabra clave "extends" en Java se utiliza para definir la herencia entre clases, permitiendo que una clase herede propiedades y métodos de otra clase.