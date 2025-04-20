<!--
Meta Description: # Tcl 中的 source 命令：加載和執行 Tcl 腳本 ## 摘要 `source` 命令用於在 Tcl 中加載和執行外部 Tcl 腳本文件，允許開發者將代碼分割成多個文件以提高可維護性和重用性。 ## 文檔 ### 目的 `source` 命令的主要目的是將指定的 Tcl 腳本文件內容加載...
Meta Keywords: tcl, source, example, filename, hello
-->

# Tcl 中的 source 命令：加載和執行 Tcl 腳本

## 摘要
`source` 命令用於在 Tcl 中加載和執行外部 Tcl 腳本文件，允許開發者將代碼分割成多個文件以提高可維護性和重用性。

## 文檔
### 目的
`source` 命令的主要目的是將指定的 Tcl 腳本文件內容加載到當前的 Tcl 解釋器中並執行，這對於模組化代碼及維護大型應用程序非常有用。

### 用法
```tcl
source filename
```
- `filename`：要加載的 Tcl 腳本文件的路徑。可以是相對路徑或絕對路徑。

### 詳細信息
- 當 `source` 命令被調用時，Tcl 解釋器會將指定文件的內容讀入並立即執行。
- 如果文件不存在或無法讀取，`source` 命令會引發錯誤。
- `source` 可以加載任意數量的 Tcl 腳本，使得代碼結構更加清晰和組織化。

## 示例
### 基本用法
假設有一個名為 `example.tcl` 的文件：
```tcl
# example.tcl
puts "Hello, World!"
```
你可以通過以下命令來加載和執行此文件：
```tcl
source example.tcl
```
執行後，將輸出：
```
Hello, World!
```

### 加載多個腳本
你可以在主腳本中依次加載多個腳本：
```tcl
source script1.tcl
source script2.tcl
```

## 解釋
- **常見陷阱**：在使用 `source` 命令時，確保文件路徑正確，否則會引發錯誤。
- **作用域問題**：被加載的腳本中的變量和命令會在當前的命名空間中可用，這可能會影響主腳本的執行。要小心變量命名衝突。
- **錯誤處理**：如果 `source` 命令因為文件錯誤而失敗，會拋出錯誤信息，建議使用 `catch` 命令來捕獲錯誤。

## 一句總結
`source` 命令在 Tcl 中用於加載和執行外部腳本，促進代碼的模組化和重用。