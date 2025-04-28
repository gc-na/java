<!--
Meta Description: # Módulos en Java: Estructuración y Organización del Código ## Sinopsis En Java, un módulo es una unidad de encapsulación que permite agrupar paquetes...
Meta Keywords: java, que, módulos, módulo, module
-->

# Módulos en Java: Estructuración y Organización del Código

## Sinopsis
En Java, un módulo es una unidad de encapsulación que permite agrupar paquetes, clases y recursos relacionados. Introducido en Java 9, el sistema de módulos mejora la modularidad y ayuda en la gestión de dependencias, facilitando el desarrollo de aplicaciones más grandes y mantenibles.

## Documentación
### Propósito
El sistema de módulos en Java permite a los desarrolladores dividir sus aplicaciones en partes más pequeñas y manejables, llamadas módulos, lo que promueve la reutilización de código y mejora la organización del mismo.

### Uso
Para definir un módulo, se utiliza un archivo `module-info.java` en el directorio raíz del módulo. Este archivo especifica el nombre del módulo y las dependencias de otros módulos. Un módulo puede exportar paquetes, lo que permite que otros módulos accedan a sus clases y recursos.

**Sintaxis básica de `module-info.java`:**
```java
module nombre.del.modulo {
    exports paquete.a.exportar;
    requires otro.modulo;
}
```

### Detalles
- **Exportar paquetes:** Con la palabra clave `exports`, un módulo puede permitir que otros módulos accedan a sus paquetes.
- **Requerir módulos:** Con `requires`, un módulo puede indicar dependencias de otros módulos, lo que asegura que se carguen antes de que el módulo actual se ejecute.
- **Encapsulación:** Los módulos encapsulan su contenido, lo que significa que solo las partes explícitamente exportadas son accesibles desde otros módulos.

## Ejemplos
### Definición de un Módulo
```java
// module-info.java
module mi.modulo {
    exports com.ejemplo.paquete;
    requires otro.modulo;
}
```

### Uso de un Módulo en un Programa
```java
// com/ejemplo/paquete/MiClase.java
package com.ejemplo.paquete;

public class MiClase {
    public void mostrar() {
        System.out.println("Hola desde MiClase");
    }
}
```

### Acceso a un Módulo desde Otro
```java
// module-info.java de otro.modulo
module otro.modulo {
    requires mi.modulo;
}

// com/otro/paquete/OtraClase.java
package com.otro.paquete;

import com.ejemplo.paquete.MiClase;

public class OtraClase {
    public static void main(String[] args) {
        MiClase miClase = new MiClase();
        miClase.mostrar();
    }
}
```

## Explicación
Al trabajar con módulos en Java, es común cometer algunos errores. Aquí hay algunos puntos a tener en cuenta:
- **Falta de `module-info.java`:** Si no se incluye este archivo, la funcionalidad de módulos no estará disponible.
- **Exportación de paquetes incorrectos:** Asegúrate de que todos los paquetes que deseas que sean accesibles estén correctamente exportados.
- **Ciclo de dependencias:** Evita crear ciclos en tus dependencias entre módulos, ya que esto puede causar problemas en la carga de clases.

## Resumen en una línea
Un módulo en Java es una unidad de encapsulación que agrupa paquetes y recursos, mejorando la modularidad y la gestión de dependencias en aplicaciones.