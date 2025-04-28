<!--
Meta Description: # Exporte in Java: Eine umfassende Anleitung zur Verwendung von export ## Synopsis In Java ermöglicht das Schlüsselwort `exports` die Steuerung des Zu...
Meta Keywords: java, exports, module, das, die
-->

# Exporte in Java: Eine umfassende Anleitung zur Verwendung von export

## Synopsis
In Java ermöglicht das Schlüsselwort `exports` die Steuerung des Zugriffs auf Pakete innerhalb eines Moduls und definiert, welche Pakete für andere Module zugänglich sind.

## Dokumentation
Das `exports`-Schlüsselwort ist ein zentraler Bestandteil des Modulsystems, das mit Java 9 eingeführt wurde. Es wird verwendet, um den Zugriff auf die öffentlichen Klassen eines Moduls zu steuern, indem es angibt, welche Pakete innerhalb des Moduls für andere Module sichtbar sind. Dies trägt zur Kapselung und Modularität in Java-Anwendungen bei.

### Zweck
- **Sichtbarkeit**: Bestimmt, welche Pakete eines Moduls von anderen Modulen verwendet werden können.
- **Kapselung**: Hilft dabei, die Implementierungsdetails eines Moduls zu verstecken und nur die benötigten Komponenten zur Verfügung zu stellen.

### Verwendung
Das `exports`-Schlüsselwort wird in der `module-info.java`-Datei deklariert. Hier ist die allgemeine Syntax:

```java
module Modulname {
    exports paketname;
}
```

### Details
- Mehrere Pakete können gleichzeitig exportiert werden, indem sie durch Kommas getrennt aufgelistet werden:
  ```java
  exports paketname1, paketname2;
  ```
- Es ist auch möglich, den Zugriff auf ein Paket nur für bestimmte Module zu beschränken, indem man den `to`-Teil hinzufügt:
  ```java
  exports paketname to anderesModul;
  ```

## Beispiele
### Beispiel 1: Einfaches Paket-Export
```java
module meinModul {
    exports com.meinpaket;
}
```
In diesem Beispiel wird das Paket `com.meinpaket` für andere Module zugänglich gemacht.

### Beispiel 2: Export mehrerer Pakete
```java
module meinModul {
    exports com.meinpaket1, com.meinpaket2;
}
```
Hier werden zwei Pakete gleichzeitig exportiert.

### Beispiel 3: Export mit Zugriffsbeschränkung
```java
module meinModul {
    exports com.meinpaket to anderesModul;
}
```
In diesem Beispiel kann nur das Modul `anderesModul` auf das Paket `com.meinpaket` zugreifen.

## Erklärung
Ein häufiges Missverständnis ist, dass das `exports`-Schlüsselwort nur für öffentliche Klassen gilt. Alle Klassen in einem Paket, die nicht als privat deklariert sind, sind somit für andere Module sichtbar, wenn das Paket exportiert wird. 

Ein weiterer Punkt ist, dass beim Export eines Pakets alle öffentlichen Typen und Mitglieder innerhalb des Pakets ebenfalls exportiert werden, was bedeutet, dass man sorgfältig planen sollte, welche APIs man anderen Modulen zur Verfügung stellt, um die Integrität des Moduls zu wahren.

## Zusammenfassung in einer Zeile
Das `exports`-Schlüsselwort in Java ermöglicht die gezielte Freigabe von Paketen für andere Module und fördert die Modularität in der Softwareentwicklung.