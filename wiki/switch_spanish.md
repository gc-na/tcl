<!--
Meta Description: # Comando "switch" en Tcl: Control de Flujo Eficiente ## Sinopsis El comando `switch` en Tcl permite la selección de un bloque de código a ejecutar ba...
Meta Keywords: puts, switch, tcl, patrones, que
-->

# Comando "switch" en Tcl: Control de Flujo Eficiente

## Sinopsis
El comando `switch` en Tcl permite la selección de un bloque de código a ejecutar basado en el valor de una expresión. Es una herramienta útil para manejar múltiples condiciones de forma clara y concisa, mejorando la legibilidad del código.

## Documentación
El comando `switch` evalúa una expresión y la compara con una serie de patrones. Dependiendo del patrón que coincide, ejecuta el bloque de código correspondiente. Su sintaxis básica es la siguiente:

```tcl
switch ?-exact? valor {
    patrón1 {comando1}
    patrón2 {comando2}
    ...
    default {comando_default}
}
```

### Propósito
El propósito principal de `switch` es simplificar la estructura de control de flujo en Tcl, permitiendo manejar múltiples condiciones de manera más organizada que con múltiples sentencias `if`.

### Uso
- **-exact**: Compara el valor exactamente con los patrones (por defecto, la comparación es menos estricta).
- **valor**: La expresión que se va a evaluar.
- **patrones y comandos**: Pueden ser expresiones que se evalúan y ejecutan si hay coincidencia.

### Detalles
- El primer patrón que coincide con el valor evaluado es el que determina el bloque de código a ejecutar.
- Si no hay coincidencias, se ejecuta el bloque `default` si está presente.
- Se pueden usar expresiones regulares como patrones.

## Ejemplos
### Ejemplo Básico
```tcl
set dia "Lunes"
switch $dia {
    "Lunes" {puts "Hoy es lunes."}
    "Martes" {puts "Hoy es martes."}
    "Miércoles" {puts "Hoy es miércoles."}
    default {puts "No es un día de la semana."}
}
```

### Ejemplo con -exact
```tcl
set respuesta "Sí"
switch -exact $respuesta {
    "Sí" {puts "Respuesta afirmativa."}
    "No" {puts "Respuesta negativa."}
    default {puts "Respuesta no válida."}
}
```

### Ejemplo con patrones
```tcl
set numero 5
switch -- $numero {
    1 {puts "Uno"}
    2 {puts "Dos"}
    3 {puts "Tres"}
    4 {puts "Cuatro"}
    5 {puts "Cinco"}
    default {puts "Número desconocido"}
}
```

## Explicación
Al utilizar `switch`, es importante tener en cuenta las siguientes consideraciones:

- **Orden de los patrones**: Los patrones son evaluados en el orden en que aparecen, por lo que un patrón más específico debe ir antes de uno más general.
- **Uso de `default`**: Siempre es bueno incluir un bloque `default` para manejar casos no anticipados.
- **Cuidado con los símbolos**: Si se utilizan símbolos especiales en los patrones, pueden requerir escapes o comillas para ser evaluados correctamente.
- **Comparaciones**: La opción `-exact` puede ser útil para evitar coincidencias no intencionadas.

## Resumen en una línea
El comando `switch` en Tcl permite seleccionar y ejecutar bloques de código basados en el valor de una expresión de manera eficiente y legible.