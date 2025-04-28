<!--
Meta Description: # Der Datentyp "int" in Java: Grundlagen und Anwendung ## Synopsis Der Datentyp "int" in Java ist ein grundlegender primitiver Datentyp, der zur Speic...
Meta Keywords: int, der, ist, java, und
-->

# Der Datentyp "int" in Java: Grundlagen und Anwendung

## Synopsis
Der Datentyp "int" in Java ist ein grundlegender primitiver Datentyp, der zur Speicherung von Ganzzahlen verwendet wird. Er spielt eine zentrale Rolle in der Programmierung und ist entscheidend für die Durchführung von Berechnungen und die Steuerung von Programmabläufen.

## Dokumentation
Der "int"-Datentyp in Java wird verwendet, um ganze Zahlen im Bereich von -2.147.483.648 bis 2.147.483.647 zu speichern. Dies entspricht einer 32-Bit-Zahl und ermöglicht eine effiziente Verarbeitung von Ganzzahlen in Programmen. Der "int"-Datentyp wird oft in Schleifen, Bedingungen und mathematischen Berechnungen eingesetzt. 

### Verwendung
Um eine Variable vom Typ "int" zu deklarieren, verwenden Sie die folgende Syntax:

```java
int variableName;
```

Sie können einer "int"-Variablen auch einen Wert zuweisen:

```java
int zahl = 10;
```

Darüber hinaus können Sie mathematische Operationen mit "int"-Variablen durchführen, wie Addition, Subtraktion, Multiplikation und Division.

### Details
- **Größe:** Der "int"-Datentyp belegt 4 Byte (32 Bit) im Speicher.
- **Standardwert:** Der Standardwert für eine nicht initialisierte "int"-Variable ist 0.
- **Berechnung:** Bei mathematischen Operationen, die zu Werten außerhalb des "int"-Bereichs führen, kommt es zu einem Überlauf, was zu unerwarteten Ergebnissen führen kann.

## Beispiele
### Beispiel 1: Deklaration und Initialisierung
```java
int a = 5;
int b = 10;
int summe = a + b; // summe ist jetzt 15
```

### Beispiel 2: Verwendung in einer Schleife
```java
for (int i = 0; i < 5; i++) {
    System.out.println("Der Wert von i ist: " + i);
}
```

### Beispiel 3: Mathematische Operationen
```java
int x = 20;
int y = 3;
int division = x / y; // division ist 6
int rest = x % y; // rest ist 2
```

## Erklärung
Ein häufiges Problem beim Arbeiten mit "int" ist der Überlauf. Wenn eine Rechnung einen Wert produziert, der den Bereich von -2.147.483.648 bis 2.147.483.647 überschreitet, wird der Wert in den negativen Bereich zurückgesetzt, was zu unerwarteten Ergebnissen führen kann. Zum Beispiel:

```java
int maxInt = Integer.MAX_VALUE; // 2.147.483.647
int überlauf = maxInt + 1; // überlauf ist jetzt -2.147.483.648
```

Ein weiterer Punkt ist der Unterschied zwischen ganzzahligen Divisionen und Fließkommadivisionen. Bei der Division von zwei "int"-Variablen wird das Ergebnis ebenfalls als "int" zurückgegeben, wobei der Nachkommabereich verworfen wird.

## Einzeilensummary
Der "int"-Datentyp in Java ist ein 32-Bit primitiver Datentyp, der zur Speicherung und Manipulation von Ganzzahlen verwendet wird.