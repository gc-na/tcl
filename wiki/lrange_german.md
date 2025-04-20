<!--
Meta Description: # lrange: Tcl-Befehl zum Abrufen von Teillisten ## Synopsis Der Tcl-Befehl `lrange` wird verwendet, um einen Teilbereich (Sublist) aus einer Liste zu ...
Meta Keywords: der, lrange, die, liste, ist
-->

# lrange: Tcl-Befehl zum Abrufen von Teillisten

## Synopsis
Der Tcl-Befehl `lrange` wird verwendet, um einen Teilbereich (Sublist) aus einer Liste zu extrahieren. Dieser Befehl ist nützlich, um bestimmte Elemente aus einer Liste zu selektieren und weiterzuverarbeiten.

## Documentation
### Zweck
`lrange` ermöglicht es, eine Teilliste aus einer gegebenen Liste zu erstellen, indem ein Start- und ein End-Index angegeben werden. Die resultierende Teilliste enthält alle Elemente von der angegebenen Startposition bis zur Endposition.

### Verwendung
Der Befehl hat die folgende Syntax:

```tcl
lrange list start end
```

- **list**: Die Quellliste, aus der die Elemente extrahiert werden.
- **start**: Der Index des ersten Elements, das in die Teilliste aufgenommen werden soll. Der Index beginnt bei 0.
- **end**: Der Index des letzten Elements, das in die Teilliste aufgenommen werden soll. Dieser Index ist inklusiv.

### Details
- Wenn der **start**-Index größer als der **end**-Index ist, gibt `lrange` eine leere Liste zurück.
- Wenn der **start**-Index kleiner als 0 ist, wird er auf 0 gesetzt. Wenn der **end**-Index größer als die Liste ist, wird er auf die maximale Listegröße gesetzt.
- `lrange` ist eine nützliche Funktion, um Listen zu segmentieren, insbesondere in Datenverarbeitungs- und Analyseanwendungen.

## Examples
### Beispiel 1: Grundlegende Verwendung
```tcl
set myList {a b c d e f g}
set subList [lrange myList 2 4]
# subList enthält jetzt {c d e}
```

### Beispiel 2: Leere Liste zurückgeben
```tcl
set myList {a b c d}
set subList [lrange myList 3 2]
# subList ist jetzt {}
```

### Beispiel 3: Negative Indizes verwenden
```tcl
set myList {a b c d e f g}
set subList [lrange myList -3 end]
# subList enthält jetzt {e f g}
```

## Explanation
Ein häufiger Fehler bei der Verwendung von `lrange` ist, dass der Benutzer vergisst, dass die Indizes nullbasiert sind. Ein weiteres häufiges Problem ist, dass die Indizes außerhalb der Grenzen der Liste liegen können, was zu unerwarteten Ergebnissen führt. Es ist wichtig, die Indizes sorgfältig zu überprüfen, um sicherzustellen, dass sie im gültigen Bereich der Liste liegen. Außerdem sollte man sich bewusst sein, dass `lrange` eine neue Liste zurückgibt und die ursprüngliche Liste unverändert bleibt.

## One Line Summary
Der Tcl-Befehl `lrange` extrahiert einen Teilbereich aus einer Liste, indem er einen Start- und End-Index angibt.