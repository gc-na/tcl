<!--
Meta Description: # Tcl Socket 指令：建立網路連線的基礎 ## 概述 在 Tcl 程式語言中，`socket` 指令用於創建網路連線，允許程式與其他計算機進行通信。這個指令是實現客戶端和伺服器系統的關鍵組件。 ## 文檔 `socket` 指令的主要目的是建立 TCP 或 UDP 連線。使用此指令可以讓 ...
Meta Keywords: socket, tcl, set, sock, fconfigure
-->

# Tcl Socket 指令：建立網路連線的基礎

## 概述
在 Tcl 程式語言中，`socket` 指令用於創建網路連線，允許程式與其他計算機進行通信。這個指令是實現客戶端和伺服器系統的關鍵組件。

## 文檔
`socket` 指令的主要目的是建立 TCP 或 UDP 連線。使用此指令可以讓 Tcl 程式開啟一個新的 socket 並與指定的主機及埠進行連線。

### 語法
```tcl
set sock [socket hostname port]
```

### 參數
- `hostname`：目標主機的名稱或 IP 地址。
- `port`：目標主機上的埠號。

### 返回值
`socket` 指令返回一個 socket 的標識符，該標識符可用於後續的讀寫操作。

### 使用方式
1. **創建客戶端 socket**：使用 `socket` 指令連接到伺服器。
2. **創建伺服器 socket**：使用 `socket` 指令並結合 `fconfigure` 設定相關的選項，以便接收連線請求。

## 範例
以下是使用 `socket` 指令的基本範例：

### 客戶端範例
```tcl
set sock [socket "localhost" 12345]
puts $sock "Hello, Server!"
close $sock
```

### 伺服器範例
```tcl
set serverSock [socket "localhost" 12345]
fconfigure $serverSock -blocking 0 -buffering line
while {1} {
    set clientSock [accept $serverSock]
    puts $clientSock "Hello, Client!"
    close $clientSock
}
```

## 解釋
在使用 `socket` 指令時，開發者需要注意以下幾點：
- 確保目標主機和埠號是正確的，否則連線將失敗。
- 在伺服器模式下，使用 `fconfigure` 可以設定 socket 的行為，例如阻塞模式和緩衝區設定。
- 當 socket 使用完成後，務必關閉它以釋放系統資源。

## 一句總結
`socket` 指令在 Tcl 中用於創建網路連線，讓應用程序能夠與其他計算機通信。