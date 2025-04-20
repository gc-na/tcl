<!--
Meta Description: # Tcl "subst" Befehl – String-Substitution in Tcl ## Synopsis Der `subst` Befehl in Tcl ermöglicht die Auswertung und Ersetzung von Variablen und Esca...
Meta Keywords: subst, und, escape, von, sequenzen
-->

# Tcl "subst" Befehl – String-Substitution in Tcl

## Synopsis
Der `subst` Befehl in Tcl ermöglicht die Auswertung und Ersetzung von Variablen und Escape-Sequenzen innerhalb von Strings. Er ist besonders nützlich, um dynamische Inhalte zu erzeugen und Variablenwerte in Strings einzufügen.

## Dokumentation
Der `subst` Befehl hat das folgende Format:

```tcl
subst string
```

### Zweck
`subst` wird verwendet, um Variablen in einem angegebenen String zu ersetzen und Escape-Zeichen zu interpretieren. Dies ist besonders hilfreich, wenn Sie Strings mit Variablen generieren oder wenn Sie sicherstellen möchten, dass Escape-Sequenzen korrekt interpretiert werden.

### Verwendung
Der Befehl nimmt einen String als Argument und gibt den resultierenden String zurück, wobei alle Variablen durch ihre Werte ersetzt und Escape-Sequenzen interpretiert werden. 

#### Syntax:
- **`subst string`**: Ersetzt Variablen und interpretiert Escape-Sequenzen in `string`.

### Details
- **Variablenersetzung**: Alle Variablen, die im String enthalten sind, werden durch ihren aktuellen Wert ersetzt.
- **Escape-Sequenzen**: Escape-Sequenzen wie `\n` (neue Zeile) oder `\t` (Tabulator) werden in ihre entsprechenden Zeichen umgewandelt.
- **Doppelte vs. einfache Anführungszeichen**: Beachten Sie, dass `subst` in einfachen Anführungszeichen nicht arbeitet, da diese den Inhalt als Literal behandeln.

## Beispiele
### Beispiel 1: Einfache Variablenersetzung
```tcl
set name "Welt"
set greeting "Hallo, $name!"
puts [subst $greeting]
```
**Ausgabe:** `Hallo, Welt!`

### Beispiel 2: Verwendung von Escape-Sequenzen
```tcl
set text "Erste Zeile\nZweite Zeile"
puts [subst $text]
```
**Ausgabe:**
```
Erste Zeile
Zweite Zeile
```

### Beispiel 3: String mit doppelten Anführungszeichen
```tcl
set a 5
set b 10
set result "Die Summe von \$a und \$b ist [expr {$a + $b}]"
puts [subst $result]
```
**Ausgabe:** `Die Summe von 5 und 10 ist 15`

## Erklärung
Ein häufiger Stolperstein beim Einsatz von `subst` ist das Missverständnis über die Verwendung einfacher und doppelter Anführungszeichen. Bei einfachen Anführungszeichen erfolgt keine Variablenersetzung. Ein weiteres Problem kann die falsche Verwendung von Escape-Sequenzen sein. Wenn Sie sicherstellen möchten, dass Escape-Sequenzen korrekt interpretiert werden, verwenden Sie `subst` immer mit Strings in doppelten Anführungszeichen.

## Ein-Satz-Zusammenfassung
Der `subst` Befehl in Tcl ermöglicht die Ersetzung von Variablen und die Interpretation von Escape-Sequenzen innerhalb von Strings, wodurch dynamische Inhalte einfach erstellt werden können.