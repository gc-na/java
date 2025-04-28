<!--
Meta Description: # Verwendung von 'var' in Java: Dynamische Typisierung leicht gemacht ## Synopsis Der Schlüsselwort `var` in Java ermöglicht eine vereinfachte Typdekl...
Meta Keywords: var, die, kann, java, nicht
-->

# Verwendung von 'var' in Java: Dynamische Typisierung leicht gemacht

## Synopsis
Der Schlüsselwort `var` in Java ermöglicht eine vereinfachte Typdeklaration durch inferierte Typen, was den Code leserlicher und wartungsfreundlicher macht.

## Dokumentation
In Java 10 wurde das Schlüsselwort `var` eingeführt, um die Typinferenz zu ermöglichen. Dies bedeutet, dass der Compiler den Datentyp einer Variable basierend auf dem zugewiesenen Wert automatisch bestimmen kann. `var` kann für lokale Variablen verwendet werden, die innerhalb von Methoden, Konstruktoren oder Initialisierungsblöcken deklariert sind. 

### Zweck
Der Hauptzweck von `var` ist es, die Lesbarkeit des Codes zu erhöhen und Boilerplate-Code zu reduzieren. Es erleichtert die Arbeit mit generischen Typen und kann oft die Notwendigkeit verringern, lange und komplexe Typen zu schreiben.

### Verwendung
Um `var` zu verwenden, deklarieren Sie eine lokale Variable wie folgt:

```java
var zahl = 10; // Der Compiler erkennt, dass 'zahl' vom Typ int ist
var text = "Hallo Welt"; // 'text' wird als String erkannt
```

Es ist wichtig zu beachten, dass `var` nur für lokale Variablen verwendet werden kann und nicht für Felder, Parameter oder Rückgabewerte von Methoden.

### Details
- `var` kann nicht mit null initialisiert werden, da der Compiler den Typ nicht ableiten kann:
  ```java
  var unbekannt; // Fehler: Variable kann nicht ohne Initialisierung deklariert werden
  ```
- `var` kann nicht für Arrays verwendet werden, wenn die Dimensionen nicht angegeben sind:
  ```java
  var array = new int[10]; // Korrekt
  var leeresArray = new int[]; // Fehler: Typ kann nicht abgeleitet werden
  ```
- Die Verwendung von `var` kann die Lesbarkeit des Codes verringern, wenn der Typ nicht offensichtlich ist.

## Beispiele
### Beispiel 1: Einfache Typinferenz
```java
var anzahl = 5; // int
var preis = 19.99; // double
```

### Beispiel 2: Verwendung mit Collections
```java
var liste = new ArrayList<String>(); // ArrayList<String>
liste.add("Java");
```

### Beispiel 3: Lambdas und Streams
```java
var namen = List.of("Anna", "Bert", "Charlie");
var gefilterteNamen = namen.stream()
                           .filter(name -> name.startsWith("A"))
                           .collect(Collectors.toList());
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `var` ist die Unsicherheit über den abgeleiteten Typ. Wenn der Typ nicht offensichtlich ist oder wenn eine komplexe Initialisierung erforderlich ist, kann dies zu Verwirrung führen. Eine weitere Herausforderung ist, dass `var` nicht für die Definition von Feldern oder Methodenparametern verwendet werden kann. Daher sollten Entwickler sorgfältig abwägen, wann `var` sinnvoll eingesetzt wird, um die Lesbarkeit und Wartbarkeit des Codes nicht zu beeinträchtigen.

## Einzeiler Zusammenfassung
Das Schlüsselwort `var` in Java ermöglicht die einfache Deklaration von Variablen durch Typinferenz, was zu einem klareren und prägnanteren Code führt.