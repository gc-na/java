<!--
Meta Description: # Importar en Java: Guía Completa sobre el Comando "import" ## Sinopsis El comando "import" en Java es fundamental para incluir clases y paquetes en u...
Meta Keywords: java, import, clases, para, paquetes
-->

# Importar en Java: Guía Completa sobre el Comando "import"

## Sinopsis
El comando "import" en Java es fundamental para incluir clases y paquetes en un programa, permitiendo el uso de funcionalidades externas y la organización del código de manera eficiente.

## Documentación
El comando `import` se utiliza en Java para acceder a clases y paquetes que no pertenecen al paquete actual. Esto es esencial para el desarrollo de aplicaciones Java, ya que permite reutilizar código y utilizar bibliotecas externas.

### Propósito
El propósito del comando `import` es facilitar la incorporación de clases de otros paquetes, evitando la necesidad de utilizar nombres de clases completamente calificados en cada instancia.

### Uso
La declaración de importación se coloca al principio de un archivo Java, antes de la declaración de la clase. La sintaxis básica es la siguiente:

```java
import nombre_del_paquete.NombreDeLaClase;
```

También se puede utilizar un asterisco (*) para importar todas las clases de un paquete:

```java
import nombre_del_paquete.*;
```

### Detalles
1. **Importación específica**: Permite importar una clase específica de un paquete.
2. **Importación por paquete**: Permite importar todas las clases dentro de un paquete.
3. **Importaciones estáticas**: Se pueden importar métodos o variables estáticas de una clase para acceder a ellos sin necesidad de instanciar esa clase:

   ```java
   import static nombre_del_paquete.NombreDeLaClase.metodoEstatico;
   ```

## Ejemplos

### Ejemplo 1: Importación de una clase específica
```java
import java.util.ArrayList;

public class EjemploImport {
    public static void main(String[] args) {
        ArrayList<String> lista = new ArrayList<>();
        lista.add("Hola");
        System.out.println(lista);
    }
}
```

### Ejemplo 2: Importación de todas las clases de un paquete
```java
import java.util.*;

public class EjemploImportPaquete {
    public static void main(String[] args) {
        HashMap<String, String> mapa = new HashMap<>();
        mapa.put("clave", "valor");
        System.out.println(mapa);
    }
}
```

### Ejemplo 3: Importación estática
```java
import static java.lang.Math.PI;
import static java.lang.Math.pow;

public class EjemploImportEstatica {
    public static void main(String[] args) {
        System.out.println("El valor de PI es: " + PI);
        System.out.println("2 elevado a la 3 es: " + pow(2, 3));
    }
}
```

## Explicación
Al utilizar el comando `import`, es importante tener en cuenta que:

- **Conflictos de nombres**: Si se importan dos clases con el mismo nombre de diferentes paquetes, se debe especificar el paquete para evitar confusiones.
- **Importaciones innecesarias**: Importar clases que no se utilizan puede llevar a un código poco limpio y a que el compilador emita advertencias.
- **Organización de paquetes**: Es recomendable organizar las clases en paquetes adecuados para facilitar su importación y uso.

## Resumen en una línea
El comando `import` en Java permite incluir clases y paquetes externos en un programa, facilitando la reutilización de código y la organización del mismo.