<!--
Meta Description: # Tcl regexp: A Comprehensive Guide to Regular Expressions in Tcl ## Synopsis The `regexp` command in Tcl is a powerful tool for matching and manipula...
Meta Keywords: match, regexp, tcl, regular, string
-->

# Tcl regexp: A Comprehensive Guide to Regular Expressions in Tcl

## Synopsis
The `regexp` command in Tcl is a powerful tool for matching and manipulating strings using regular expressions, allowing developers to search for patterns, validate input, and extract information efficiently.

## Documentation
### Purpose
The `regexp` command enables pattern matching within strings using regular expressions. It supports complex search patterns, providing a flexible way to validate and extract data from strings.

### Usage
The basic syntax of the `regexp` command is as follows:

```tcl
regexp ?options? exp string ?matchVar? ?subMatchVar...?
```

- **options**: Optional flags to modify the behavior of the match (e.g., `-nocase`, `-line`, `-indices`).
- **exp**: The regular expression pattern to match against the string.
- **string**: The input string to be searched.
- **matchVar**: (optional) A variable to store the entire match.
- **subMatchVar**: (optional) Variables to store submatches defined by parentheses in the regular expression.

### Details
The `regexp` command returns 1 if the pattern matches the string, and 0 otherwise. When a match is found, if `matchVar` is provided, it will contain the matched substring. Any subpatterns captured using parentheses will be stored in the corresponding `subMatchVar`.

#### Options
- `-nocase`: Perform a case-insensitive match.
- `-line`: Treat the string as multiple lines, affecting the behavior of `^` and `$`.
- `-indices`: Return the start and end indices of the match and submatches.

## Examples
### Basic Match
```tcl
set str "Hello, World!"
if {[regexp {Hello} $str]} {
    puts "Match found!"
}
```

### Case-Insensitive Match
```tcl
set str "hello, world!"
if {[regexp -nocase {HELLO} $str]} {
    puts "Match found (case insensitive)!"
}
```

### Capturing Submatches
```tcl
set str "abc123def"
if {[regexp {(\w+)(\d+)(\w+)} $str matchVar sub1 sub2 sub3]} {
    puts "Full match: $matchVar"
    puts "Letters before numbers: $sub1"
    puts "Numbers: $sub2"
    puts "Letters after numbers: $sub3"
}
```

### Using Options
```tcl
set multilineStr "First line\nSecond line"
if {[regexp -line {^Second} $multilineStr]} {
    puts "Match found on a new line!"
}
```

## Explanation
While `regexp` is a versatile command, there are some common pitfalls to be aware of:
- **Greedy vs. Non-Greedy**: By default, patterns match greedily. Use `*?` or `+?` for non-greedy matches.
- **Escaping Characters**: Special characters (like `.` or `*`) may need to be escaped with a backslash (`\`) when used literally.
- **Performance**: Complex regular expressions can lead to performance issues. Optimize patterns and avoid excessive backtracking.

## One Line Summary
The `regexp` command in Tcl is a robust facility for pattern matching and string manipulation using regular expressions, enabling efficient data validation and extraction.