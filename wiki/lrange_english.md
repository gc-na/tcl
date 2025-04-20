<!--
Meta Description: # lrange: Extracting Subsets from Lists in Tcl ## Synopsis The `lrange` command in Tcl is used to retrieve a subset of elements from a list, defined b...
Meta Keywords: list, lrange, tcl, indices, command
-->

# lrange: Extracting Subsets from Lists in Tcl

## Synopsis
The `lrange` command in Tcl is used to retrieve a subset of elements from a list, defined by a specified range of indices.

## Documentation
The `lrange` command is part of the Tcl list commands that facilitate list manipulation. It allows users to extract a specific segment of a list, making it versatile for various programming scenarios where only a portion of the data is needed.

### Purpose
The main purpose of `lrange` is to enable developers to access a subset of elements from a given list without modifying the original list. This command is especially useful in scenarios where data needs to be processed in smaller chunks or when only specific elements are required.

### Usage
The basic syntax of the `lrange` command is:

```tcl
lrange list first last
```

- `list`: The list from which elements are to be extracted.
- `first`: The starting index of the range (inclusive).
- `last`: The ending index of the range (inclusive).

### Details
- **Indices**: Tcl lists are zero-indexed, meaning the first element of the list is at index 0. If `first` is greater than `last`, `lrange` will return an empty list.
- **Negative Indices**: You can use negative indices with `lrange`, where `-1` refers to the last element, `-2` refers to the second last, and so forth.
- **Out of Bounds**: If the specified range exceeds the bounds of the list, Tcl will simply return elements within the valid indices.

## Examples
Here are a few basic usage examples of the `lrange` command:

### Example 1: Basic List Range
```tcl
set myList {a b c d e f g}
set subList [lrange $myList 2 4]
# subList now contains {c d e}
```

### Example 2: Using Negative Indices
```tcl
set myList {1 2 3 4 5 6}
set subList [lrange $myList -3 -1]
# subList now contains {4 5 6}
```

### Example 3: Empty List Return
```tcl
set myList {x y z}
set subList [lrange $myList 3 5]
# subList now contains {}
```

## Explanation
When using `lrange`, there are a few common pitfalls and notes to consider:

- **Inclusive Indices**: Remember that both the `first` and `last` indices are inclusive. If you want a specific count of elements, adjust the `last` index accordingly.
- **Empty Lists**: If the list is empty or if the indices point outside the list's bounds, the command will return an empty list, which is important to handle in your code to prevent unexpected behavior.
- **Performance**: For very large lists, consider the performance implications of creating sublists, as they may consume additional memory.

## One Line Summary
The `lrange` command in Tcl extracts a specified range of elements from a list, offering a simple way to access sublists efficiently.