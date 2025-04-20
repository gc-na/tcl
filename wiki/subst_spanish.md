<!--
Meta Description: # Comando "subst" en Tcl: Sustitución de Cadenas ## Sinopsis El comando `subst` en Tcl se utiliza para realizar sustituciones en cadenas, permitiendo ...
Meta Keywords: subst, tcl, que, variables, texto
-->

# Comando "subst" en Tcl: Sustitución de Cadenas

## Sinopsis
El comando `subst` en Tcl se utiliza para realizar sustituciones en cadenas, permitiendo la expansión de variables y la evaluación de expresiones dentro de un texto. Es fundamental para la manipulación dinámica de cadenas en scripts Tcl.

## Documentación
El comando `subst` tiene como objetivo principal realizar la sustitución de variables y la evaluación de expresiones dentro de una cadena. Su sintaxis es la siguiente:

```tcl
subst string
```

### Propósito
El propósito de `subst` es tomar una cadena de texto y reemplazar cualquier variable o expresión en ella por su valor actual. Esto es especialmente útil cuando se necesita preparar un comando o un texto que incluirá valores dinámicos.

### Uso
- **Cadena simple**: Si se pasa una cadena sin variables ni expresiones, la función retornará la cadena tal cual.
- **Con variables**: Si la cadena incluye nombres de variables precedidos por `$`, `subst` los reemplazará por el valor de la variable correspondiente.
- **Con expresiones**: También permite la evaluación de expresiones que están encerradas en corchetes `[]`.

### Detalles
- Las variables que no están definidas se sustituyen por una cadena vacía.
- `subst` es más seguro que otros métodos de sustitución, ya que no ejecuta comandos de Tcl, solo realiza sustituciones de texto.

## Ejemplos
### Ejemplo 1: Sustitución de Variable
```tcl
set nombre "Juan"
set saludo [subst "Hola, $nombre!"]
puts $saludo  ;# Salida: Hola, Juan!
```

### Ejemplo 2: Evaluación de Expresión
```tcl
set x 5
set y 10
set resultado [subst "[expr {$x + $y}] es el resultado"]
puts $resultado  ;# Salida: 15 es el resultado
```

### Ejemplo 3: Cadena Sin Variables
```tcl
set texto [subst "Este es un texto estático."]
puts $texto  ;# Salida: Este es un texto estático.
```

## Explicación
Un error común al usar `subst` es olvidar que las variables deben estar definidas previamente. Si una variable no ha sido establecida, `subst` simplemente la reemplazará con una cadena vacía, lo que puede llevar a resultados inesperados. Además, es importante recordar que `subst` no ejecuta comandos, por lo que si se intenta usar con código Tcl que no sea una simple variable o expresión, no producirá el resultado esperado.

## Resumen en Una Línea
El comando `subst` en Tcl permite la sustitución de variables y la evaluación de expresiones dentro de cadenas, facilitando la manipulación dinámica de texto.