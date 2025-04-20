<!--
Meta Description: # lindex Command in Tcl: Accessing List Elements Efficiently ## Synopsis The `lindex` command in Tcl is used to retrieve an element from a list at a s...
Meta Keywords: lindex, list, index, tcl, element
-->

# lindex Command in Tcl: Accessing List Elements Efficiently

## Synopsis
The `lindex` command in Tcl is used to retrieve an element from a list at a specified index, allowing for efficient access to list contents.

## Documentation
The `lindex` command is a built-in function in the Tcl programming language that allows users to access elements within a list by their index. Its primary purpose is to facilitate the extraction of a single element from a list, enabling easier manipulation and access to data structures that utilize lists.

### Usage
The basic syntax for the `lindex` command is as follows:

```tcl
lindex list index
```

- **list**: This is the list from which you want to retrieve an element.
- **index**: This is the zero-based index of the element you wish to access. 

### Details
- If the specified index is negative, it counts from the end of the list (e.g., `-1` refers to the last element).
- If the index exceeds the bounds of the list, `lindex` returns an empty string.
- `lindex` can also handle nested lists, allowing for deep element access by specifying multiple indices.

## Examples

### Basic Example
```tcl
set myList {apple banana cherry}
set fruit [lindex $myList 1]
# $fruit will be "banana"
```

### Accessing the Last Element
```tcl
set myList {apple banana cherry}
set lastFruit [lindex $myList -1]
# $lastFruit will be "cherry"
```

### Nested Lists
```tcl
set nestedList {{A B C} {D E F} {G H I}}
set element [lindex [lindex $nestedList 1] 2]
# $element will be "F"
```

## Explanation
When using `lindex`, it's important to be cautious with the index values:

- **Zero-based Indexing**: Tcl lists are indexed starting from zero, which may cause confusion for those accustomed to one-based indexing in other programming languages.
- **Negative Indices**: Negative indices are a powerful feature but can be overlooked by beginners. Always ensure that the index does not go out of bounds.
- **Empty Lists**: If the list is empty, any index will return an empty string. Always check the list's length before accessing elements if there's any uncertainty.

## One Line Summary
The `lindex` command in Tcl is a versatile tool for retrieving elements from lists using zero-based or negative indexing.