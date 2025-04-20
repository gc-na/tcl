<!--
Meta Description: # Tcl Befehl: linsert – Einfügen von Elementen in Listen ## Synopsis Der Tcl-Befehl `linsert` wird verwendet, um ein oder mehrere Elemente an einer be...
Meta Keywords: die, liste, der, linsert, elemente
-->

# Tcl Befehl: linsert – Einfügen von Elementen in Listen

## Synopsis
Der Tcl-Befehl `linsert` wird verwendet, um ein oder mehrere Elemente an einer bestimmten Position in einer Liste einzufügen. Dieser Befehl ist besonders nützlich, wenn Sie die Struktur von Listen dynamisch ändern möchten.

## Dokumentation
Der `linsert` Befehl hat die folgende Syntax:

```tcl
linsert liste index element ?element ...?
```

### Zweck
`linsert` ermöglicht es Ihnen, Elemente in eine bestehende Liste einzufügen, ohne die bestehenden Elemente zu überschreiben. Dies ist nützlich für die Manipulation von Listen in Skripten, wo die Reihenfolge der Elemente wichtig ist.

### Verwendung
- **liste**: Die Liste, in die die Elemente eingefügt werden sollen.
- **index**: Die Position, an der die neuen Elemente eingefügt werden sollen. Der Index beginnt bei 0. 
- **element**: Die Elemente, die eingefügt werden sollen. Es können mehrere Elemente angegeben werden.

Wenn der angegebene Index größer als die Länge der Liste ist, wird das Element am Ende der Liste hinzugefügt.

### Details
- `linsert` gibt die modifizierte Liste zurück.
- Wenn `index` 0 ist, wird das Element am Anfang der Liste eingefügt.
- Ein negativer Index wird relativ zum Ende der Liste interpretiert.

## Beispiele

### Beispiel 1: Einfaches Einfügen
```tcl
set meineListe {1 2 3}
set neueListe [linsert meineListe 1 1.5]
# neueListe: {1 1.5 2 3}
```

### Beispiel 2: Mehrere Elemente einfügen
```tcl
set meineListe {a b c}
set neueListe [linsert meineListe 2 d e]
# neueListe: {a b d e c}
```

### Beispiel 3: Einfügen am Ende der Liste
```tcl
set meineListe {1 2 3}
set neueListe [linsert meineListe 5 4]
# neueListe: {1 2 3 4}
```

### Beispiel 4: Negativer Index
```tcl
set meineListe {x y z}
set neueListe [linsert meineListe -1 a]
# neueListe: {x y a z}
```

## Erklärung
- **Häufige Fallstricke**: Achten Sie darauf, dass der Index 0 ist, wenn Sie am Anfang der Liste einfügen möchten. Wenn Sie einen Index verwenden, der größer ist als die Liste, wird das Element am Ende eingefügt, was möglicherweise nicht das gewünschte Verhalten ist.
- **Typen**: Stellen Sie sicher, dass die Eingabewerte in der Liste die richtigen Datentypen haben, die Sie erwarten.
- **Änderung der Liste**: `linsert` verändert nicht die ursprüngliche Liste, sondern gibt eine neue Liste zurück.

## Ein-Satz-Zusammenfassung
Der Tcl-Befehl `linsert` ermöglicht das Einfügen von einem oder mehreren Elementen an einer bestimmten Stelle in einer Liste.