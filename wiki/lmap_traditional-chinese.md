<!--
Meta Description: # lmap 指令：在 Tcl 中使用的高效列表映射功能 ## 概述 `lmap` 是 Tcl 語言中一個強大的指令，用於對列表中的每個元素進行映射操作。它允許用戶以簡潔的方式生成新的列表，並在過程中應用自定義的操作或函數。 ## 文件說明 `lmap` 指令的主要目的是對一個給定的列表進行元素級的...
Meta Keywords: lmap, tcl, set, varname, puts
-->

# lmap 指令：在 Tcl 中使用的高效列表映射功能

## 概述
`lmap` 是 Tcl 語言中一個強大的指令，用於對列表中的每個元素進行映射操作。它允許用戶以簡潔的方式生成新的列表，並在過程中應用自定義的操作或函數。

## 文件說明
`lmap` 指令的主要目的是對一個給定的列表進行元素級的操作，並生成一個新的列表。該指令的語法如下：

```tcl
lmap varName listName script
```

- `varName`：在操作過程中用來表示列表中當前元素的變數名稱。
- `listName`：需要被遍歷的列表。
- `script`：在每個元素上執行的 Tcl 腳本，可以使用 `varName` 來引用當前元素。

### 使用方法
`lmap` 提供了一種簡潔的方式來處理列表，特別是在需要生成新列表的情況下。它的運作方式是對列表中的每個元素執行所提供的腳本，並將結果收集到一個新的列表中。

## 示例
以下是一些使用 `lmap` 指令的基本示例：

### 示例 1：簡單的數字加倍
```tcl
set numbers {1 2 3 4 5}
set doubled [lmap n $numbers {expr {$n * 2}}]
puts $doubled  ; # 輸出: 2 4 6 8 10
```

### 示例 2：將字符串轉為大寫
```tcl
set strings {"hello" "world" "tcl"}
set upperStrings [lmap s $strings {string toupper $s}]
puts $upperStrings  ; # 輸出: HELLO WORLD TCL
```

### 示例 3：過濾並轉換列表
```tcl
set values {1 2 3 4 5}
set evenDoubled [lmap v $values {if {$v % 2 == 0} {expr {$v * 2}}}]
puts $evenDoubled  ; # 輸出: 4
```

## 解釋
使用 `lmap` 時需注意以下幾點：
- `lmap` 會返回一個新列表，原始列表不會被修改。
- 當腳本中包含條件語句時，確保正確使用 `if` 語句以避免返回不期望的值。
- 若列表為空，則返回的結果也將是空列表。

## 簡要總結
`lmap` 是 Tcl 中用於高效處理和生成新列表的指令，允許用戶對列表中的每個元素進行自定義操作。