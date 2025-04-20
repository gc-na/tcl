<!--
Meta Description: # Tcl 的 subst 命令：字串替換與展開 ## 摘要 `subst` 是 Tcl 語言中的一個內建命令，用於處理字串中的變數替換和命令展開，是進行字串操作的強大工具。 ## 文檔 ### 目的 `subst` 命令的主要目的是將字串中的變數和命令進行替換。這使得在構造字串時，可以根據當前上下...
Meta Keywords: subst, set, tcl, price, puts
-->

# Tcl 的 subst 命令：字串替換與展開

## 摘要
`subst` 是 Tcl 語言中的一個內建命令，用於處理字串中的變數替換和命令展開，是進行字串操作的強大工具。

## 文檔
### 目的
`subst` 命令的主要目的是將字串中的變數和命令進行替換。這使得在構造字串時，可以根據當前上下文動態地插入值。

### 用法
`subst` 的基本語法如下：

```tcl
subst string
```

- `string`：要進行替換的字串，可以包含變數和命令。

### 詳細說明
- `subst` 會檢查字串中的所有變數和命令，並將它們展開為當前的值。
- 如果字串中沒有變數或命令，`subst` 會直接返回原始字串。
- 這個命令通常用於處理需要動態內容的情況，例如生成 SQL 語句或 HTML 內容。

## 範例
### 基本用法
```tcl
set name "Tcl"
set greeting "Hello, $name!"
set message [subst $greeting]
puts $message  ; # 輸出: Hello, Tcl!
```

### 使用命令展開
```tcl
set num 5
set commandResult "[expr {$num * 2}]"
set result [subst $commandResult]
puts $result  ; # 輸出: 10
```

### 混合字串
```tcl
set item "apple"
set price 10
set output "The price of $item is \$[subst $price]."
puts $output  ; # 輸出: The price of apple is $10.
```

## 解釋
- **常見陷阱**：使用 `subst` 時，需注意字串中的引號與轉義字符。若引號未正確處理，可能導致意外的展開結果。
- **命令展開**：`subst` 會對字串中的命令進行展開，這意味著你可以在字串中直接執行計算或函數，這可能會導致性能影響，特別是在大量字串操作時。
- **性能考量**：對於頻繁進行展開的操作，建議考慮使用 `set` 命令直接賦值，來優化性能。

## 一句總結
`subst` 是 Tcl 中用於進行字串變數替換和命令展開的關鍵命令，能夠動態生成內容。