<!--
Meta Description: # La palabra clave "super" en Java: Uso y Ejemplos ## Sinopsis La palabra clave "super" en Java se utiliza para hacer referencia a la clase padre de u...
Meta Keywords: clase, padre, super, constructor, para
-->

# La palabra clave "super" en Java: Uso y Ejemplos

## Sinopsis
La palabra clave "super" en Java se utiliza para hacer referencia a la clase padre de un objeto, permitiendo acceder a sus métodos y atributos. Es fundamental para la herencia y el polimorfismo en la programación orientada a objetos.

## Documentación
En Java, "super" es una palabra reservada que se usa principalmente en dos contextos: para acceder a los métodos y atributos de la clase padre y para invocar el constructor de la clase padre. Esto permite a los desarrolladores extender y personalizar el comportamiento de las clases base en sus jerarquías de clases.

### Propósito
El propósito de "super" es facilitar la interacción con la clase padre, especialmente en situaciones donde hay métodos o atributos con el mismo nombre en la clase hija.

### Uso
1. **Acceso a Métodos y Atributos**: Cuando se tiene un método o atributo en la clase hija que oculta uno en la clase padre, "super" puede ser utilizado para acceder al método o atributo de la clase padre.
2. **Invocación de Constructores**: "super()" se utiliza en el constructor de una clase hija para invocar el constructor de la clase padre. Esto es esencial para asegurar que la parte heredada del objeto sea inicializada correctamente.

## Ejemplos

### Ejemplo 1: Acceso a Métodos de la Clase Padre

```java
class Animal {
    void hacerSonido() {
        System.out.println("El animal hace un sonido");
    }
}

class Perro extends Animal {
    void hacerSonido() {
        System.out.println("El perro ladra");
    }

    void sonidoDelAnimal() {
        super.hacerSonido(); // Llama al método de la clase padre
    }
}

public class Main {
    public static void main(String[] args) {
        Perro perro = new Perro();
        perro.sonidoDelAnimal(); // Salida: El animal hace un sonido
    }
}
```

### Ejemplo 2: Invocación de Constructores

```java
class Vehiculo {
    Vehiculo() {
        System.out.println("Constructor de Vehículo");
    }
}

class Coche extends Vehiculo {
    Coche() {
        super(); // Llama al constructor de la clase padre
        System.out.println("Constructor de Coche");
    }
}

public class Main {
    public static void main(String[] args) {
        Coche coche = new Coche(); // Salida: Constructor de Vehículo
                                     //         Constructor de Coche
    }
}
```

## Explicación
Al usar "super", es importante tener en cuenta que:
- **Confusión de Nombres**: Si un método o atributo de la clase hija tiene el mismo nombre que uno en la clase padre, "super" es necesario para referirse al de la clase padre.
- **Uso en Constructores**: "super()" debe ser la primera línea en el constructor de la clase hija. Si no se especifica, Java invocará automáticamente el constructor por defecto de la clase padre.
- **Acceso a Métodos Privados**: No se puede acceder a métodos o atributos privados de la clase padre usando "super".

## Resumen en una línea
La palabra clave "super" en Java permite acceder a métodos y atributos de la clase padre y es esencial para la correcta inicialización de las clases en la herencia.