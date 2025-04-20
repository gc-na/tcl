<!--
Meta Description: # Tcl 命令：lrange - 提取列表中的子列表 ## 概述 `lrange` 是 Tcl 編程語言中的一個指令，用於從列表中提取指定範圍的元素。這個命令非常有用，在處理和操作列表時，能夠輕鬆獲得所需的子列表。 ## 文檔 ### 目的 `lrange` 用來從一個列表中返回指定範圍的元素，這...
Meta Keywords: lrange, tcl, last, set, mylist
-->

# Tcl 命令：lrange - 提取列表中的子列表

## 概述
`lrange` 是 Tcl 編程語言中的一個指令，用於從列表中提取指定範圍的元素。這個命令非常有用，在處理和操作列表時，能夠輕鬆獲得所需的子列表。

## 文檔
### 目的
`lrange` 用來從一個列表中返回指定範圍的元素，這對於需要從大列表中提取部分數據的情況特別有用。

### 語法
```tcl
lrange list first last
```

### 參數
- `list`: 要進行操作的原始列表。
- `first`: 要提取的第一個元素的索引（從0開始）。
- `last`: 要提取的最後一個元素的索引（也是從0開始）。如果 `last` 為 `end`，則會提取到列表的最後一個元素。

### 返回值
`lrange` 返回一個新列表，包含從 `first` 到 `last` 的所有元素。如果 `first` 或 `last` 超出了列表的範圍，則返回的列表將會是空的。

## 示例
### 基本用法
```tcl
set myList {a b c d e f g}
set subList [lrange $myList 1 4]
puts $subList  ;# 輸出: b c d e
```

### 使用 `end`
```tcl
set myList {1 2 3 4 5}
set subList [lrange $myList 2 end]
puts $subList  ;# 輸出: 3 4 5
```

### 空列表情況
```tcl
set myList {}
set subList [lrange $myList 0 1]
puts $subList  ;# 輸出: (空)
```

## 解釋
- **索引範圍**：索引是從0開始的，如果你提供的索引超出了列表的範圍，則返回的子列表將會是空的。
- **使用 `end`**：使用 `end` 可以方便地表示列表的最後一個元素，這在動態列表中非常有用。
- **空列表**：對於空列表，無論 `first` 和 `last` 的值是什麼，返回的子列表都是空的。

## 一句總結
`lrange` 是 Tcl 中一個強大的命令，用於從列表中提取指定範圍的元素，簡化了數據處理的過程。