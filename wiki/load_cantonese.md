<!--
Meta Description: # Tcl 的 load 命令詳解 ## 簡介 `load` 是 Tcl 語言中一個重要的命令，用於將共享庫（shared library）加載到 Tcl 解釋器中，從而使得庫中的功能可以在 Tcl 腳本中被調用。 ## 文檔 ### 目的 `load` 命令的主要目的是將外部的 C 語言編寫的共享...
Meta Keywords: tcl, load, mylib, library, 解釋器中
-->

# Tcl 的 load 命令詳解

## 簡介
`load` 是 Tcl 語言中一個重要的命令，用於將共享庫（shared library）加載到 Tcl 解釋器中，從而使得庫中的功能可以在 Tcl 腳本中被調用。

## 文檔
### 目的
`load` 命令的主要目的是將外部的 C 語言編寫的共享庫加載到 Tcl 環境中，這樣可以擴展 Tcl 的功能，使其能夠利用用戶自定義的 C 函數或其他編程語言編寫的函數。

### 使用方法
`load` 命令的基本語法如下：
```tcl
load <library> ?<symbol>?
```
- `<library>`: 必需的參數，指定要加載的共享庫的完整路徑或相對路徑。
- `<symbol>`: 可選的參數，指定一個符號，通常是共享庫中的一個函數名稱。

### 詳細說明
- 如果成功，`load` 命令會返回一個空字符串。
- 如果指定的庫已經加載過，`load` 不會重新加載它。
- 加載庫的過程中，如果發生錯誤，會拋出異常。
- 當庫加載成功後，相關的命令和函數可以在 Tcl 腳本中直接調用。

## 示例
### 基本用法
```tcl
# 加載名為 mylib.so 的共享庫
load ./mylib.so

# 調用共享庫中的函数
set result [mylib_function arg1 arg2]
```

### 確認庫是否加載
```tcl
# 加載庫
load ./mylib.so

# 檢查是否加載成功
if {[info sharedlib mylib.so] == ""} {
    puts "成功加載 mylib.so"
} else {
    puts "mylib.so 已經加載"
}
```

## 解釋
- **常見陷阱**: 確保共享庫的路徑正確且有適當的讀取權限，否則將會報錯。
- **符號錯誤**: 如果指定符號不存在，則會導致加載失敗。
- **平台依賴性**: 共享庫的格式在不同操作系統之間可能不同（如 `.so` 在 Linux 和 `.dll` 在 Windows），需注意使用正確的格式。

## 一句總結
`load` 命令用於將外部共享庫加載到 Tcl 解釋器中，擴展 Tcl 的功能。