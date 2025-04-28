<!--
Meta Description: # Import in Java: Ein Leitfaden für Import-Anweisungen und deren Verwendung ## Synopsis In Java ist das `import`-Schlüsselwort entscheidend für das Ei...
Meta Keywords: import, java, klassen, die, der
-->

# Import in Java: Ein Leitfaden für Import-Anweisungen und deren Verwendung

## Synopsis
In Java ist das `import`-Schlüsselwort entscheidend für das Einbinden von Klassen und Paketen, die nicht im aktuellen Namensraum vorhanden sind. Es ermöglicht Entwicklern, auf externe Bibliotheken und eigene Klassen zuzugreifen, ohne den vollständigen Paketnamen angeben zu müssen.

## Dokumentation
Das `import`-Schlüsselwort in Java wird verwendet, um Klassen, Schnittstellen und Pakete in eine Java-Datei zu integrieren. Es ermöglicht eine einfachere Handhabung von Code, indem es die Notwendigkeit reduziert, den vollqualifizierten Namen einer Klasse ständig zu verwenden.

### Zweck
Der Hauptzweck der `import`-Anweisung ist die Vereinfachung der Nutzung von Klassen, die sich in anderen Paketen befinden. Anstatt den vollständigen Pfad zur Klasse anzugeben, kann `import` verwendet werden, um die Klasse direkt zugänglich zu machen.

### Verwendung
Die `import`-Anweisung wird typischerweise am Anfang einer Java-Datei platziert, bevor die Klassendeklaration folgt. Es gibt zwei Hauptarten von Imports:

1. **Einzelner Import**: Importiert eine spezifische Klasse.
   ```java
   import java.util.List;
   ```

2. **Import aller Klassen eines Pakets**: Importiert alle Klassen eines bestimmten Pakets.
   ```java
   import java.util.*;
   ```

### Details
- Der Import von Paketen erfolgt in der Reihenfolge, in der sie deklariert werden.
- Es ist nicht notwendig, Klassen aus dem aktuellen Paket zu importieren, da sie automatisch verfügbar sind.
- Die `import`-Anweisung kann mehrmals verwendet werden, um mehrere Klassen oder Pakete zu importieren.

## Beispiele
### Beispiel 1: Einzelner Import
```java
import java.util.ArrayList;

public class Beispiel {
    public static void main(String[] args) {
        ArrayList<String> liste = new ArrayList<>();
        liste.add("Hallo, Welt!");
        System.out.println(liste);
    }
}
```

### Beispiel 2: Import aller Klassen eines Pakets
```java
import java.util.*;

public class Beispiel {
    public static void main(String[] args) {
        HashMap<String, Integer> map = new HashMap<>();
        map.put("Eins", 1);
        System.out.println(map);
    }
}
```

## Erklärung
Eine häufige Falle ist das Verwechseln von Importen mit dem Packagenamen. Das `import`-Schlüsselwort bezieht sich nur auf Klassen oder Schnittstellen innerhalb eines Pakets und nicht auf das Paket selbst. Außerdem kann es zu Namenskonflikten kommen, wenn zwei Klassen mit dem gleichen Namen aus unterschiedlichen Paketen importiert werden. In solchen Fällen muss der vollqualifizierte Name verwendet werden, um die richtige Klasse zu referenzieren.

## Ein Satz Zusammenfassung
Die `import`-Anweisung in Java erleichtert den Zugriff auf Klassen und Pakete, indem sie die Notwendigkeit reduziert, vollständige Pfadnamen zu verwenden.