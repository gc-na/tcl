<!--
Meta Description: # Tcl-Befehl "split": Text in Listen aufteilen ## Synopsis Der Tcl-Befehl `split` wird verwendet, um einen gegebenen String in eine Liste von Substrin...
Meta Keywords: split, der, string, tcl, text
-->

# Tcl-Befehl "split": Text in Listen aufteilen

## Synopsis
Der Tcl-Befehl `split` wird verwendet, um einen gegebenen String in eine Liste von Substrings zu unterteilen, basierend auf einem definierten Trennzeichen.

## Dokumentation
Der Befehl `split` hat die folgende Syntax:

```tcl
split string ?separator?
```

### Zweck
`split` ist nützlich, um einen langen String in kleinere Teile zu zerlegen, die dann einfacher verarbeitet oder analysiert werden können. Standardmäßig trennt `split` den String an Leerzeichen, kann aber auch an anderen Trennzeichen arbeiten, die als zweiter Parameter angegeben werden.

### Verwendung
- **string**: Der String, der aufgeteilt werden soll.
- **separator**: (optional) Das Trennzeichen, an dem der String aufgeteilt wird. Wenn kein Trennzeichen angegeben ist, verwendet `split` standardmäßig ein Leerzeichen.

### Details
- Rückgabewert: `split` gibt eine Liste zurück, die die einzelnen Teile des Strings enthält.
- Wenn der String leer ist, gibt `split` eine leere Liste zurück.
- Wenn der `separator` nicht im String enthalten ist, wird der gesamte String als ein Element in der Liste zurückgegeben.

## Beispiele
### Beispiel 1: Standardnutzung
```tcl
set text "Hallo Welt"
set result [split $text]
puts $result  ;# Ausgabe: {Hallo Welt}
```

### Beispiel 2: Benutzerdefiniertes Trennzeichen
```tcl
set text "Apfel,Banane,Kirsche"
set result [split $text ","]
puts $result  ;# Ausgabe: {Apfel Banane Kirsche}
```

### Beispiel 3: Leerer String
```tcl
set text ""
set result [split $text]
puts $result  ;# Ausgabe: {}
```

### Beispiel 4: Separator nicht gefunden
```tcl
set text "Tcl ist großartig"
set result [split $text ";"]
puts $result  ;# Ausgabe: {Tcl ist großartig}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `split` ist die Wahl des Trennzeichens. Wenn das Trennzeichen nicht im String vorhanden ist, wird der gesamte String als ein einzelnes Element in der Liste zurückgegeben. Dies kann zu unerwarteten Ergebnissen führen, wenn man annimmt, dass der String immer aufgeteilt wird.

Ein weiterer Punkt ist, dass `split` Leerzeichen als standardmäßiges Trennzeichen behandelt. Dies kann zu Verwirrung führen, wenn der Benutzer denkt, dass der String bei jedem Leerzeichen aufgeteilt wird, während in Wirklichkeit nur auf aufeinanderfolgende Leerzeichen geachtet wird.

## Ein-Satz-Zusammenfassung
Der Tcl-Befehl `split` ermöglicht die Aufteilung eines Strings in eine Liste von Substrings basierend auf einem definierten Trennzeichen.