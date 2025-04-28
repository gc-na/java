<!--
Meta Description: # Sealed Classes in Java: Eine umfassende Anleitung ## Synopsis Sealed Classes in Java ermöglichen eine präzise Kontrolle darüber, welche Klassen eine...
Meta Keywords: sealed, eine, klasse, und, die
-->

# Sealed Classes in Java: Eine umfassende Anleitung

## Synopsis
Sealed Classes in Java ermöglichen eine präzise Kontrolle darüber, welche Klassen eine bestimmte Klasse erweitern können, und fördern somit eine bessere Strukturierung und Sicherheit im Code.

## Documentation
Sealed Classes wurden in Java 15 als Vorschau-Feature eingeführt und sind seit Java 17 stabil. Sie erlauben es Entwicklern, eine Klasse als "sealed" zu deklarieren, was bedeutet, dass nur bestimmte, vorher definierte Unterklassen diese Klasse erweitern dürfen. Dies bietet eine klare Hierarchie und vermeidet unerwünschte Erweiterungen.

### Zweck
Der Hauptzweck von Sealed Classes ist es, die Vererbung zu steuern und sicherzustellen, dass nur definierte Klassen eine bestimmte Klasse erweitern können. Dies kann hilfreich sein, um eine kontrollierte API zu schaffen, die sich nicht unvorhergesehen ändert.

### Verwendung
Um eine Klasse als sealed zu deklarieren, verwendet man das Schlüsselwort `sealed` gefolgt von der Klassendeklaration. Die erlaubten Unterklassen müssen mit den Schlüsselwörtern `permits` gefolgt von den Klassennamen angegeben werden. Hier ist ein Beispiel:

```java
public sealed class Shape
    permits Circle, Rectangle {
    // ...
}

public final class Circle extends Shape {
    // Implementierung
}

public final class Rectangle extends Shape {
    // Implementierung
}
```

In diesem Beispiel ist die Klasse `Shape` als sealed deklariert und erlaubt nur die Erweiterung durch die Klassen `Circle` und `Rectangle`.

### Details
- **Finale Unterklassen**: Unterklassen einer sealed Klasse müssen als `final`, `sealed` oder `non-sealed` deklariert werden. `final` bedeutet, dass sie nicht weiter erweitert werden können, während `sealed` es erlaubt, weitere kontrollierte Unterklassen zu definieren. `non-sealed` erlaubt es jeder Klasse, diese Klasse zu erweitern.
- **Kompilierungsfehler**: Wenn eine nicht erlaubte Klasse versucht, eine sealed Klasse zu erweitern, wird dies vom Compiler als Fehler gemeldet.

## Beispiele
Hier sind einige einfache Beispiele für die Verwendung von Sealed Classes:

### Beispiel 1: Einfache Sealed Klasse
```java
public sealed class Vehicle
    permits Car, Truck {
    // ...
}

public final class Car extends Vehicle {
    // Implementierung
}

public final class Truck extends Vehicle {
    // Implementierung
}
```

### Beispiel 2: Sealed Klasse mit weiteren Sealed Unterklassen
```java
public sealed class Animal
    permits Dog, Cat {
}

public sealed class Dog extends Animal
    permits Bulldog, Beagle {
}

public final class Bulldog extends Dog {
    // Implementierung
}

public final class Beagle extends Dog {
    // Implementierung
}

public final class Cat extends Animal {
    // Implementierung
}
```

## Erklärung
Eine häufige Herausforderung bei der Verwendung von Sealed Classes ist das Verständnis der Einschränkungen und der korrekten Deklaration der Unterklassen. Entwickler sollten sicherstellen, dass sie die erlaubten Unterklassen korrekt angeben und sich bewusst sein, dass alle Unterklassen einer sealed Klasse bestimmte Zugriffsmodifizierer (wie `final`, `sealed` oder `non-sealed`) benötigen.

Ein weiterer Punkt ist, dass die Verwendung von sealed Klassen die Flexibilität im Vergleich zu normalen Klassen einschränken kann. Daher sollten Entwickler sorgfältig abwägen, wo und wann sie diese Funktionalität einsetzen.

## One Line Summary
Sealed Classes in Java bieten eine präzise Kontrolle über die Vererbung und fördern eine sichere und strukturiert API.