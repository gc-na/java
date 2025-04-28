<!--
Meta Description: # Non-Sealed in Java: Eine klare Definition und Anwendung ## Synopsis Das Schlüsselwort "non-sealed" in Java ermöglicht es Entwicklern, die Vererbungs...
Meta Keywords: sealed, die, non, von, klassen
-->

# Non-Sealed in Java: Eine klare Definition und Anwendung

## Synopsis
Das Schlüsselwort "non-sealed" in Java ermöglicht es Entwicklern, die Vererbungseinschränkungen für eine Klasse, die als "sealed" deklariert wurde, aufzuheben und somit Unterklassen zuzulassen, die nicht weiter eingeschränkt sind.

## Dokumentation
### Zweck
Das "non-sealed" Schlüsselwort wurde in Java 17 eingeführt, um die Flexibilität bei der Verwendung von "sealed" Klassen zu erhöhen. "Sealed" Klassen erlauben es Entwicklern, genau zu steuern, welche Klassen von ihnen abgeleitet werden können. Mit "non-sealed" können abgeleitete Klassen jedoch ohne weitere Einschränkungen erstellt werden.

### Verwendung
Um eine Klasse als "non-sealed" zu deklarieren, muss sie von einer "sealed" Klasse abgeleitet sein. Hier ist die grundsätzliche Syntax:

```java
sealed class Tier permits Hund, Katze {
    // ...
}

non-sealed class Hund extends Tier {
    // ...
}

non-sealed class Katze extends Tier {
    // ...
}
```

In diesem Beispiel ist die Klasse `Tier` eine "sealed" Klasse, die nur die Klassen `Hund` und `Katze` als Unterklassen zulässt. Durch die Verwendung von `non-sealed` können `Hund` und `Katze` beliebig viele Unterklassen haben.

### Details
- **Einführung**: "non-sealed" wurde als Teil des Ziels eingeführt, die Kontrolle über die Vererbung in Java zu verbessern.
- **Zugänglichkeit**: Nur Klassen, die von einer "sealed" Klasse abgeleitet sind, können als "non-sealed" deklariert werden.
- **Verwendung**: Das Schlüsselwort wird in der gleichen Syntax wie andere Modifizierer wie `public` oder `private` verwendet.

## Beispiele
Hier sind einige einfache Beispiele, die die Verwendung von "non-sealed" verdeutlichen:

### Beispiel 1: Grundlegende Verwendung
```java
sealed class Fahrzeug permits Auto, Motorrad {
    // ...
}

non-sealed class Auto extends Fahrzeug {
    // ...
}

non-sealed class Motorrad extends Fahrzeug {
    // ...
}

class Sportwagen extends Auto {
    // ...
}

class Cruiser extends Motorrad {
    // ...
}
```

In diesem Beispiel können `Sportwagen` und `Cruiser` von den nicht versiegelten Klassen `Auto` und `Motorrad` abgeleitet werden.

### Beispiel 2: Erlaubte Vererbung
```java
sealed class Form permits Kreis, Quadrat {
    // ...
}

non-sealed class Kreis extends Form {
    // ...
}

class SpezialKreis extends Kreis {
    // ...
}
```

Hier kann `SpezialKreis` von `Kreis` abgeleitet werden, da `Kreis` als "non-sealed" deklariert ist.

## Erklärung
Ein häufiges Missverständnis beim Arbeiten mit "non-sealed" Klassen ist, dass die Verwendung von "non-sealed" die Kontrolle über die Vererbung aufhebt. Es ist wichtig zu beachten, dass "non-sealed" Klassen immer noch von "sealed" Klassen abgeleitet werden müssen, und dass die ursprüngliche "sealed" Klasse die Kontrolle darüber behält, welche Klassen direkt von ihr abgeleitet werden können.

Ein weiterer Punkt ist die Komplexität der Hierarchien. Wenn viele "non-sealed" Klassen erstellt werden, kann die Struktur unübersichtlich werden. Es ist ratsam, die Vererbung hierarchisch zu planen, um die Lesbarkeit und Wartbarkeit des Codes zu gewährleisten.

## Ein Satz Zusammenfassung
Das "non-sealed" Schlüsselwort in Java ermöglicht es, Unterklassen von einer "sealed" Klasse zu erstellen, ohne weitere Vererbungseinschränkungen.