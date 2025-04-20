<!--
Meta Description: # Tcl 中的 lsort 命令：排序列表的最佳工具 ## 概述 `lsort` 是 Tcl 编程语言中的一个内置命令，用于对列表进行排序。它提供了多种排序选项，适用于不同的数据类型和需求。 ## 文档 `lsort` 命令的主要目的是对给定的列表进行排序，并返回一个新的排序后列表。该命令支持多种...
Meta Keywords: lsort, tcl, set, mylist, sortedlist
-->

# Tcl 中的 lsort 命令：排序列表的最佳工具

## 概述
`lsort` 是 Tcl 编程语言中的一个内置命令，用于对列表进行排序。它提供了多种排序选项，适用于不同的数据类型和需求。

## 文档
`lsort` 命令的主要目的是对给定的列表进行排序，并返回一个新的排序后列表。该命令支持多种排序方式，包括升序和降序，以及自定义比较规则。

### 用法
```tcl
lsort ?options? list
```

### 参数说明
- `options`：可选参数，指定排序方式和其他选项。
  - `-unique`：只返回唯一的元素。
  - `-increasing`：按升序排序（默认）。
  - `-decreasing`：按降序排序。
  - `-index index`：根据列表中每个元素的特定索引排序。
  - `-command script`：自定义排序的比较命令。
- `list`：要排序的列表。

### 返回值
`lsort` 返回一个新的排序后的列表。

## 示例
以下是 `lsort` 的基本使用示例：

### 示例 1：升序排序
```tcl
set myList {3 1 4 1 5 9 2}
set sortedList [lsort $myList]
puts $sortedList  ;# 输出：1 1 2 3 4 5 9
```

### 示例 2：降序排序
```tcl
set myList {3 1 4 1 5 9 2}
set sortedList [lsort -decreasing $myList]
puts $sortedList  ;# 输出：9 5 4 3 2 1 1
```

### 示例 3：返回唯一元素
```tcl
set myList {3 1 4 1 5 9 2 5}
set uniqueList [lsort -unique $myList]
puts $uniqueList  ;# 输出：1 2 3 4 5 9
```

### 示例 4：自定义排序
```tcl
set myList {apple banana Cherry date}
set sortedList [lsort -command {expr {[string compare [lindex $a 0] [lindex $b 0]]}} $myList]
puts $sortedList  ;# 输出：apple banana Cherry date
```

## 解释
使用 `lsort` 时，需要注意以下几点：
- 确保列表元素的类型一致，以避免比较错误。
- 自定义排序时，比较命令的返回值必须为负数、零或正数，分别表示第一个元素小于、等于或大于第二个元素。
- 使用 `-unique` 选项时，返回的列表中不会包含重复的元素。

## 一句话总结
`lsort` 是 Tcl 中用于对列表进行排序的强大命令，支持多种排序选项和自定义比较功能。