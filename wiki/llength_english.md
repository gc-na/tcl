<!--
Meta Description: # llength: Determine the Length of a Tcl List ## Synopsis The `llength` command in Tcl is used to return the number of elements in a list, providing a...
Meta Keywords: list, llength, length, tcl, lists
-->

# llength: Determine the Length of a Tcl List

## Synopsis
The `llength` command in Tcl is used to return the number of elements in a list, providing a straightforward way to determine the size of a list structure.

## Documentation
### Purpose
The primary purpose of the `llength` command is to count the number of elements contained within a Tcl list. This command is essential for list manipulation, enabling developers to verify the size of lists for iteration, validation, or conditional operations.

### Usage
The syntax for using `llength` is as follows:

```tcl
llength list
```

- `list`: This argument represents the Tcl list whose length you wish to determine. The list can be a variable containing a list or a directly specified list.

### Details
- The `llength` command evaluates the input as a list, which means that it can handle both literal lists and variables containing lists.
- If the input is an empty list, `llength` will return `0`.
- The command is highly efficient and operates in constant time, making it suitable for performance-critical applications.

## Examples
Here are some basic usage examples to illustrate the functionality of `llength`:

```tcl
# Example 1: Using llength with a simple list
set myList {apple banana cherry}
set length [llength $myList]
puts "Length of myList: $length"  ;# Output: Length of myList: 3

# Example 2: Using llength with an empty list
set emptyList {}
set emptyLength [llength $emptyList]
puts "Length of emptyList: $emptyLength"  ;# Output: Length of emptyList: 0

# Example 3: Using llength with a variable containing a list
set anotherList {one two three four five}
puts "Length of anotherList: [llength $anotherList]"  ;# Output: Length of anotherList: 5
```

## Explanation
While `llength` is straightforward, there are a few common pitfalls to be aware of:

- **Non-list input**: If you pass a non-list variable or a string that is not formatted as a list, `llength` will still return a count, but it may not be what you expect. For example, `llength "hello"` will return `1`, as the entire string is treated as a single element.
  
- **Whitespace handling**: Be cautious with whitespace in your lists. Extra spaces may lead to unexpected results. For instance, `{one two}` has a length of `2`, whereas `{one  two}` (with extra space) still counts as `2` due to Tcl’s handling of list items.

- **Nested lists**: If you have nested lists, `llength` only counts the top-level elements. For example, `llength {{a b} {c d}}` will return `2`, reflecting the two nested lists.

## One Line Summary
The `llength` command in Tcl returns the number of elements in a list, facilitating effective list manipulation and size validation.