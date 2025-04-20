<!--
Meta Description: # Tcl `info` Command: Comprehensive Guide and Usage Examples ## Synopsis The `info` command in Tcl provides a variety of useful information about the ...
Meta Keywords: info, tcl, command, commands, level
-->

# Tcl `info` Command: Comprehensive Guide and Usage Examples

## Synopsis
The `info` command in Tcl provides a variety of useful information about the Tcl interpreter, its state, and the current environment, enabling developers to query details regarding commands, variables, and more.

## Documentation
The `info` command is a built-in Tcl command that serves multiple purposes. Its syntax is straightforward, allowing users to retrieve information about various aspects of their Tcl environment. 

### Purpose
The primary purpose of the `info` command is to allow users to obtain insights into the Tcl interpreter's state, including details about available commands, variables, and their associated properties.

### Usage
The general syntax for the `info` command is as follows:

```tcl
info option ?arg arg ...?
```

### Options
The `info` command supports several options, each serving a unique function:

- **level**: Returns information about the call stack.
  - `info level ?level?`: Provides the name of the command at a specified level in the call stack. If no level is specified, it defaults to the current level.

- **vars**: Lists all global variables.
  - `info vars ?pattern?`: Returns a list of variable names, optionally filtered by a pattern.

- **commands**: Lists all available commands.
  - `info commands ?pattern?`: Returns a list of command names, optionally filtered by a pattern.

- **exists**: Checks if a variable or command exists.
  - `info exists name`: Returns `1` if the variable or command with the specified name exists, `0` otherwise.

- **tclversion**: Returns the version of the Tcl interpreter in use.
  - `info tclversion`: Returns the current Tcl version as a string.

- **interp**: Provides information about the interpreter.
  - `info interp`: Returns details regarding the current interpreter.

### Additional Options
Other options include `patchlevel`, which returns the patch level of the Tcl interpreter, and `complete`, which checks if a command is complete.

## Examples
Here are some basic usage examples of the `info` command:

1. **Querying the Tcl version**:
   ```tcl
   puts "Current Tcl version: [info tclversion]"
   ```

2. **Listing all global variables**:
   ```tcl
   set myVar "Hello, Tcl!"
   puts "Global variables: [info vars]"
   ```

3. **Checking if a variable exists**:
   ```tcl
   if {[info exists myVar]} {
       puts "Variable myVar exists."
   } else {
       puts "Variable myVar does not exist."
   }
   ```

4. **Listing available commands**:
   ```tcl
   puts "Available commands: [info commands]"
   ```

5. **Getting the command at a specific level in the call stack**:
   ```tcl
   proc myProc {} {
       puts "Command at level 1: [info level 1]"
   }
   myProc
   ```

## Explanation
While the `info` command is straightforward to use, there are common pitfalls that developers should be aware of:

- **Scope Awareness**: When using `info vars`, it's important to note that it only lists global variables unless specified otherwise. Local variables will not be included unless the context of the command is correctly set.
  
- **Pattern Matching**: When using the `pattern` option with `info commands` or `info vars`, ensure that the pattern is correctly formatted to avoid missing out on relevant commands or variables.

- **Interpreting Output**: The output of `info` commands can vary significantly depending on the state of the interpreter and the context in which they are invoked. Always consider the current context when interpreting results.

## One Line Summary
The `info` command in Tcl retrieves vital information about the interpreter, commands, and variables, aiding in better debugging and understanding of the Tcl environment.