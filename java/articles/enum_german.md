<!--
Meta Description: # Enum in Java: Eine umfassende Anleitung zu Aufzählungstypen ## Synopsis Enums in Java sind eine spezielle Art von Klasse, die eine feste Menge von k...
Meta Keywords: enum, enums, java, von, eine
-->

# Enum in Java: Eine umfassende Anleitung zu Aufzählungstypen

## Synopsis
Enums in Java sind eine spezielle Art von Klasse, die eine feste Menge von konstanten Werten definiert. Sie verbessern die Lesbarkeit des Codes und bieten Typsicherheit.

## Dokumentation
### Zweck
Enums (kurz für "Enumerations") ermöglichen es Entwicklern, eine Gruppe von konstanten Werten unter einem gemeinsamen Typ zu definieren. Sie sind besonders nützlich, wenn eine Variable nur eine bestimmte Anzahl von Werten annehmen kann, wie z.B. Wochentage, Statuscodes oder Benutzerrollen.

### Verwendung
Enums werden in Java mit dem Schlüsselwort `enum` deklariert. Sie können in einer eigenen Datei oder innerhalb einer anderen Klasse definiert werden. Ein Enum kann auch Methoden, Konstruktoren und Felder enthalten. 

```java
public enum Wochentag {
    MONTAG, DIENSTAG, MITTWOCH, DONNERSTAG, FREITAG, SAMSTAG, SONNTAG;
}
```

### Details
- **Typsicherheit**: Enums bieten eine starke Typprüfung zur Compile-Zeit. Dies reduziert die Wahrscheinlichkeit von Fehlern zur Laufzeit.
- **Methoden**: Enums können eigene Methoden haben, die spezifische Funktionen auf den Enum-Werten ausführen.
- **Vergleich**: Enum-Werte können mithilfe des `==`-Operators oder der `equals()`-Methode verglichen werden.

## Beispiele
### Einfaches Enum-Beispiel
```java
public enum Farbe {
    ROT, GRÜN, BLAU;
}

public class TestFarbe {
    public static void main(String[] args) {
        Farbe meineFarbe = Farbe.ROT;
        System.out.println("Die gewählte Farbe ist: " + meineFarbe);
    }
}
```

### Enum mit Methoden
```java
public enum Wochentag {
    MONTAG("Montag"), DIENSTAG("Dienstag"), MITTWOCH("Mittwoch");

    private String name;

    Wochentag(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

public class TestWochentag {
    public static void main(String[] args) {
        for (Wochentag tag : Wochentag.values()) {
            System.out.println(tag.getName());
        }
    }
}
```

## Erklärung
### Häufige Stolpersteine und Hinweise
- **Enums sind nicht erweiterbar**: Enums in Java können nicht von anderen Klassen abgeleitet werden, da sie implizit von der Klasse `java.lang.Enum` erben.
- **Enums und Switch-Anweisungen**: Enums können in Switch-Anweisungen verwendet werden, was den Code lesbarer und einfacher macht.
- **Persistenz**: Beim Speichern von Enum-Werten in einer Datenbank ist es wichtig, die Enum-Werte konsistent zu halten, um Fehler zu vermeiden.

## Ein-Satz-Zusammenfassung
Enums in Java sind eine leistungsstarke Funktion zur Definition von konstanten Werten mit Typsicherheit, die die Lesbarkeit und Wartbarkeit des Codes erhöhen.