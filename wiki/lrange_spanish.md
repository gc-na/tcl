<!--
Meta Description: # lrange: Cómo utilizar el comando de lista en Tcl ## Sinopsis El comando `lrange` en Tcl se utiliza para extraer un rango específico de elementos de ...
Meta Keywords: lista, lrange, índice, tcl, una
-->

# lrange: Cómo utilizar el comando de lista en Tcl

## Sinopsis
El comando `lrange` en Tcl se utiliza para extraer un rango específico de elementos de una lista. Este comando es fundamental para manipular y acceder a datos dentro de listas en Tcl.

## Documentación
### Propósito
El comando `lrange` permite obtener una sublista de una lista original, especificando los índices de inicio y fin. Esto es especialmente útil para trabajar con fragmentos de datos sin alterar la lista original.

### Uso
La sintaxis básica de `lrange` es la siguiente:

```tcl
lrange lista inicio fin
```

- **lista**: La lista de la cual se desea extraer el rango de elementos.
- **inicio**: El índice del primer elemento a incluir en la sublista (0 basado).
- **fin**: El índice del último elemento a incluir en la sublista.

Si el índice de fin es mayor que el número de elementos en la lista, `lrange` retornará todos los elementos hasta el final de la lista.

### Detalles
- Los índices pueden ser negativos. Un índice negativo indica una posición desde el final de la lista, donde `-1` representa el último elemento.
- Si el índice de inicio es mayor que el índice de fin, `lrange` devolverá una lista vacía.

## Ejemplos
### Ejemplo 1: Obtener un rango básico
```tcl
set mi_lista {a b c d e f g}
set sub_lista [lrange mi_lista 2 4]
puts $sub_lista  ; # Salida: c d e
```

### Ejemplo 2: Uso de índices negativos
```tcl
set mi_lista {a b c d e f g}
set sub_lista [lrange mi_lista -4 -2]
puts $sub_lista  ; # Salida: e f g
```

### Ejemplo 3: Cuando el índice de fin supera el tamaño de la lista
```tcl
set mi_lista {a b c d e}
set sub_lista [lrange mi_lista 1 10]
puts $sub_lista  ; # Salida: b c d e
```

### Ejemplo 4: Índice de inicio mayor que el índice de fin
```tcl
set mi_lista {a b c d e}
set sub_lista [lrange mi_lista 3 1]
puts $sub_lista  ; # Salida: (nada)
```

## Explicación
Al utilizar `lrange`, es importante tener en cuenta:
- Los índices son 0-basados, así que el primer elemento tiene un índice de 0.
- Si se proporcionan índices negativos, asegúrate de que el rango que intentas extraer sea válido y no salgas de los límites de la lista.
- Siempre verifica si el índice de inicio es menor o igual que el índice de fin para evitar obtener una lista vacía.

## Resumen en una línea
El comando `lrange` en Tcl permite extraer un rango de elementos de una lista, facilitando la manipulación de datos de manera eficiente.