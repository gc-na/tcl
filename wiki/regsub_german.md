<!--
Meta Description: # regsub: Reguläre Ausdrücke in Tcl für String-Manipulation ## Synopsis Der `regsub` Befehl in Tcl ermöglicht das Ersetzen von Mustern in Strings mith...
Meta Keywords: der, regsub, tcl, die, das
-->

# regsub: Reguläre Ausdrücke in Tcl für String-Manipulation

## Synopsis
Der `regsub` Befehl in Tcl ermöglicht das Ersetzen von Mustern in Strings mithilfe von regulären Ausdrücken. Diese Funktion ist essenziell für die Bearbeitung und Transformation von Textdaten.

## Documentation
### Zweck
Der `regsub` Befehl wird verwendet, um Teile eines Strings, die einem bestimmten Muster entsprechen, durch einen anderen String zu ersetzen. Dies geschieht unter Verwendung von regulären Ausdrücken, die eine leistungsstarke Methode zur Mustererkennung bieten.

### Verwendung
Die allgemeine Syntax des `regsub` Befehls lautet:

```tcl
regsub ?-options? ?pattern? ?subst? ?string? ?varName?
```

#### Parameter:
- `-options`: Zusätzliche Optionen, die das Verhalten von `regsub` steuern (z. B. `-all` für das Ersetzen aller Vorkommen).
- `pattern`: Der reguläre Ausdruck, der das zu ersetzende Muster definiert.
- `subst`: Der String, der anstelle des gefundenen Musters eingesetzt wird.
- `string`: Der Eingabestring, in dem das Muster gesucht wird.
- `varName`: Optional. Wenn angegeben, wird das Ergebnis in der angegebenen Variable gespeichert.

### Details
- Wenn die Option `-all` verwendet wird, ersetzt `regsub` alle Vorkommen des Musters im String. Andernfalls wird nur das erste Vorkommen ersetzt.
- `subst` kann Platzhalter wie `\1`, `\2` usw. enthalten, um auf die Gruppen im `pattern` zuzugreifen.

## Examples
### Beispiel 1: Einfaches Ersetzen
```tcl
set text "Hallo Welt"
set result [regsub {Welt} $text "Tcl"]
puts $result  ; # Ausgabe: Hallo Tcl
```

### Beispiel 2: Ersetzen aller Vorkommen
```tcl
set text "Tcl ist toll. Tcl macht Spaß."
set result [regsub -all {Tcl} $text "Python"]
puts $result  ; # Ausgabe: Python ist toll. Python macht Spaß.
```

### Beispiel 3: Verwendung von Gruppen
```tcl
set text "Der Preis ist 100 Euro."
set result [regsub {(\d+)} $text {\1 Dollar}]
puts $result  ; # Ausgabe: Der Preis ist 100 Dollar.
```

## Explanation
Ein häufiger Fehler bei der Verwendung von `regsub` ist das Missverständnis bezüglich der regulären Ausdrücke. Stellen Sie sicher, dass Sie die richtige Syntax und die Escape-Sequenzen verwenden. Eine weitere Falle ist das Vergessen, die Option `-all` zu setzen, wenn alle Vorkommen ersetzt werden sollen. Achten Sie auch darauf, dass die Eingabe nicht leer ist, da dies zu unerwarteten Ergebnissen führen kann.

## One Line Summary
Der `regsub` Befehl in Tcl dient zum Ersetzen von Mustern in Strings mithilfe regulärer Ausdrücke und ist ein wertvolles Werkzeug für die Textbearbeitung.