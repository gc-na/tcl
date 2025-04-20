<!--
Meta Description: # lmap: Ein leistungsstarker Befehl zur Listenmanipulation in Tcl ## Synopsis Der Befehl `lmap` in Tcl ermöglicht es, eine Liste zu durchlaufen und da...
Meta Keywords: liste, die, lmap, der, ist
-->

# lmap: Ein leistungsstarker Befehl zur Listenmanipulation in Tcl

## Synopsis
Der Befehl `lmap` in Tcl ermöglicht es, eine Liste zu durchlaufen und dabei eine Transformation auf die Elemente anzuwenden, wobei eine neue Liste erzeugt wird. Dies ist besonders nützlich, um Listen effizient zu verarbeiten und zu transformieren.

## Dokumentation
### Zweck
`lmap` ist ein Befehl in Tcl, der genutzt wird, um eine Liste von Elementen zu iterieren und eine Funktion oder ein Skript auf jedes Element anzuwenden. Das Ergebnis dieser Anwendung wird in einer neuen Liste gespeichert.

### Verwendung
Die Grundsyntax von `lmap` lautet:

```tcl
lmap variable liste {script}
```

- `variable`: Der Name der Variablen, die das aktuelle Element während der Iteration speichert.
- `liste`: Die Liste, die durchlaufen werden soll.
- `script`: Der Tcl-Code, der auf jedes Element der Liste angewendet wird. Dieser Code kann eine Rückgabe haben, die das transformierte Element darstellt.

### Details
- `lmap` ist besonders nützlich in Kombination mit anderen Befehlen, die Listen verarbeiten, wie `set`, `puts`, oder `foreach`.
- Es ist wichtig zu beachten, dass `lmap` eine neue Liste zurückgibt, die das Ergebnis der Transformation enthält. Die ursprüngliche Liste bleibt unverändert.

## Beispiele
### Einfaches Beispiel
Hier ist ein einfaches Beispiel, das zeigt, wie `lmap` verwendet wird, um alle Elemente einer Liste zu quadrieren:

```tcl
set zahlen {1 2 3 4 5}
set quadrierteZahlen [lmap zahl $zahlen {expr {$zahl * $zahl}}]
puts $quadrierteZahlen  ; # Ausgabe: {1 4 9 16 25}
```

### Beispiel mit einer Bedingung
In diesem Beispiel verwenden wir `lmap`, um nur die geraden Zahlen aus einer Liste zu extrahieren:

```tcl
set zahlen {1 2 3 4 5 6 7 8 9 10}
set geradeZahlen [lmap zahl $zahlen {if {$zahl % 2 == 0} {set zahl}}]
puts $geradeZahlen  ; # Ausgabe: {2 4 6 8 10}
```

## Erklärung
Ein häufiger Stolperstein ist die Verwendung von `lmap`, wenn die Rückgabe des Skripts nicht korrekt behandelt wird. Es ist wichtig sicherzustellen, dass der `script`-Block tatsächlich einen Wert zurückgibt, der in die neue Liste aufgenommen werden soll. Andernfalls könnte die resultierende Liste leer oder unvollständig sein.

Ein weiterer Punkt zu beachten ist, dass `lmap` in einer Schleife verwendet werden kann, um komplexere Listenoperationen durchzuführen, jedoch kann dies die Lesbarkeit des Codes beeinträchtigen, wenn es übermäßig kompliziert wird.

## Zusammenfassung in einem Satz
`lmap` ist ein leistungsfähiger Tcl-Befehl zur Transformation von Listen, der eine neue Liste basierend auf der Anwendung eines Skripts auf jedes Element erstellt.