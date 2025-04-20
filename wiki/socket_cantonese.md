<!--
Meta Description: # Tcl Socket 命令：網絡編程的基石 ## 簡介 Tcl 的 `socket` 命令是一個強大的工具，用於在網絡編程中建立和管理 TCP/IP 連接。無論是客戶端還是伺服器，`socket` 都能幫助開發者輕鬆處理網絡通訊。 ## 文檔 `socket` 命令的主要目的是創建一個新的 so...
Meta Keywords: socket, server, tcl, sock, port
-->

# Tcl Socket 命令：網絡編程的基石

## 簡介
Tcl 的 `socket` 命令是一個強大的工具，用於在網絡編程中建立和管理 TCP/IP 連接。無論是客戶端還是伺服器，`socket` 都能幫助開發者輕鬆處理網絡通訊。

## 文檔
`socket` 命令的主要目的是創建一個新的 socket（套接字），這是進行網絡通信的基本單位。使用此命令，開發者可以輕鬆地建立客戶端連接或啟動伺服器來接收連接。

### 語法
```tcl
socket ?-server? port
socket host port
```

### 參數
- `-server`：這是一個可選參數，當指定時，將會創建一個伺服器 socket，並監聽指定的端口。
- `port`：指定要使用的端口號。
- `host`：要連接的主機名稱或 IP 地址。

### 返回值
成功時，`socket` 返回一個套接字的文件描述符，失敗則會拋出錯誤。

## 示例
### 創建客戶端 socket
```tcl
set sock [socket "localhost" 8080]
puts $sock "Hello, Server!"
flush $sock
```

### 創建伺服器 socket
```tcl
proc acceptClient {sock} {
    set client [accept $sock]
    puts $client "Welcome to the server!"
    close $client
}

set serverSock [socket -server 8080]
puts "Server is running on port 8080"
while {1} {
    acceptClient $serverSock
}
```

## 解釋
使用 `socket` 命令時，開發者需要注意以下幾點：
- 確保指定的端口未被其他應用占用，否則會發生錯誤。
- 在伺服器端，使用 `-server` 參數時，應提前設置好接收邏輯，包括如何處理傳入的客戶端連接。
- 在客戶端，確保目標主機是可連接的，並且服務正在運行。

## 一句總結
Tcl 的 `socket` 命令是進行網絡編程的基礎，能夠輕鬆建立 TCP/IP 連接，適用於各類網絡應用。