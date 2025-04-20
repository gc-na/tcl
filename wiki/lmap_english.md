<!--
Meta Description: # lmap Command in Tcl: Transforming Lists with Ease ## Synopsis The `lmap` command in Tcl provides a powerful way to transform lists by applying a spe...
Meta Keywords: list, lmap, tcl, command, script
-->

# lmap Command in Tcl: Transforming Lists with Ease

## Synopsis
The `lmap` command in Tcl provides a powerful way to transform lists by applying a specified script to each element of a list, returning a new list as a result.

## Documentation
### Purpose
The `lmap` command is designed to iterate over a list and apply a transformation to each element, producing a new list. This command is particularly useful for functional programming paradigms within Tcl, enabling concise and readable code when processing list data.

### Usage
The basic syntax for the `lmap` command is as follows:

```tcl
lmap varName listName script
```

- **varName**: A variable name that represents each element of the list during the iteration.
- **listName**: The list that you want to iterate over.
- **script**: The Tcl script that will be executed for each element of the list, which can utilize the `varName`.

### Details
- The `lmap` command returns a new list constructed from the results of executing the provided script on each element of the original list.
- If the original list is empty, `lmap` returns an empty list.
- The `script` can include any valid Tcl expressions and can manipulate `varName` in any way necessary.

## Examples
### Basic Example
Here’s a simple example that doubles each number in a list:

```tcl
set numbers {1 2 3 4 5}
set doubled [lmap num $numbers {expr {$num * 2}}]
puts $doubled  ;# Output: {2 4 6 8 10}
```

### Using Multiple Variables
`lmap` can also utilize multiple variables if the list contains sublists:

```tcl
set pairs {{1 2} {3 4} {5 6}}
set sums [lmap {x y} $pairs {expr {$x + $y}}]
puts $sums ;# Output: {3 7 11}
```

### Complex Transformation
You can use `lmap` for more complex transformations, such as conditional modifications:

```tcl
set values {1 2 3 4 5}
set modified [lmap val $values {
    if {$val % 2 == 0} {
        expr {$val * 10}
    } else {
        $val
    }
}]
puts $modified ;# Output: {1 20 3 40 5}
```

## Explanation
### Common Pitfalls
- **Variable Scope**: Ensure that `varName` is not already in use in the current scope, as it will overwrite existing variables.
- **Empty Lists**: If an empty list is passed to `lmap`, the output will also be an empty list. This is the expected behavior but can be overlooked when not accounted for.
- **Complex Scripts**: While `lmap` allows for complex scripts, readability may suffer if the transformations become too convoluted. Aim for clarity.

### Gotchas
- The `lmap` command will create a new list rather than modifying the original list, which is a key aspect to remember when performing transformations.
- The use of `expr` within `script` is common, but be cautious with mixed types (e.g., strings and numbers) as it may lead to unexpected results.

## One Line Summary
The `lmap` command in Tcl is a list manipulation tool that applies a given script to each element of a list, generating a new transformed list.