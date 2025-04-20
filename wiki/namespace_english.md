<!--
Meta Description: # Understanding Tcl Namespaces: A Comprehensive Guide ## Synopsis In Tcl, a namespace is a fundamental construct that provides a mechanism for organiz...
Meta Keywords: namespace, name, tcl, namespaces, create
-->

# Understanding Tcl Namespaces: A Comprehensive Guide

## Synopsis
In Tcl, a namespace is a fundamental construct that provides a mechanism for organizing variables and procedures into distinct scopes, enabling better modularity and avoiding naming collisions.

## Documentation
### Purpose
Namespaces in Tcl serve to encapsulate and manage code, allowing developers to create isolated contexts for variables and procedures. This encapsulation helps avoid naming conflicts, especially in large applications or when integrating multiple libraries.

### Usage
The `namespace` command is used to create, delete, and manage namespaces. Here’s the basic syntax:

```tcl
namespace create ?name?
namespace delete name
namespace eval name script
namespace ensemble name
```

- **Creating a Namespace**: You can create a new namespace using `namespace create name`, where `name` is the identifier for the namespace. If `name` is omitted, it creates a namespace in the current context.

- **Deleting a Namespace**: Use `namespace delete name` to remove a namespace and all its associated variables and procedures.

- **Evaluating Commands in a Namespace**: The `namespace eval name script` command allows you to execute a script in the context of the specified namespace.

- **Creating Ensembles**: The `namespace ensemble` command is used to define a collection of commands that can be called as a single entity.

### Details
Namespaces are hierarchical and can be nested, which allows for a structured organization of code. The global namespace is the default namespace in Tcl, and all procedures and variables are accessible from there unless encapsulated within other namespaces.

To access a variable or procedure defined within a namespace, you can use the syntax `namespace::name`. This specifies that you're referring to `name` within the `namespace` context.

## Examples
### Basic Namespace Creation
```tcl
namespace create myNamespace
namespace eval myNamespace {
    proc greet {} {
        return "Hello from myNamespace!"
    }
}

puts [myNamespace::greet]  ; # Outputs: Hello from myNamespace!
```

### Deleting a Namespace
```tcl
namespace delete myNamespace
```

### Evaluating Commands in a Namespace
```tcl
namespace create math
namespace eval math {
    proc add {a b} {
        return [expr {$a + $b}]
    }
}

puts [math::add 5 10]  ; # Outputs: 15
```

### Using Ensembles
```tcl
namespace create actions
namespace ensemble create actions
namespace eval actions {
    proc run {} {
        return "Action running"
    }
    proc stop {} {
        return "Action stopped"
    }
}

puts [actions::run]  ; # Outputs: Action running
puts [actions::stop] ; # Outputs: Action stopped
```

## Explanation
When working with namespaces, it's important to remember:

- **Naming Collisions**: Namespaces help prevent naming collisions. If two procedures have the same name but exist in different namespaces, they can coexist without issue.

- **Accessing Variables and Procedures**: Always use the full namespace path (e.g., `namespace::procName`) to avoid ambiguity.

- **Deleting Namespaces**: Deleting a namespace will remove all its contents, so use this command with caution.

- **Default Namespace**: If you don’t specify a namespace, Tcl assumes you're working within the global namespace.

## One Line Summary
Tcl namespaces provide a structured way to organize variables and procedures, preventing naming conflicts and enhancing code modularity.