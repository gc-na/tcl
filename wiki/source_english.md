<!--
Meta Description: # Tcl `source` Command: Load and Execute Tcl Scripts ## Synopsis The `source` command in Tcl allows users to read and execute commands from a specifie...
Meta Keywords: tcl, file, source, variables, command
-->

# Tcl `source` Command: Load and Execute Tcl Scripts

## Synopsis
The `source` command in Tcl allows users to read and execute commands from a specified file, enabling modular programming and code reuse.

## Documentation
### Purpose
The `source` command is designed to load Tcl script files into the current interpreter context. It reads the file line by line and executes its contents as if they were typed directly into the interpreter. This is particularly useful for organizing code into separate files for better maintainability and readability.

### Usage
The syntax for the `source` command is as follows:

```tcl
source filename
```

- `filename`: A string representing the path to the Tcl script file to be loaded and executed.

### Details
- The `source` command can accept both absolute and relative paths to the script file.
- If the specified file does not exist or cannot be read, Tcl will raise an error.
- It is recommended to use the full path or ensure that your script's working directory is set correctly to avoid file not found errors.
- The commands executed via `source` are evaluated in the same context as the current interpreter, meaning variables and procedures defined in the sourced file can be accessed immediately after sourcing.

## Examples
### Basic Example
Assuming there is a file named `hello.tcl` containing the following code:

```tcl
puts "Hello, World!"
```

You can source this file in your Tcl interpreter as follows:

```tcl
source hello.tcl
```

When executed, it will print:

```
Hello, World!
```

### Example with Variables
Consider a file `variables.tcl` with the following contents:

```tcl
set myVar "Hello from variables.tcl"
```

You can source this file and access the variable like this:

```tcl
source variables.tcl
puts $myVar
```

This will output:

```
Hello from variables.tcl
```

## Explanation
While using the `source` command, be aware of the following common pitfalls:

- **File Not Found**: Ensure the file path is correct. If the file does not exist or is not accessible, an error will be thrown.
- **Context Awareness**: Variables and procedures defined in the sourced file are available immediately after execution. However, if the sourced file contains conflicting variable names with existing variables, the latter will be overwritten without warning.
- **Error Handling**: Errors in the sourced file will halt the execution of subsequent commands unless managed using Tcl's error handling mechanisms (like `catch`).

## One Line Summary
The `source` command in Tcl allows for the loading and execution of external Tcl script files, facilitating code organization and reuse.