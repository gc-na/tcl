<!--
Meta Description: # Tcl 的 foreach 命令：高效迴圈處理的技巧 ## 摘要 `foreach` 是 Tcl 語言中一個強大的迴圈控制命令，用於在集合內部進行迭代操作。此命令使得處理列表和數組變得簡單而直觀，廣泛應用於數據處理和腳本自動化。 ## 文件說明 ### 目的 `foreach` 命令的主要用途是...
Meta Keywords: foreach, tcl, valuelist, set, num
-->

# Tcl 的 foreach 命令：高效迴圈處理的技巧

## 摘要
`foreach` 是 Tcl 語言中一個強大的迴圈控制命令，用於在集合內部進行迭代操作。此命令使得處理列表和數組變得簡單而直觀，廣泛應用於數據處理和腳本自動化。

## 文件說明
### 目的
`foreach` 命令的主要用途是對列表或數組進行迭代，並對每個元素執行一段指定的代碼。這對於需要批量處理數據的情境非常有用，可以提高程式碼的可讀性和可維護性。

### 使用方法
`foreach` 的基本語法如下：

```tcl
foreach varList valueList body
```

- `varList`：一個或多個變數的列表，將依序與 `valueList` 中的值對應。
- `valueList`：一個列表，包含將要迭代的值。
- `body`：要執行的 Tcl 程式碼，通常是對迭代變數的處理邏輯。

### 詳細說明
`foreach` 命令可以接受多個變數，並且可以與多維列表結合使用。當使用多個變數時，每次迴圈都會同時將 `varList` 中的每個變數與 `valueList` 中的對應值綁定。

例如：
```tcl
set myList {1 2 3}
foreach num $myList {
    puts "Number: $num"
}
```

在這個例子中，`foreach` 將對 `myList` 中的每個數字進行迭代，並打印出來。

## 例子
### 基本用法
以下是一個簡單的 `foreach` 使用範例：

```tcl
set fruits {apple banana cherry}
foreach fruit $fruits {
    puts "I like $fruit"
}
```

### 多變數迴圈
```tcl
set pairs {{1 a} {2 b} {3 c}}
foreach {num letter} $pairs {
    puts "Number: $num, Letter: $letter"
}
```

### 使用索引
```tcl
set colors {red green blue}
foreach index color [array names colors] {
    puts "$index: $color"
}
```

## 解釋
### 常見問題
- **空列表**：如果 `valueList` 是空的，`foreach` 將不會執行任何循環體。
- **變數作用域**：在 `foreach` 中定義的變數在循環外部仍然可用，這可能會導致意外的行為。

### 注意事項
1. 使用 `break` 和 `continue` 來控制迴圈流，這可以使程式更具彈性。
2. 錯誤的列表格式會導致 `foreach` 不按預期工作，請確保所有列表都正確格式化。

## 一句總結
`foreach` 是 Tcl 中一個強大的迴圈工具，適合用於方便地處理和迭代列表及數組。