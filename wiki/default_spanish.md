<!--
Meta Description: # Palabra Clave "default" en Java: Uso y Ejemplos ## Sinopsis La palabra clave `default` en Java se utiliza para definir métodos por defecto en interf...
Meta Keywords: por, defecto, default, método, void
-->

# Palabra Clave "default" en Java: Uso y Ejemplos

## Sinopsis
La palabra clave `default` en Java se utiliza para definir métodos por defecto en interfaces, permitiendo proporcionar una implementación concreta que puede ser opcional para las clases que implementan la interfaz.

## Documentación
### Propósito
Introducida en Java 8, la palabra clave `default` permite a los desarrolladores agregar métodos con implementación a interfaces sin romper la compatibilidad con clases que ya implementan esas interfaces. Esto facilita la evolución de interfaces y la incorporación de nuevos métodos sin requerir que todas las clases existentes se modifiquen.

### Uso
Para definir un método por defecto, se utiliza la palabra clave `default` seguida de la implementación del método dentro de la interfaz. Las clases que implementan la interfaz pueden optar por sobrescribir este método o usar la implementación predeterminada.

#### Sintaxis
```java
interface NombreInterfaz {
    void metodoAbstracto(); // Método abstracto

    default void metodoPorDefecto() {
        // Implementación por defecto
        System.out.println("Este es un método por defecto.");
    }
}
```

## Ejemplos
### Ejemplo 1: Uso básico de `default`
```java
interface Vehiculo {
    void conducir(); // Método abstracto

    default void encender() {
        System.out.println("El vehículo está encendido.");
    }
}

class Coche implements Vehiculo {
    public void conducir() {
        System.out.println("Conduciendo el coche.");
    }
}

public class Main {
    public static void main(String[] args) {
        Coche miCoche = new Coche();
        miCoche.conducir(); // Imprime: Conduciendo el coche.
        miCoche.encender();  // Imprime: El vehículo está encendido.
    }
}
```

### Ejemplo 2: Sobrescribir un método por defecto
```java
interface Dispositivo {
    default void encender() {
        System.out.println("Dispositivo encendido.");
    }
}

class Televisor implements Dispositivo {
    @Override
    public void encender() {
        System.out.println("Televisor encendido.");
    }
}

public class Main {
    public static void main(String[] args) {
        Televisor miTelevisor = new Televisor();
        miTelevisor.encender(); // Imprime: Televisor encendido.
    }
}
```

## Explicación
### Problemas Comunes
- **Confusión con métodos abstractos**: Es importante recordar que los métodos por defecto no son obligatorios de implementar en las clases que implementan la interfaz. Sin embargo, si una clase implementa la interfaz y define su propia versión del método por defecto, esta nueva implementación sobrescribirá la versión por defecto.
- **Herencia múltiple**: Si una clase implementa múltiples interfaces que tienen un método por defecto con el mismo nombre y firma, debe proporcionar una implementación concreta para resolver la ambigüedad.

### Notas Adicionales
- Los métodos por defecto son una herramienta poderosa para la evolución de API, permitiendo introducir nuevas funcionalidades sin afectar el código existente.
- Aunque se pueden usar métodos por defecto, es recomendable usarlos con moderación para mantener la claridad y la simplicidad del diseño de las interfaces.

## Resumen en una Línea
La palabra clave `default` en Java permite definir métodos con implementación en interfaces, facilitando la evolución de estas sin romper la compatibilidad con clases existentes.