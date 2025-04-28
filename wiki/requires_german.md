<!--
Meta Description: # Verwendet: Ein Überblick über das Schlüsselwort "requires" in Java ## Synopsis Das Schlüsselwort "requires" in Java wird hauptsächlich im Kontext vo...
Meta Keywords: requires, java, module, die, abhängigkeiten
-->

# Verwendet: Ein Überblick über das Schlüsselwort "requires" in Java

## Synopsis
Das Schlüsselwort "requires" in Java wird hauptsächlich im Kontext von Modulen verwendet, um Abhängigkeiten zwischen verschiedenen Modulen zu definieren. Es ist ein grundlegender Bestandteil des Java Platform Module Systems (JPMS), das mit Java 9 eingeführt wurde.

## Dokumentation
### Zweck
Das Schlüsselwort "requires" dient dazu, die Abhängigkeiten eines Java-Moduls zu deklarieren. Es ermöglicht einem Modul, die Funktionalitäten eines anderen Moduls zu nutzen, und sorgt dafür, dass die entsprechenden Module beim Kompilieren und Ausführen korrekt geladen werden.

### Verwendung
Das Schlüsselwort wird in der Modul-Info-Datei (module-info.java) verwendet. Hier ist die grundlegende Syntax:

```java
module Modulname {
    requires Abhängigkeitsmodul;
}
```

### Details
- **Moduldefinition**: "requires" wird in der Moduldefinition verwendet, um anzugeben, welche Module benötigt werden.
- **Transitive Abhängigkeiten**: Mit "requires transitive" kann ein Modul auch die Abhängigkeiten eines anderen Moduls an seine eigenen Abhängigkeiten weitergeben.
- **Optionale Abhängigkeiten**: Mit "requires static" können Abhängigkeiten deklariert werden, die nur zur Kompilierzeit benötigt werden und nicht zur Laufzeit.

## Beispiele
### Beispiel 1: Einfache Verwendung
```java
module MeinModul {
    requires AndereBibliothek;
}
```
In diesem Beispiel benötigt "MeinModul" die Funktionalitäten von "AndereBibliothek".

### Beispiel 2: Transitive Abhängigkeiten
```java
module MeinModul {
    requires transitive AndereBibliothek;
}
```
Hier gibt "MeinModul" die Abhängigkeit zu "AndereBibliothek" an, sodass alle Module, die "MeinModul" verwenden, auch Zugriff auf "AndereBibliothek" haben.

### Beispiel 3: Statische Abhängigkeit
```java
module MeinModul {
    requires static TestBibliothek;
}
```
In diesem Fall wird "TestBibliothek" nur zum Kompilieren benötigt und nicht zur Laufzeit.

## Erklärung
Ein häufiger Fehler ist das Vergessen, die "requires"-Deklaration in der Modul-Info-Datei hinzuzufügen, was zu Kompilierungsfehlern führen kann. Zudem sollten Entwickler darauf achten, dass keine zirkulären Abhängigkeiten zwischen Modulen entstehen, da dies zu Problemen beim Laden der Module führen kann. Es ist auch wichtig, die Sichtbarkeit von Paketen innerhalb der Module zu berücksichtigen, um sicherzustellen, dass alle benötigten Klassen verfügbar sind.

## Einzeilige Zusammenfassung
Das Schlüsselwort "requires" in Java wird verwendet, um Modulabhängigkeiten innerhalb des Java Platform Module Systems zu deklarieren.