<!--
Meta Description: # La Palabra Clave "continue" en JAVA: Control del Flujo de Ejecución ## Sinopsis La palabra clave `continue` en JAVA es utilizada dentro de estructur...
Meta Keywords: continue, bucle, iteración, con, java
-->

# La Palabra Clave "continue" en JAVA: Control del Flujo de Ejecución

## Sinopsis
La palabra clave `continue` en JAVA es utilizada dentro de estructuras de control de bucles para omitir la iteración actual y continuar con la siguiente. Es una herramienta valiosa para optimizar el flujo de ejecución en programas que requieren saltar ciertas condiciones durante la iteración.

## Documentación
### Propósito
La instrucción `continue` permite a los desarrolladores controlar el flujo de ejecución en bucles `for`, `while` y `do-while`. Al encontrarse con `continue`, el flujo de ejecución se interrumpe para la iteración actual, y el control se transfiere a la siguiente iteración del bucle.

### Uso
El uso de `continue` es simple y se puede aplicar en cualquier bucle. Aquí hay un esquema básico de su implementación:

```java
for (inicialización; condición; incremento) {
    if (condiciónEspecifica) {
        continue; // Salta a la siguiente iteración
    }
    // Código a ejecutar si la condición no se cumple
}
```

### Detalles
- `continue` solo afecta el bucle más interno en el que se encuentra.
- Puede ser utilizado con etiquetas para afectar bucles externos en situaciones más complejas.

## Ejemplos

### Ejemplo 1: Uso básico de `continue` en un bucle `for`
```java
public class ContinueExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i % 2 == 0) {
                continue; // Salta los números pares
            }
            System.out.println(i); // Imprime solo los números impares
        }
    }
}
```

### Ejemplo 2: Uso de `continue` en un bucle `while`
```java
public class ContinueWhileExample {
    public static void main(String[] args) {
        int i = 0;
        while (i < 5) {
            i++;
            if (i == 3) {
                continue; // Salta la iteración cuando i es 3
            }
            System.out.println(i); // Imprime 1, 2, 4, 5
        }
    }
}
```

### Ejemplo 3: Uso de `continue` con etiquetas
```java
public class LabeledContinueExample {
    public static void main(String[] args) {
        outerLoop:
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                if (j == 1) {
                    continue outerLoop; // Salta a la siguiente iteración del bucle externo
                }
                System.out.println("i = " + i + ", j = " + j);
            }
        }
    }
}
```

## Explicación
### Errores Comunes
- **Uso incorrecto de `continue`**: Asegúrate de que `continue` se utiliza dentro de un bucle. Fuera de un contexto de bucle, generará un error de compilación.
- **Confusión con `break`**: No confundas `continue` con `break`. Mientras que `continue` salta a la siguiente iteración, `break` termina el bucle por completo.

### Notas Adicionales
- `continue` puede hacer que el código sea menos legible si se usa en exceso, por lo que se recomienda su uso con moderación. 
- Siempre es mejor mantener la lógica simple y clara para facilitar el mantenimiento del código.

## Resumen en Una Línea
La palabra clave `continue` en JAVA permite omitir la iteración actual de un bucle y continuar con la siguiente, optimizando el flujo de ejecución.