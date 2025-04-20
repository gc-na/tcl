<!--
Meta Description: # Tcl `foreach` Command: A Comprehensive Guide ## Synopsis The `foreach` command in Tcl is used for iterating over lists or collections, allowing you ...
Meta Keywords: foreach, list, tcl, lists, command
-->

# Tcl `foreach` Command: A Comprehensive Guide

## Synopsis
The `foreach` command in Tcl is used for iterating over lists or collections, allowing you to execute a block of code for each element in the list. It is particularly useful for processing multiple items efficiently and succinctly.

## Documentation
The `foreach` command is designed to simplify the iteration over lists in Tcl scripts. It allows developers to execute specified commands for each item in a list or in a set of variables.

### Purpose
The primary purpose of `foreach` is to provide a straightforward way to loop through elements of a list without explicitly managing loop counters or iterators. This enhances code readability and reduces the likelihood of errors.

### Usage
The basic syntax of the `foreach` command is as follows:

```tcl
foreach varList list {
    # commands to execute for each element
}
```

- `varList`: A list of variable names. Each variable will be assigned the value of the current element in the iteration.
- `list`: The list of items to iterate over. This can also be a nested list.
- The block of code enclosed in curly braces `{}` will be executed for each item in the list.

#### Example Syntax with Nested Lists
```tcl
foreach {var1 var2} {{1 2} {3 4}} {
    # commands using $var1 and $var2
}
```

## Examples

### Basic Example
```tcl
set myList {apple banana cherry}

foreach fruit $myList {
    puts "I like $fruit"
}
```
**Output:**
```
I like apple
I like banana
I like cherry
```

### Nested Lists
```tcl
set nestedList {{1 2} {3 4} {5 6}}

foreach {x y} $nestedList {
    puts "X: $x, Y: $y"
}
```
**Output:**
```
X: 1, Y: 2
X: 3, Y: 4
X: 5, Y: 6
```

### Using a Command Inside `foreach`
```tcl
set numbers {1 2 3 4 5}
set sum 0

foreach num $numbers {
    set sum [expr {$sum + $num}]
}

puts "Total Sum: $sum"
```
**Output:**
```
Total Sum: 15
```

## Explanation
While `foreach` is a powerful and convenient looping construct, there are common pitfalls to be aware of:

- **Variable Scope**: Variables defined within the `foreach` loop are local to that loop. If you need to use those variables outside the loop, ensure you declare them outside first.
  
- **List Structure**: If the list is structured incorrectly (e.g., mismatched braces), it can lead to unexpected behavior. Always ensure your lists are well-formed.

- **Empty Lists**: If you pass an empty list to `foreach`, the block will not execute at all. This can be useful for avoiding operations on non-existent data, but it may also lead to confusion if not handled properly in your logic.

- **Variable Names**: Ensure that the variable names in `varList` do not conflict with existing variable names in the surrounding scope, unless intentional shadowing is desired.

## One Line Summary
The `foreach` command in Tcl provides a simple and efficient way to iterate over lists and execute commands for each element.