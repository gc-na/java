<!--
Meta Description: # Uso de "throws" en Java: Manejo de Excepciones ## Sinopsis La palabra clave `throws` en Java se utiliza para declarar que un método puede lanzar exc...
Meta Keywords: throws, excepciones, que, para, método
-->

# Uso de "throws" en Java: Manejo de Excepciones

## Sinopsis
La palabra clave `throws` en Java se utiliza para declarar que un método puede lanzar excepciones específicas. Esto permite a los desarrolladores gestionar las excepciones de manera más organizada y clara, mejorando la robustez del código.

## Documentación
### Propósito
La declaración `throws` se utiliza en la firma de un método para indicar que el método puede lanzar excepciones que no son manejadas dentro del mismo. Esto es especialmente útil para las excepciones verificadas (checked exceptions), que son aquellas que el compilador obliga a manejar, ya sea con un bloque `try-catch` o mediante otra declaración `throws`.

### Uso
La sintaxis básica para utilizar `throws` es la siguiente:

```java
public void nombreDelMetodo() throws TipoDeExcepcion {
    // Código que puede lanzar la excepción
}
```

Un método puede declarar múltiples excepciones separadas por comas:

```java
public void nombreDelMetodo() throws Excepcion1, Excepcion2 {
    // Código que puede lanzar las excepciones
}
```

### Detalles
- **Excepciones Verificadas**: Las excepciones que deben ser declaradas en la firma del método. Por ejemplo, `IOException`, `SQLException`, etc.
- **Excepciones No Verificadas**: No es necesario declararlas, como `NullPointerException`, `ArrayIndexOutOfBoundsException`, etc.
- La declaración `throws` no maneja la excepción, solo la comunica al llamador del método, quien debe estar preparado para manejarla.

## Ejemplos
### Ejemplo Básico
A continuación se presenta un ejemplo simple que utiliza `throws` para manejar una excepción:

```java
import java.io.FileReader;
import java.io.IOException;

public class EjemploThrows {
    public void leerArchivo(String nombreArchivo) throws IOException {
        FileReader archivo = new FileReader(nombreArchivo);
        // Lógica para leer el archivo
    }
    
    public static void main(String[] args) {
        EjemploThrows ejemplo = new EjemploThrows();
        try {
            ejemplo.leerArchivo("archivo.txt");
        } catch (IOException e) {
            System.out.println("Error al leer el archivo: " + e.getMessage());
        }
    }
}
```

### Ejemplo Múltiple
En este ejemplo, se declaran múltiples excepciones:

```java
public void procesarDatos() throws IOException, NumberFormatException {
    // Lógica que puede lanzar IOException o NumberFormatException
}
```

## Explicación
### Errores Comunes
1. **Olvidar Manejar Excepciones**: Si un método que llama a otro que utiliza `throws` no maneja la excepción, el compilador generará un error.
2. **Declarar Excepciones No Verificadas**: No es necesario declarar excepciones no verificadas, pero hacerlo es redundante.
3. **Confusión entre `throws` y `throw`**: `throws` se usa en la declaración de métodos, mientras que `throw` se utiliza para lanzar una excepción específica dentro del cuerpo del método.

### Notas Adicionales
- Es recomendable utilizar `throws` para métodos que tienen una alta probabilidad de fallar por razones externas, como la entrada/salida de archivos.
- La claridad en la declaración de excepciones ayuda a otros desarrolladores a entender mejor los posibles fallos del método.

## Resumen en Una Línea
La palabra clave `throws` en Java se utiliza para declarar que un método puede lanzar excepciones verificadas, permitiendo un manejo más efectivo de errores.