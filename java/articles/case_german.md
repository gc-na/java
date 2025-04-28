<!--
Meta Description: # Case in Java: Verwendung und Bedeutung von switch-Anweisungen ## Synopsis In Java wird das Schlüsselwort `case` verwendet, um in einer `switch`-Anwe...
Meta Keywords: case, die, switch, break, java
-->

# Case in Java: Verwendung und Bedeutung von switch-Anweisungen

## Synopsis
In Java wird das Schlüsselwort `case` verwendet, um in einer `switch`-Anweisung verschiedene Ausführungszweige basierend auf dem Wert einer Variablen zu definieren. Diese Struktur verbessert die Lesbarkeit und Handhabung mehrerer Bedingungen im Vergleich zu verschachtelten `if-else`-Anweisungen.

## Dokumentation
### Zweck
Die `case`-Anweisung in Java wird innerhalb einer `switch`-Anweisung verwendet, um verschiedene Codeabschnitte auszuführen, die auf dem Wert einer bestimmten Variablen basieren. Dies ist besonders nützlich, wenn mehrere Bedingungen überprüft werden müssen, die sich auf den gleichen Ausdruck beziehen.

### Verwendung
Die allgemeine Syntax einer `switch`-Anweisung mit `case` sieht wie folgt aus:

```java
switch (ausdruck) {
    case wert1:
        // Anweisungen für wert1
        break;
    case wert2:
        // Anweisungen für wert2
        break;
    default:
        // Anweisungen, wenn keine der oben genannten Bedingungen zutrifft
}
```

- **ausdruck**: Der Wert, der überprüft wird (z. B. eine Variable oder ein Ausdruck).
- **wert1, wert2**: Die verschiedenen Werte, die mit dem Ausdruck verglichen werden.
- **break**: Beendet die Ausführung der switch-Anweisung. Ohne das `break`-Schlüsselwort würde die Ausführung in den nächsten `case`-Block „hineinfallen“.
- **default**: Optionaler Block, der ausgeführt wird, wenn keine der `case`-Bedingungen erfüllt ist.

### Details
Die `case`-Anweisungen können Werte in Form von Ganzzahlen, Zeichen oder Strings annehmen. Beachten Sie, dass die Werte in den `case`-Anweisungen einzigartig sein müssen. Doppelte Werte führen zu einem Kompilierungsfehler.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von `case` in Java:

### Beispiel 1: Einfache switch-Anweisung
```java
int tag = 3;
String tagName;

switch (tag) {
    case 1:
        tagName = "Montag";
        break;
    case 2:
        tagName = "Dienstag";
        break;
    case 3:
        tagName = "Mittwoch";
        break;
    default:
        tagName = "Ungültiger Tag";
}

System.out.println(tagName); // Ausgabe: Mittwoch
```

### Beispiel 2: Verwendung von Strings
```java
String farbe = "rot";

switch (farbe) {
    case "rot":
        System.out.println("Die Farbe ist Rot.");
        break;
    case "blau":
        System.out.println("Die Farbe ist Blau.");
        break;
    default:
        System.out.println("Unbekannte Farbe.");
}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `case` ist das Fehlen des `break`-Schlüsselworts, was dazu führen kann, dass mehrere `case`-Blöcke ausgeführt werden (sogenanntes „fall-through“). Dies kann nützlich sein, wenn mehrere `case`-Bedingungen identisches Verhalten haben, sollte aber mit Bedacht eingesetzt werden.

Ein weiterer Punkt ist, dass `case`-Werte konstant sein müssen. Variablen oder Ausdrücke, die zur Laufzeit ausgewertet werden, sind nicht zulässig.

## Ein-Satz-Zusammenfassung
Das `case`-Schlüsselwort in Java wird innerhalb von `switch`-Anweisungen verwendet, um verschiedene Ausführungszweige basierend auf dem Wert einer Variablen zu definieren und dadurch den Code lesbarer zu gestalten.