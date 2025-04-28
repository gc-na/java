<!--
Meta Description: # yield in JAVA: Eine umfassende Anleitung zur Nutzung und Bedeutung ## Synopsis Das `yield` Schlüsselwort in JAVA ist ein neues Feature, das mit der ...
Meta Keywords: yield, switch, von, java, case
-->

# yield in JAVA: Eine umfassende Anleitung zur Nutzung und Bedeutung

## Synopsis
Das `yield` Schlüsselwort in JAVA ist ein neues Feature, das mit der Einführung von Java 14 als Vorschau-Feature und ab Java 15 stabilisiert wurde. Es wird hauptsächlich in der Kontext von `switch`-Ausdrücken verwendet, um Werte zurückzugeben und den Code lesbarer zu gestalten.

## Documentation
### Zweck
Das `yield` Schlüsselwort ermöglicht es Entwicklern, innerhalb eines `switch`-Ausdrucks einen Wert zurückzugeben. Es verbessert die Lesbarkeit und Wartbarkeit des Codes, indem es einen klaren und prägnanten Weg bietet, Ergebnisse von `switch`-Konstruktionen zu erhalten.

### Verwendung
Der `yield` Befehl kann nur innerhalb eines `switch`-Blocks verwendet werden. Er wird verwendet, um den Rückgabewert für den jeweiligen Fall zu definieren. Hier ist die allgemeine Syntax:

```java
int ergebnis = switch (variable) {
    case wert1 -> {
        // Block von Anweisungen
        yield rückgabewert1;
    }
    case wert2 -> {
        // Block von Anweisungen
        yield rückgabewert2;
    }
    default -> {
        // Block von Anweisungen
        yield defaultWert;
    }
};
```

### Details
- `yield` kann nur in einem `switch`-Ausdruck verwendet werden, nicht in einer traditionellen `switch`-Anweisung.
- `yield` ermöglicht die Ausführung mehrerer Anweisungen innerhalb eines Falles, bevor ein Wert zurückgegeben wird.
- Es ist wichtig, dass jeder Fall einen Rückgabewert haben muss; andernfalls führt dies zu einem Kompilierungsfehler.

## Examples
Hier sind einige grundlegende Beispiele zur Verwendung von `yield` in JAVA:

### Beispiel 1: Einfache Verwendung von yield
```java
int tag = 2;
String woTag = switch (tag) {
    case 1 -> "Montag";
    case 2 -> "Dienstag";
    case 3 -> "Mittwoch";
    default -> {
        yield "Ungültiger Tag";
    }
};
System.out.println(woTag); // Ausgabe: Dienstag
```

### Beispiel 2: Mehrere Anweisungen im Fall
```java
int zahl = 5;
String beschreibung = switch (zahl) {
    case 1 -> {
        yield "Eins";
    }
    case 2, 3 -> {
        yield "Zwei oder Drei";
    }
    case 4 -> {
        // Zusätzliche Logik
        System.out.println("Zahl ist Vier");
        yield "Vier";
    }
    default -> {
        yield "Unbekannt";
    }
};
System.out.println(beschreibung); // Ausgabe: Unbekannt
```

## Explanation
Ein häufiger Fehler beim Einsatz von `yield` ist die Annahme, dass es wie `return` in Methoden funktioniert. `yield` gibt einen Wert innerhalb eines `switch`-Ausdrucks zurück, während `return` eine Methode beendet. Ein weiterer Punkt ist, dass man sicherstellen muss, dass jeder `case` einen Rückgabewert hat, um Kompilierungsfehler zu vermeiden. 

Zusätzlich sollte beachtet werden, dass die Verwendung von `yield` in `switch`-Ausdrücken die Lesbarkeit des Codes erhöht, insbesondere wenn mehrere Anweisungen innerhalb eines Falls erforderlich sind.

## One Line Summary
Das `yield` Schlüsselwort in JAVA ermöglicht es, Werte aus `switch`-Ausdrücken zurückzugeben und verbessert die Lesbarkeit des Codes.