<!--
Meta Description: # Das Schlüsselwort "default" in Java: Eine umfassende Erklärung ## Synopsis Das Schlüsselwort "default" in Java wird verwendet, um Standardmethoden i...
Meta Keywords: die, das, eine, interfaces, der
-->

# Das Schlüsselwort "default" in Java: Eine umfassende Erklärung

## Synopsis
Das Schlüsselwort "default" in Java wird verwendet, um Standardmethoden in Interfaces zu definieren, die eine Implementierung bieten. Diese Funktionalität ermöglicht es Entwicklern, Interfaces mit konkretem Verhalten zu erweitern, ohne die bestehenden Implementierungen zu beeinträchtigen.

## Dokumentation
Das Schlüsselwort "default" wurde mit Java 8 eingeführt und ermöglicht es Entwicklern, Standardmethoden in Interfaces zu deklarieren. Eine Standardmethode ist eine Methode, die nicht abstrakt ist und eine Implementierung innerhalb des Interfaces selbst hat. Dies ist besonders nützlich, um bestehende Interfaces zu erweitern, ohne die bestehenden Implementierungen der Klassen zu ändern, die dieses Interface bereits implementieren.

### Verwendung
Um eine Standardmethode zu definieren, wird das Schlüsselwort "default" gefolgt von der Methodensignatur und der Implementierung verwendet. Hier ist die grundlegende Syntax:

```java
public interface MeinInterface {
    default void meineStandardmethode() {
        // Implementierung der Standardmethode
    }
}
```

### Details
- **Kompatibilität**: Standardmethoden fördern die Rückwärtskompatibilität, indem sie es ermöglichen, neue Methoden zu Interfaces hinzuzufügen, ohne bestehende Implementierungen zu brechen.
- **Mehrfachvererbung**: Wenn eine Klasse zwei Interfaces mit identischen Standardmethoden implementiert, muss die Klasse die Methode überschreiben, um sicherzustellen, welche Implementierung verwendet werden soll.
- **Annotations**: Standardmethoden können mit Annotations versehen werden, genau wie gewöhnliche Methoden.

## Beispiele

### Beispiel 1: Einfache Standardmethode
```java
public interface Fahrzeug {
    default void starten() {
        System.out.println("Das Fahrzeug startet.");
    }
}

class Auto implements Fahrzeug {
    // Auto erbt die Standardmethode starten
}

public class Main {
    public static void main(String[] args) {
        Auto meinAuto = new Auto();
        meinAuto.starten(); // Ausgabe: Das Fahrzeug startet.
    }
}
```

### Beispiel 2: Überschreiben einer Standardmethode
```java
public interface Tier {
    default void lautGeben() {
        System.out.println("Das Tier macht ein Geräusch.");
    }
}

class Hund implements Tier {
    @Override
    public void lautGeben() {
        System.out.println("Der Hund bellt.");
    }
}

public class Main {
    public static void main(String[] args) {
        Hund meinHund = new Hund();
        meinHund.lautGeben(); // Ausgabe: Der Hund bellt.
    }
}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von Standardmethoden ist das Überschreiben in erstellten Klassen. Wenn zwei Interfaces mit der gleichen Methode implementiert werden, die als Standardmethode definiert ist, muss die Klasse die Methode überschreiben, um Konflikte zu vermeiden. Ein weiterer Punkt ist, dass Standardmethoden nicht in abstrakten Klassen verwendet werden können, da sie bereits in der Natur einer abstrakten Klasse eine Implementierung erfordern.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort "default" in Java ermöglicht die Definition von Standardmethoden in Interfaces, die eine Implementierung bieten und so die Rückwärtskompatibilität fördern.