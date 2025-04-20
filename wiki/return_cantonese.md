<!--
Meta Description: # Tcl 中的 return 命令：用於函數返回值 ## 摘要 `return` 命令是 Tcl 語言中用來從函數或腳本中返回值的關鍵字，能夠有效地結束函數的執行並提供結果。 ## 文檔 ### 目的 `return` 命令的主要目的是在函數執行結束時返回一個或多個值給調用者，並可以用來控制函數的...
Meta Keywords: return, tcl, sum, set, coords
-->

# Tcl 中的 return 命令：用於函數返回值

## 摘要
`return` 命令是 Tcl 語言中用來從函數或腳本中返回值的關鍵字，能夠有效地結束函數的執行並提供結果。

## 文檔
### 目的
`return` 命令的主要目的是在函數執行結束時返回一個或多個值給調用者，並可以用來控制函數的流程。

### 用法
基本語法如下：
```tcl
return ?value1 value2 ...?
```
- `value1, value2, ...`：可選參數，表示要返回的值，可以是任意類型的 Tcl 對象。

### 詳細說明
當 `return` 被執行時，函數的執行會立即結束，並將指定的返回值傳遞給調用該函數的上下文。這個命令在錯誤處理中尤為重要，因為它可以用來早期終止函數執行並回傳錯誤狀態。

- 如果不指定返回值，則返回 `""`（空字符串）。
- 在 Tcl 中，返回值可以是數字、字符串、列表或其他任何 Tcl 對象。

## 範例
### 基本用法
以下是一個簡單的示例函數，演示如何使用 `return` 來返回值：

```tcl
proc add {a b} {
    set sum [expr {$a + $b}]
    return $sum
}

set result [add 5 10]
puts "The sum is: $result"  ;# 輸出：The sum is: 15
```

### 返回多個值
可以同時返回多個值，例如：

```tcl
proc getCoordinates {} {
    return 10 20
}

set coords [getCoordinates]
puts "X: [lindex $coords 0], Y: [lindex $coords 1]"  ;# 輸出：X: 10, Y: 20
```

## 解釋
在使用 `return` 時，開發者應注意以下幾點：
- 確保在需要結束函數時才使用 `return`，過多的使用可能會導致代碼難以理解。
- 在使用 `return` 返回多個值時，需謹慎處理返回值的接收和解析。
- 如果函數中包含錯誤處理邏輯，建議在發生錯誤時使用 `return` 結束函數並返回錯誤信息。

## 一句總結
`return` 命令在 Tcl 中用於結束函數執行並返回值，是進行函數設計時不可或缺的工具。