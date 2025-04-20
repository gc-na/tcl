<!--
Meta Description: # Tcl中的「return」指令：功能與用法詳解 ## 概述 在Tcl編程語言中，「return」是一個重要的指令，用於結束一個程序或過程並返回指定的值。它在函數和腳本編寫中扮演著關鍵角色，能夠控制程序的執行流。 ## 文檔 ### 目的 「return」指令的主要目的是從當前的程序、函數或過程中...
Meta Keywords: return, tcl, result, values, proc
-->

# Tcl中的「return」指令：功能與用法詳解

## 概述
在Tcl編程語言中，「return」是一個重要的指令，用於結束一個程序或過程並返回指定的值。它在函數和腳本編寫中扮演著關鍵角色，能夠控制程序的執行流。

## 文檔
### 目的
「return」指令的主要目的是從當前的程序、函數或過程中返回結果，並結束該執行上下文。這對於函數的結果處理及控制程序流程非常重要。

### 用法
```tcl
return ?value?
```

- **value**：可選的參數，表示要返回的數據。如果省略，則返回空值。

### 詳細信息
- 使用「return」指令時，該指令必須在函數或過程的上下文中使用。
- 當「return」被執行時，當前的執行環境將被終止，並將控制權返回到調用該函數或過程的上下文。
- 如果沒有指定返回值，則函數將返回空字符串。

## 示例
以下是使用「return」指令的基本示例：

### 示例 1：簡單返回值
```tcl
proc add {a b} {
    return [expr {$a + $b}]
}

set result [add 5 10]
puts $result  ;# 輸出 15
```

### 示例 2：返回空值
```tcl
proc noValue {} {
    return
}

set result [noValue]
puts $result  ;# 輸出空字符串
```

### 示例 3：多重返回值
```tcl
proc getValues {} {
    return [list 1 2 3]
}

set values [getValues]
puts "Values: $values"  ;# 輸出 Values: 1 2 3
```

## 解釋
使用「return」時需注意以下幾點：
- 確保「return」在函數或過程的正確上下文中使用，否則可能會導致錯誤。
- 如果在沒有指定返回值的情況下使用「return」，則返回空字符串，這可能會在某些情況下引起混淆。
- 在嵌套函數呼叫中，「return」將終止最內層的函數，並不會影響外層函數的執行。

## 總結
「return」指令是Tcl中的一個基本且重要的工具，用於結束函數或過程並返回結果。