<!--
Meta Description: # lassign - Tcl-Befehl zur Zuweisung von Listenwerten ## Synopsis Der `lassign` Befehl in Tcl ermöglicht es, Werte aus einer Liste mehreren Variablen ...
Meta Keywords: variablen, der, die, lassign, liste
-->

# lassign - Tcl-Befehl zur Zuweisung von Listenwerten

## Synopsis
Der `lassign` Befehl in Tcl ermöglicht es, Werte aus einer Liste mehreren Variablen zuzuweisen, indem die Elemente der Liste direkt in die angegebenen Variablen "zugewiesen" werden.

## Dokumentation
Der `lassign` Befehl hat die folgende Syntax:

```
lassign liste ?variable ...?
```

### Zweck
`lassign` wird verwendet, um die Elemente einer Liste an mehrere Variablen zuzuweisen. Dies ist besonders nützlich, wenn man mit einer Liste von Werten arbeitet und diese in separate Variablen für eine einfachere Verarbeitung aufteilen möchte.

### Verwendung
- **liste**: Eine Tcl-Liste, deren Elemente zugewiesen werden sollen.
- **variable**: Eine oder mehrere Variablen, denen die Werte der Liste zugewiesen werden. Wenn mehr Variablen angegeben werden als Elemente in der Liste vorhanden sind, werden die nicht verwendeten Variablen auf `""` (leerer String) gesetzt.

### Details
- `lassign` gibt den Wert der letzten zugewiesenen Variablen zurück.
- Der Befehl kann auch mit einer leeren Liste aufgerufen werden, was dazu führt, dass alle angegebenen Variablen auf `""` gesetzt werden.
- Die Anzahl der zugewiesenen Variablen kann variabel sein, wobei die Anzahl der Elemente in der Liste flexibel gehandhabt wird.

## Beispiele
### Beispiel 1: Grundlegende Zuweisung
```tcl
set meineListe {1 2 3}
lassign meineListe a b c
puts "a: $a, b: $b, c: $c"  ;# Ausgabe: a: 1, b: 2, c: 3
```

### Beispiel 2: Weniger Variablen als Listenelemente
```tcl
set meineListe {10 20 30 40}
lassign meineListe x y
puts "x: $x, y: $y"  ;# Ausgabe: x: 10, y: 20
```

### Beispiel 3: Mehr Variablen als Listenelemente
```tcl
set meineListe {A B}
lassign meineListe p q r
puts "p: $p, q: $q, r: $r"  ;# Ausgabe: p: A, q: B, r: 
```

## Erklärung
Ein häufiger Fehler bei der Verwendung von `lassign` ist das Missverständnis über die Anzahl der zugewiesenen Variablen. Wenn weniger Variablen als Listenelemente angegeben sind, werden nur die ersten Elemente zugewiesen, während die übrigen Elemente ignoriert werden. Umgekehrt, wenn mehr Variablen als Elemente vorhanden sind, werden die nicht verwendeten Variablen auf einen leeren String gesetzt. 

Zusätzlich ist es wichtig, den Rückgabewert von `lassign` im Kontext zu betrachten, da er den Wert der letzten zugewiesenen Variablen zurückgibt. Dies kann in bestimmten Anwendungen nützlich sein, wo das Ergebnis der letzten Zuweisung benötigt wird.

## Einzeilige Zusammenfassung
`lassign` in Tcl ermöglicht die einfache Zuweisung von Listenwerten an mehrere Variablen.