<!--
Meta Description: # lmap: Manipulación de Listas en Tcl ## Sinopsis El comando `lmap` en Tcl permite aplicar una operación a cada elemento de una lista, devolviendo una...
Meta Keywords: lista, una, lmap, tcl, nueva
-->

# lmap: Manipulación de Listas en Tcl

## Sinopsis
El comando `lmap` en Tcl permite aplicar una operación a cada elemento de una lista, devolviendo una nueva lista con los resultados. Es una herramienta esencial para la manipulación de listas en programación Tcl.

## Documentación
### Propósito
`lmap` se utiliza para crear una nueva lista a partir de una lista existente, aplicando una expresión sobre cada elemento. Es especialmente útil para transformar datos en estructuras de listas.

### Uso
La sintaxis básica de `lmap` es la siguiente:

```tcl
lmap variable lista {expresión}
```

- **variable**: El nombre de la variable que representa cada elemento de la lista durante la iteración.
- **lista**: La lista original que se desea mapear.
- **expresión**: Una expresión Tcl que se evalúa para cada elemento de la lista y cuyo resultado se incluye en la nueva lista.

### Detalles
- `lmap` retorna una nueva lista construida a partir de los resultados de la evaluación de la expresión para cada elemento de la lista original.
- Si la lista es vacía, `lmap` devolverá una lista vacía.
- Es importante notar que `lmap` no modifica la lista original; crea una nueva lista en su lugar.

## Ejemplos
### Ejemplo 1: Multiplicar elementos de una lista
```tcl
set lista {1 2 3 4 5}
set nuevaLista [lmap num $lista {expr {$num * 2}}]
puts $nuevaLista  ;# Salida: {2 4 6 8 10}
```

### Ejemplo 2: Convertir a mayúsculas
```tcl
set lista {"uno" "dos" "tres"}
set nuevaLista [lmap palabra $lista {string toupper $palabra}]
puts $nuevaLista  ;# Salida: {UNO DOS TRES}
```

### Ejemplo 3: Filtrar elementos
```tcl
set lista {1 2 3 4 5 6}
set nuevaLista [lmap num $lista {expr {$num % 2 == 0 ? $num : ""}}]
puts [lremove $nuevaLista ""]  ;# Salida: {2 4 6}
```

## Explicación
Al utilizar `lmap`, es fundamental tener en cuenta que la expresión debe devolver un valor adecuado para cada elemento, ya que el resultado se unirá en una nueva lista. 

Un error común es olvidar que `lmap` no altera la lista original. Si se necesita preservar la lista original y crear una nueva, `lmap` es la elección correcta.

Además, si la expresión contiene errores o no devuelve un valor, esto puede resultar en una nueva lista incompleta o inesperada. Es recomendable probar las expresiones en un entorno controlado antes de usarlas.

## Resumen en una línea
El comando `lmap` en Tcl permite transformar y crear nuevas listas aplicando una expresión a cada elemento de una lista original.