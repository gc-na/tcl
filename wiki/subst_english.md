<!--
Meta Description: # Tcl Command: subst - String Substitution in Tcl ## Synopsis The `subst` command in Tcl is used for string substitution, allowing variables and comma...
Meta Keywords: subst, command, string, substitution, set
-->

# Tcl Command: subst - String Substitution in Tcl

## Synopsis
The `subst` command in Tcl is used for string substitution, allowing variables and command substitutions to be processed within strings. This command is essential for dynamically constructing strings with variable values and command results.

## Documentation
### Purpose
The `subst` command evaluates its argument(s) and performs substitutions of variables and commands within the string. It is particularly useful for generating dynamic strings that incorporate variable values or the results of other commands.

### Usage
The basic syntax of the `subst` command is:
```tcl
subst string
```
Where `string` can be any string containing variables or commands to be substituted.

### Details
- **Variable Substitution**: If the string contains variables (like `$varName`), `subst` replaces those with their current values.
- **Command Substitution**: If the string contains command substitutions (like `[command]`), `subst` evaluates the command and replaces it with the result.
- **Nested Substitutions**: `subst` can handle nested substitutions, allowing multiple layers of evaluation.
- **No Escape Sequences**: Unlike some other commands, `subst` does not interpret escape sequences such as `\n` or `\t`.

## Examples
### Example 1: Basic Variable Substitution
```tcl
set name "World"
set greeting "Hello, $name!"
puts [subst $greeting]  ;# Outputs: Hello, World!
```

### Example 2: Command Substitution
```tcl
set currentDate [clock format [clock seconds]]
set message "Today's date is: [subst $currentDate]"
puts $message  ;# Outputs: Today's date is: (current date)
```

### Example 3: Nested Substitution
```tcl
set a 5
set b 10
set result "The sum of $a and $b is [expr {$a + $b}]"
puts [subst $result]  ;# Outputs: The sum of 5 and 10 is 15
```

## Explanation
### Common Pitfalls
1. **Uninitialized Variables**: If a variable used in `subst` is uninitialized, it will result in an empty string. Always ensure that variables are set before substitution.
2. **Escape Sequences Ignored**: Remember that `subst` does not evaluate escape sequences. For example, using `\n` will simply return `\n` rather than a newline.
3. **No Quoting**: If you pass a string that contains quotes, be cautious as they can alter how `subst` interprets the string.

### Additional Notes
- The `subst` command is often used in scenarios where string manipulation is necessary, such as generating dynamic error messages or user prompts.
- It is important to understand the difference between `subst` and other commands like `set` or `eval`, as they serve different purposes in string handling and evaluation.

## One Line Summary
The `subst` command in Tcl performs string substitution by replacing variables and command results within a given string.