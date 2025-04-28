<!--
Meta Description: # Record in Java: Eine umfassende Anleitung zu Datentransferobjekten ## Synopsis Das `record`-Schlüsselwort in Java ermöglicht die einfache Erstellung...
Meta Keywords: record, die, von, und, java
-->

# Record in Java: Eine umfassende Anleitung zu Datentransferobjekten

## Synopsis
Das `record`-Schlüsselwort in Java ermöglicht die einfache Erstellung von Datentransferobjekten (DTOs), die unveränderlich sind und direkt aus den Feldern generierte Methoden wie `equals()`, `hashCode()` und `toString()` bieten.

## Dokumentation
In Java 14 eingeführt und in späteren Versionen (ab Java 16 als endgültiges Feature) weiterentwickelt, ermöglicht `record` die Definition von Klassen, die hauptsächlich Daten halten. Diese Klassen sind eine spezielle Art von finalen Klassen, die automatisch die Boilerplate-Codes für Konstruktoren und Methoden generieren.

### Zweck
Der Hauptzweck von `record` ist es, die Erstellung einfacher Datenkarrieren zu erleichtern. Es ermöglicht Entwicklern, sich auf die Logik ihrer Anwendungen zu konzentrieren, ohne sich um die repetitive Implementierung von Methoden zur Verwaltung von Datenstrukturen kümmern zu müssen.

### Verwendung
Ein `record` wird ähnlich wie eine normale Klasse deklariert, verwendet jedoch das Schlüsselwort `record` anstelle von `class`. Hier ist die grundlegende Syntax:

```java
record NameDesRecords(Typ feld1, Typ feld2) { }
```

### Details
- `record`-Klassen sind final und können nicht erweitert werden.
- Alle Felder sind standardmäßig privat und final.
- Es werden automatisch Konstruktoren, `equals()`, `hashCode()` und `toString()` generiert, basierend auf den Feldern, die im `record` definiert sind.
- `record`-Klassen können auch Methoden, Konstruktoren und statische Felder enthalten, jedoch können sie keine Vererbung verwenden.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `record`.

### Beispiel 1: Einfacher Record
```java
public record Person(String name, int alter) { }

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Max", 30);
        System.out.println(person.name()); // Ausgabe: Max
        System.out.println(person.alter()); // Ausgabe: 30
        System.out.println(person); // Ausgabe: Person[name=Max, alter=30]
    }
}
```

### Beispiel 2: Record mit zusätzlicher Methode
```java
public record Rechteck(double breite, double hoehe) {
    public double flaeche() {
        return breite * hoehe;
    }
}

public class Main {
    public static void main(String[] args) {
        Rechteck rechteck = new Rechteck(5, 3);
        System.out.println(rechteck.flaeche()); // Ausgabe: 15.0
    }
}
```

## Erklärung
Einige häufige Fallstricke und zusätzliche Hinweise zur Verwendung von `record` in Java:

- **Unveränderlichkeit**: Da `record`-Felder final sind, können sie nach der Erstellung nicht mehr geändert werden. Dies kann zu Verwirrung führen, wenn Entwickler versuchen, die Werte zu aktualisieren.
- **Vererbung**: `record`-Klassen unterstützen keine Vererbung. Dies kann in Fällen einschränkend sein, wenn eine Hierarchie von Datentypen erforderlich ist.
- **Konstruktoren**: Es ist möglich, benutzerdefinierte Konstruktoren zu definieren, aber diese müssen die Parameter der Felder abdecken und können keine zusätzlichen Felder hinzufügen.

## Ein Satz Zusammenfassung
Das `record`-Schlüsselwort in Java vereinfacht die Erstellung von unveränderlichen Datentransferobjekten, indem es automatisch Boilerplate-Code für die Verwaltung von Datenfeldern generiert.