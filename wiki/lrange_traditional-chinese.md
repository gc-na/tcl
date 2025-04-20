<!--
Meta Description: # lrange：Tcl 中的列表子範圍命令 ## 概述 `lrange` 是 Tcl 語言中用於從列表中提取指定範圍元素的命令。它是處理列表數據結構的重要工具，能夠有效地從大型列表中獲取所需的子列表。 ## 文檔 `lrange` 命令的主要目的是從一個列表中選擇一個子範圍。其基本語法如下： ``...
Meta Keywords: lrange, tcl, start, end, set
-->

# lrange：Tcl 中的列表子範圍命令

## 概述
`lrange` 是 Tcl 語言中用於從列表中提取指定範圍元素的命令。它是處理列表數據結構的重要工具，能夠有效地從大型列表中獲取所需的子列表。

## 文檔
`lrange` 命令的主要目的是從一個列表中選擇一個子範圍。其基本語法如下：

```tcl
lrange list start end
```

### 參數說明
- **list**：要操作的原始列表。
- **start**：範圍的起始索引（包含）。
- **end**：範圍的結束索引（包含）。

### 返回值
`lrange` 返回一個新列表，包含從 `start` 到 `end` 指定範圍內的所有元素。如果 `start` 或 `end` 超出了列表的範圍，則 `lrange` 會根據有效範圍自動調整。

### 注意事項
- 索引從 0 開始。
- 如果 `start` 大於 `end`，則返回空列表。
- 如果 `start` 或 `end` 為負數，則從列表尾部計算索引。

## 範例
以下是一些使用 `lrange` 的基本範例：

### 範例 1：提取簡單範圍
```tcl
set myList {a b c d e f}
set subList [lrange $myList 1 3]
puts $subList  ;# 輸出: b c d
```

### 範例 2：使用負索引
```tcl
set myList {1 2 3 4 5}
set subList [lrange $myList -3 -1]
puts $subList  ;# 輸出: 3 4 5
```

### 範例 3：範圍超出
```tcl
set myList {x y z}
set subList [lrange $myList 0 5]
puts $subList  ;# 輸出: x y z
```

## 解釋
在使用 `lrange` 時，有一些常見的陷阱需要注意：
- 確認索引範圍是否正確。若 `start` 大於 `end`，會返回空列表。
- 負索引可以方便地從列表尾部提取元素，但需理解其在不同情境下的行為。
- 檢查列表是否為空，因為對於空列表使用 `lrange` 會直接返回空列表。

## 總結
`lrange` 是 Tcl 中用於提取列表子範圍的重要命令，可以靈活地選擇和操作列表元素。