<!--
Meta Description: # Der `super`-Befehl in Java: Bedeutung und Anwendung ## Synopsis Der `super`-Befehl in Java ermöglicht den Zugriff auf Mitglieder (Methoden und Varia...
Meta Keywords: der, superklasse, super, auf, die
-->

# Der `super`-Befehl in Java: Bedeutung und Anwendung

## Synopsis
Der `super`-Befehl in Java ermöglicht den Zugriff auf Mitglieder (Methoden und Variablen) der übergeordneten Klasse (Superklasse) und wird häufig in der Vererbung verwendet.

## Dokumentation
In Java wird der `super`-Befehl verwendet, um auf die Eigenschaften und Methoden der Elternklasse zuzugreifen. Dies ist besonders nützlich in einer Vererbungshierarchie, wo eine abgeleitete Klasse (Unterklasse) auf die Mitglieder ihrer übergeordneten Klasse (Superklasse) zugreifen möchte. 

### Verwendung
1. **Zugriff auf Variablen der Superklasse**: Wenn eine Variable in der Unterklasse den gleichen Namen hat wie eine Variable in der Superklasse, kann `super.variableName` verwendet werden, um auf die Variable der Superklasse zuzugreifen.
  
2. **Aufruf von Methoden der Superklasse**: Mit `super.methodName()` kann eine Methode der Superklasse aufgerufen werden, auch wenn diese in der Unterklasse überschrieben wurde.
  
3. **Konstruktor der Superklasse**: `super()` kann im Konstruktor einer Unterklasse verwendet werden, um den Konstruktor der Superklasse aufzurufen und so sicherzustellen, dass die Superklasse korrekt initialisiert wird.

### Details
- `super` ist ein Schlüsselwort und kein Funktionsaufruf.
- Es kann nur innerhalb einer Methode oder eines Konstruktors verwendet werden.
- Es muss vor dem Zugriff auf die Mitglieder der Superklasse deklariert werden.

## Beispiele
```java
class Tier {
    String name;

    Tier(String name) {
        this.name = name;
    }

    void zeigeName() {
        System.out.println("Tiername: " + name);
    }
}

class Hund extends Tier {
    String rasse;

    Hund(String name, String rasse) {
        super(name); // Aufruf des Konstruktors der Superklasse
        this.rasse = rasse;
    }

    void zeigeDetails() {
        super.zeigeName(); // Aufruf der Methode der Superklasse
        System.out.println("Rasse: " + rasse);
    }
}

public class Main {
    public static void main(String[] args) {
        Hund meinHund = new Hund("Bello", "Labrador");
        meinHund.zeigeDetails();
    }
}
```

## Erklärung
Ein häufiger Fehler bei der Verwendung von `super` ist, dass Entwickler versuchen, auf Mitglieder der Superklasse zuzugreifen, ohne sicherzustellen, dass die Superklasse initialisiert wurde. Dies kann zu NullPointerExceptions führen. 

Ein weiteres häufiges Missverständnis ist die Verwendung von `super` in statischen Kontexten; `super` kann nur in Instanzmethoden oder Konstruktoren verwendet werden, nicht in statischen Methoden.

## Ein-Satz-Zusammenfassung
Der `super`-Befehl in Java ist entscheidend für den Zugriff auf Mitglieder der übergeordneten Klasse in einer Vererbungshierarchie.