<!--
Meta Description: # Tcl Socket 命令详解 ## 概述 Tcl 的 socket 命令用于创建网络连接，支持 TCP 和 UDP 协议。它可以用于客户端和服务器之间的通信，是构建网络应用程序的基础。 ## 文档 ### 目的 socket 命令的主要目的是在 Tcl 应用程序中创建和管理网络连接。它允许程序...
Meta Keywords: socket, server, tcl, puts, serversock
-->

# Tcl Socket 命令详解

## 概述
Tcl 的 socket 命令用于创建网络连接，支持 TCP 和 UDP 协议。它可以用于客户端和服务器之间的通信，是构建网络应用程序的基础。

## 文档
### 目的
socket 命令的主要目的是在 Tcl 应用程序中创建和管理网络连接。它允许程序通过网络进行数据传输，实现分布式计算和服务。

### 用法
基本语法如下：
```tcl
socket ?-server? ?-protocol? host port
```

#### 参数说明
- `-server`：可选参数，表示创建一个服务器 socket。
- `-protocol`：可选参数，指定使用的协议（如 TCP 或 UDP），默认为 TCP。
- `host`：目标主机的名称或 IP 地址。
- `port`：目标端口号，服务端口或客户端连接的端口。

### 详细信息
- 创建的 socket 可以用于发送和接收数据。
- 当使用 `-server` 选项创建服务器 socket 时，Tcl 将监听指定的端口，等待客户端连接。
- 服务器 socket 会返回一个新的 socket，供与客户端通信。
- socket 命令生成的对象可以使用 `puts`、`gets` 等命令进行数据交互。

## 示例
### 创建客户端 socket
```tcl
set sock [socket "localhost" 8080]
puts $sock "Hello, Server!"
gets $sock response
puts "Response from server: $response"
close $sock
```

### 创建服务器 socket
```tcl
proc server {} {
    set serverSock [socket -server myServer 8080]
    puts "Server is listening on port 8080"
    fconfigure $serverSock -blocking 0
    fileevent $serverSock readable [list acceptConnection $serverSock]
}

proc acceptConnection {serverSock} {
    set clientSock [accept $serverSock]
    puts "Client connected"
    puts $clientSock "Hello, Client!"
    close $clientSock
}

server
```

## 说明
- 使用 socket 时，确保指定的主机和端口可用，避免因连接失败而导致的错误。
- 在服务器模式下，需注意处理并发连接，可以使用 `fileevent` 机制。
- 关闭 socket 后，确保不再使用该 socket 对象，避免未定义行为。

## 一句总结
Tcl 的 socket 命令为网络编程提供了一种简单而强大的方式，支持 TCP 和 UDP 通信。