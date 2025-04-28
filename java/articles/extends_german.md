<!--
Meta Description: # Die Verwendung von "extends" in Java: Vererbung und Klassenhierarchien ## Synopsis In Java ist das Schlüsselwort "extends" entscheidend für die Impl...
Meta Keywords: der, die, klasse, von, java
-->

# Die Verwendung von "extends" in Java: Vererbung und Klassenhierarchien

## Synopsis
In Java ist das Schlüsselwort "extends" entscheidend für die Implementierung der Vererbung, die es einer Klasse ermöglicht, Eigenschaften und Methoden einer anderen Klasse zu erben. Dies fördert die Wiederverwendbarkeit von Code und die Schaffung einer klaren Klassenhierarchie.

## Dokumentation
### Zweck
Das Schlüsselwort "extends" wird verwendet, um eine Unterklasse zu definieren, die von einer übergeordneten Klasse erbt. Die Unterklasse erhält Zugriff auf öffentliche und geschützte Mitglieder (Methoden und Variablen) der übergeordneten Klasse. Dies ist ein zentraler Bestandteil des objektorientierten Programmierens in Java, da es die Strukturierung von Code in wiederverwendbare Komponenten ermöglicht.

### Verwendung
Um eine Klasse zu erstellen, die von einer anderen Klasse erbt, wird das Schlüsselwort "extends" gefolgt vom Namen der übergeordneten Klasse verwendet. Ein Beispiel für die Syntax ist:

```java
class Unterklasse extends Überklasse {
    // Methoden und Variablen der Unterklasse
}
```

### Details
- **Einzelvererbung:** In Java unterstützt eine Klasse nur die Vererbung von einer einzigen anderen Klasse. Das bedeutet, dass eine Klasse nicht von mehreren Klassen gleichzeitig erben kann.
- **Konstruktoren:** Der Konstruktor der Unterklasse kann den Konstruktor der übergeordneten Klasse durch den Aufruf von `super()` aufrufen, um sicherzustellen, dass die übergeordneten Mitglieder korrekt initialisiert werden.
- **Methodenüberschreibung:** Eine Unterklasse kann Methoden der übergeordneten Klasse überschreiben, um spezifisches Verhalten zu implementieren.
- **Zugriffsmodifizierer:** Private Mitglieder der übergeordneten Klasse sind in der Unterklasse nicht direkt zugänglich, während öffentliche und geschützte Mitglieder verfügbar sind.

## Beispiele
### Einfaches Beispiel der Vererbung
```java
class Tier {
    void essen() {
        System.out.println("Das Tier isst.");
    }
}

class Hund extends Tier {
    void bellen() {
        System.out.println("Der Hund bellt.");
    }
}

public class Hauptprogramm {
    public static void main(String[] args) {
        Hund meinHund = new Hund();
        meinHund.essen(); // Ausgabe: Das Tier isst.
        meinHund.bellen(); // Ausgabe: Der Hund bellt.
    }
}
```

### Überschreibung einer Methode
```java
class Vogel {
    void singen() {
        System.out.println("Der Vogel singt.");
    }
}

class Spatz extends Vogel {
    @Override
    void singen() {
        System.out.println("Der Spatz zwitschert.");
    }
}

public class Hauptprogramm {
    public static void main(String[] args) {
        Vogel meinVogel = new Spatz();
        meinVogel.singen(); // Ausgabe: Der Spatz zwitschert.
    }
}
```

## Erklärung
### Häufige Fallstricke
- **Vererbung von mehreren Klassen:** Java unterstützt keine Mehrfachvererbung, was bedeutet, dass eine Klasse nicht von mehreren Klassen erben kann. Dies kann zu Verwirrung führen, wenn Entwickler versuchen, diese Funktionalität zu implementieren.
- **Zugriffsmodifizierer:** Entwickler müssen darauf achten, dass private Mitglieder der übergeordneten Klasse in der Unterklasse nicht zugänglich sind. Dies kann zu unerwarteten Fehlern führen, wenn man versucht, auf diese Mitglieder zuzugreifen.
- **Konstruktoren:** Wenn die übergeordnete Klasse keinen Standardkonstruktor hat, muss die Unterklasse explizit einen Konstruktor definieren, der den Konstruktor der übergeordneten Klasse aufruft.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "extends" in Java ermöglicht die Vererbung von Klassen, was die Wiederverwendbarkeit von Code und die Schaffung klarer Klassenhierarchien fördert.