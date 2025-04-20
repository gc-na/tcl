<!--
Meta Description: # Tcl Socket Command: A Comprehensive Guide to Network Communication in Tcl ## Synopsis The `socket` command in Tcl provides a powerful way to create ...
Meta Keywords: socket, server, tcl, port, command
-->

# Tcl Socket Command: A Comprehensive Guide to Network Communication in Tcl

## Synopsis
The `socket` command in Tcl provides a powerful way to create network connections, enabling communication between processes over the Internet or local networks. It supports both client and server implementations, allowing developers to write networking applications efficiently.

## Documentation
The `socket` command is a fundamental feature in Tcl that allows users to create TCP or UDP sockets. Its primary purpose is to facilitate data exchange between different applications or services, whether running on the same machine or across different devices.

### Purpose
- Establish network connections.
- Send and receive data between applications.
- Implement both client-server architectures.

### Usage
The basic syntax for the `socket` command is:

```tcl
socket ?-server? port
```
- **-server**: Optional flag that indicates the socket is being created as a server.
- **port**: The port number on which the server will listen or the host/port for a client connection.

### Details
- The `socket` command can create either a TCP or UDP socket. By default, it creates a TCP socket unless specified otherwise.
- After creating a socket, you can use commands like `puts`, `gets`, and `read` to interact with the socket.
- The `close` command is used to terminate the socket connection once the communication is complete.

## Examples

### Example 1: Creating a TCP Client Socket
```tcl
set sock [socket example.com 80]
puts $sock "GET / HTTP/1.0\r\nHost: example.com\r\n\r\n"
set response [read $sock]
puts $response
close $sock
```

### Example 2: Creating a TCP Server Socket
```tcl
proc server {} {
    set sock [socket -server accept 12345]
    puts "Server is listening on port 12345"
}

proc accept {sock addr port} {
    puts "Accepted connection from $addr on port $port"
    puts $sock "Hello from server!"
    close $sock
}

server
vwait forever
```

### Example 3: Creating a UDP Socket
```tcl
set udpSock [socket -type udp 12345]
fconfigure $udpSock -buffering line
puts $udpSock "Hello from UDP socket!"
close $udpSock
```

## Explanation
While using the `socket` command in Tcl, there are several common pitfalls and considerations to keep in mind:

- **Port Availability**: Ensure that the port you intend to use is not already in use by another application.
- **Network Permissions**: On some systems, creating sockets may require elevated permissions or specific firewall rules.
- **Blocking Behavior**: By default, sockets may block until data is available. Use `fconfigure` to set non-blocking modes if necessary.
- **Error Handling**: Always include error handling for socket operations to manage unexpected disconnections or network issues gracefully.

## One Line Summary
The `socket` command in Tcl is essential for establishing TCP and UDP connections, allowing seamless network communication between applications.