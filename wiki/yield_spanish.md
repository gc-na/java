<!--
Meta Description: # La palabra clave "yield" en Java: Uso y Funcionalidades ## Sinopsis La palabra clave `yield` en Java se introdujo en la versión 14 como una forma de...
Meta Keywords: yield, case, switch, java, bloque
-->

# La palabra clave "yield" en Java: Uso y Funcionalidades

## Sinopsis
La palabra clave `yield` en Java se introdujo en la versión 14 como una forma de devolver un valor desde un bloque de código de una expresión de tipo `switch`. Permite simplificar la lógica de selección de valores en estructuras de control, proporcionando una alternativa más legible y expresiva a las declaraciones `switch` tradicionales.

## Documentación
### Propósito
La introducción de `yield` tiene como objetivo mejorar la legibilidad y la funcionalidad de los bloques `switch`, permitiendo devolver valores directamente desde ellos. Esto es especialmente útil en situaciones donde se desea asignar un valor a una variable basado en múltiples condiciones.

### Uso
La sintaxis básica para usar `yield` dentro de un bloque `switch` es la siguiente:

```java
variable = switch (expresión) {
    case valor1 -> valorDeRetorno1;
    case valor2 -> valorDeRetorno2;
    default -> valorPorDefecto;
    // Se puede usar yield en un bloque de código más complejo
    case valorN -> {
        // Lógica adicional
        yield valorDeRetornoN;
    }
};
```

### Detalles
- `yield` solo puede ser usado dentro de un bloque `switch`.
- Permite realizar lógica más compleja dentro de un caso, lo que puede ser útil para cálculos o evaluaciones antes de devolver un valor.
- `yield` hace que el código sea más limpio y fácil de entender, especialmente en comparación con el uso de múltiples `return` en métodos o bloques de código.

## Ejemplos
### Ejemplo básico de uso de `yield`
```java
int dia = 3;
String nombreDia = switch (dia) {
    case 1 -> "Lunes";
    case 2 -> "Martes";
    case 3 -> "Miércoles";
    case 4 -> "Jueves";
    case 5 -> "Viernes";
    case 6 -> "Sábado";
    case 7 -> "Domingo";
    default -> {
        yield "Día no válido";
    }
};

System.out.println(nombreDia); // Salida: Miércoles
```

### Ejemplo con lógica adicional
```java
int numero = 10;
String resultado = switch (numero) {
    case 1, 2, 3 -> {
        yield "Pequeño";
    }
    case 4, 5, 6, 7, 8 -> {
        yield "Mediano";
    }
    case 9, 10 -> {
        yield "Grande";
    }
    default -> {
        yield "Número fuera de rango";
    }
};

System.out.println(resultado); // Salida: Grande
```

## Explicación
### Errores comunes y notas
- **Uso incorrecto de `yield`:** `yield` no puede ser usado fuera de un bloque `switch`, lo que puede llevar a errores de compilación si se intenta usar en otro contexto.
- **Confusión con el `return`:** Aunque `yield` puede parecerse a `return`, no debe confundirse con él; `yield` se utiliza específicamente dentro de `switch`, mientras que `return` se usa para salir de métodos.
- **Complejidad innecesaria:** Si bien `yield` permite lógica compleja, es importante no abusar de ello. Un bloque `switch` debe seguir siendo fácil de leer y entender.

## Resumen en una línea
La palabra clave `yield` en Java permite devolver valores desde bloques `switch` de manera más legible y estructurada.