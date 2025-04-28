<!--
Meta Description: # Klasse in JAVA: Grundlagen, Verwendung und Beispiele ## Synopsis Eine Klasse in Java ist eine grundlegende Baueinheit der objektorientierten Program...
Meta Keywords: public, java, klasse, die, eine
-->

# Klasse in JAVA: Grundlagen, Verwendung und Beispiele

## Synopsis
Eine Klasse in Java ist eine grundlegende Baueinheit der objektorientierten Programmierung, die als Vorlage für die Erstellung von Objekten dient.

## Dokumentation

### Zweck
In Java ist eine Klasse eine Blaupause für Objekte. Sie definiert Eigenschaften (Attribute) und Verhalten (Methoden), die die Objekte dieser Klasse besitzen. Klassen ermöglichen es Entwicklern, Daten und Funktionen zusammenzufassen und die Wiederverwendbarkeit des Codes zu fördern.

### Verwendung
Um eine Klasse in Java zu definieren, verwendet man das Schlüsselwort `class`, gefolgt vom Namen der Klasse. Die Konvention ist, dass Klassennamen mit einem Großbuchstaben beginnen. Hier ist ein einfaches Beispiel für die Definition einer Klasse:

```java
public class Auto {
    // Attribute
    private String marke;
    private int baujahr;

    // Konstruktor
    public Auto(String marke, int baujahr) {
        this.marke = marke;
        this.baujahr = baujahr;
    }

    // Methode
    public void fahren() {
        System.out.println("Das Auto fährt.");
    }

    // Getter
    public String getMarke() {
        return marke;
    }

    public int getBaujahr() {
        return baujahr;
    }
}
```

### Details
- **Zugriffsmodifikatoren**: Klassenmitglieder (Attribute und Methoden) können mithilfe von Zugriffsmodifikatoren (public, private, protected) geschützt werden.
- **Konstruktoren**: Eine Klasse kann Konstruktoren haben, um Objekte mit bestimmten Werten zu initialisieren.
- **Vererbung**: Klassen können von anderen Klassen erben, wodurch Eigenschaften und Methoden übernommen werden. Dies geschieht mit dem Schlüsselwort `extends`.

## Beispiele

### Beispiel 1: Einfache Klassendefinition
```java
public class Tier {
    private String name;

    public Tier(String name) {
        this.name = name;
    }

    public void lautGeben() {
        System.out.println(name + " macht ein Geräusch.");
    }
}

public class Main {
    public static void main(String[] args) {
        Tier hund = new Tier("Hund");
        hund.lautGeben();
    }
}
```

### Beispiel 2: Vererbung
```java
public class Fahrzeug {
    public void fahren() {
        System.out.println("Das Fahrzeug fährt.");
    }
}

public class Fahrrad extends Fahrzeug {
    @Override
    public void fahren() {
        System.out.println("Das Fahrrad fährt.");
    }
}

public class Main {
    public static void main(String[] args) {
        Fahrrad meinFahrrad = new Fahrrad();
        meinFahrrad.fahren();
    }
}
```

## Erklärung
Ein häufiges Problem bei der Arbeit mit Klassen in Java ist die falsche Verwendung von Zugriffsmodifikatoren. Wenn Attribute als `private` deklariert werden, müssen Getter-Methoden bereitgestellt werden, um auf diese Attribute zuzugreifen. Ein weiteres häufiges Missverständnis betrifft Konstruktoren: Wenn kein Konstruktor definiert wird, stellt Java einen Standardkonstruktor zur Verfügung, der keine Parameter akzeptiert.

## Zusammenfassung in einem Satz
Eine Klasse in Java ist eine grundlegende Struktur der objektorientierten Programmierung, die zur Definition von Objekten mit spezifischen Attributen und Methoden dient.