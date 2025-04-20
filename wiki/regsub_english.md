<!--
Meta Description: # regsub Command in Tcl: Regular Expression Substitution Made Easy ## Synopsis The `regsub` command in Tcl is used for substituting occurrences of a r...
Meta Keywords: string, regsub, tcl, pattern, regular
-->

# regsub Command in Tcl: Regular Expression Substitution Made Easy

## Synopsis
The `regsub` command in Tcl is used for substituting occurrences of a regular expression in a string with a specified replacement string, allowing for powerful text manipulation and data transformation.

## Documentation
### Purpose
The `regsub` command performs regular expression-based substitutions in strings. It identifies patterns in the input string that match a specified regular expression and replaces them with a given replacement string.

### Usage
The basic syntax of the `regsub` command is as follows:

```tcl
regsub ?-nocase? ?-all? ?pattern? ?replacement? ?string?
```

#### Parameters:
- `-nocase`: Optional flag that makes the pattern matching case-insensitive.
- `-all`: Optional flag that specifies that all occurrences of the pattern should be replaced; if omitted, only the first occurrence is replaced.
- `pattern`: The regular expression pattern to match against the input string.
- `replacement`: The string to replace the matched patterns with.
- `string`: The input string where the pattern matching and replacement occur.

#### Returns:
The modified string after performing the substitutions.

### Detailed Information
When using `regsub`, it's essential to note that the pattern follows the Tcl regular expression syntax, which allows for a wide variety of matching capabilities, including literals, character classes, and quantifiers. 

### Flags:
- **-nocase**: This flag allows for matching without regard to case, making it easier to perform substitutions in a case-insensitive manner.
- **-all**: By default, `regsub` only replaces the first match. Including the `-all` flag will ensure every occurrence of the pattern is replaced.

## Examples
### Example 1: Basic Substitution
```tcl
set original "Hello World"
set modified [regsub "World" "Tcl" $original]
puts $modified  ;# Output: Hello Tcl
```

### Example 2: Case-Insensitive Substitution
```tcl
set original "Hello World"
set modified [regsub -nocase "world" "Tcl" $original]
puts $modified  ;# Output: Hello Tcl
```

### Example 3: Substituting All Occurrences
```tcl
set original "abc abc abc"
set modified [regsub -all "abc" "xyz" $original]
puts $modified  ;# Output: xyz xyz xyz
```

## Explanation
When using `regsub`, users should be cautious about the following common pitfalls:
- **Regular Expression Syntax**: Ensure the pattern is correctly formatted, as incorrect syntax will lead to errors or unexpected results.
- **Replacement String**: If the replacement string contains special characters (like `\`), they must be properly escaped to avoid unintended behavior.
- **Performance**: Using the `-all` flag can impact performance if the string is large or if the pattern matches many occurrences, as each match must be processed.

## One Line Summary
The `regsub` command in Tcl enables efficient substitution of regular expression matches in strings, offering flexible text manipulation capabilities.