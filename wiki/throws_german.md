<!--
Meta Description: # throws in Java: Ausnahmebehandlung und Fehlerpropagierung ## Synopsis Das Schlüsselwort `throws` in Java dient dazu, Ausnahmen (Exceptions) zu dekla...
Meta Keywords: throws, der, die, methode, java
-->

# throws in Java: Ausnahmebehandlung und Fehlerpropagierung

## Synopsis
Das Schlüsselwort `throws` in Java dient dazu, Ausnahmen (Exceptions) zu deklarieren, die von einer Methode möglicherweise ausgelöst werden. Es ermöglicht Entwicklern, Fehlererkennung und -behandlung zu steuern, indem sie die Verantwortung für die Behandlung dieser Ausnahmen an den Aufrufer der Methode übertragen.

## Dokumentation
In Java wird das Schlüsselwort `throws` in der Methodendeklaration verwendet, um anzugeben, dass eine Methode eine oder mehrere Ausnahmen auslösen kann. Dies ist besonders nützlich bei der Arbeit mit checked Exceptions, da der Compiler sicherstellt, dass diese Ausnahmen behandelt werden, entweder durch einen try-catch-Block oder durch eine weitere throws-Deklaration in der aufrufenden Methode.

### Zweck
Der Hauptzweck von `throws` ist die Fehlerpropagierung. Durch die Verwendung von `throws` können Entwickler klar kommunizieren, welche Fehler in einer Methode auftreten können, und fördern so eine bessere Fehlerbehandlung in der gesamten Anwendung.

### Verwendung
Das Schlüsselwort `throws` wird in der Methodensignatur verwendet, gefolgt von einer oder mehreren Ausnahmen, die durch Kommas getrennt sind. Hier ein einfaches Beispiel:

```java
public void meineMethode() throws IOException, SQLException {
    // Methodenkörper
}
```

In diesem Beispiel gibt die Methode `meineMethode` an, dass sie sowohl eine `IOException` als auch eine `SQLException` auslösen kann.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von `throws` in Java:

### Beispiel 1: IOException
```java
import java.io.*;

public class DateiLesen {
    public void leseDatei(String dateiName) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader(dateiName));
        String zeile;
        while ((zeile = br.readLine()) != null) {
            System.out.println(zeile);
        }
        br.close();
    }
}
```

### Beispiel 2: SQLException
```java
import java.sql.*;

public class DatenbankZugriff {
    public void verbindeDatenbank() throws SQLException {
        Connection verbindung = DriverManager.getConnection("jdbc:mysql://localhost:3306/meineDatenbank", "benutzer", "passwort");
        // Weitere Datenbankoperationen
    }
}
```

## Erklärung
Bei der Verwendung von `throws` sollten Entwickler sich der folgenden Punkte bewusst sein:

1. **Checked vs. Unchecked Exceptions**: `throws` ist hauptsächlich für checked exceptions relevant, da der Compiler sicherstellt, dass diese behandelt werden. Unchecked exceptions (z.B. `NullPointerException`) müssen nicht deklariert werden.

2. **Mehrere Ausnahmen**: Eine Methode kann mehrere Ausnahmen deklarieren, die durch Kommas getrennt sind. Der Aufrufer muss in der Lage sein, mit jeder dieser Ausnahmen umzugehen.

3. **Methoden mit throws**: Wenn eine Methode eine Ausnahme deklariert, muss jede Methode, die diese Methode aufruft, ebenfalls die Ausnahme behandeln oder weitergeben.

4. **Fehlerbehandlung**: Es ist wichtig, geeignete Fehlerbehandlungsmechanismen zu implementieren, um unerwartete Programmabbrüche zu vermeiden.

## Zusammenfassung in einem Satz
Das Schlüsselwort `throws` in Java ermöglicht es Entwicklern, Ausnahmen zu deklarieren, die von einer Methode möglicherweise ausgelöst werden, und fördert so eine strukturierte Fehlerbehandlung.