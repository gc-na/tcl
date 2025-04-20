<!--
Meta Description: # Tclのregexpコマンド：正規表現による文字列操作 ## 概要 Tclの`regexp`コマンドは、正規表現を使用して文字列内のパターンマッチングを行うための強力なツールです。このコマンドを使用することで、指定したパターンに一致する部分を検索し、抽出や置換、検証を行うことができます。 ## ...
Meta Keywords: regexp, string, tcl, コマンドは, options
-->

# Tclのregexpコマンド：正規表現による文字列操作

## 概要
Tclの`regexp`コマンドは、正規表現を使用して文字列内のパターンマッチングを行うための強力なツールです。このコマンドを使用することで、指定したパターンに一致する部分を検索し、抽出や置換、検証を行うことができます。

## ドキュメンテーション
`regexp`コマンドは、与えられた正規表現パターンが文字列にマッチするかどうかを判断します。基本的な構文は以下の通りです。

```tcl
regexp ?options? pattern string ?matchVar? ?submatchVar1? ... ?submatchVarN?
```

### 引数
- `options`：オプションを指定することで、マッチの挙動を変更できます。
- `pattern`：検索する正規表現パターン。
- `string`：対象の文字列。
- `matchVar`：オプション。マッチした部分文字列を格納する変数。
- `submatchVar1` 〜 `submatchVarN`：オプション。サブマッチの結果を格納する変数。

### 戻り値
`regexp`は、パターンが文字列にマッチした場合は真（1）、そうでない場合は偽（0）を返します。また、`matchVar`が指定されている場合は、マッチした部分文字列がその変数に格納されます。

### オプション
- `-nocase`：大文字と小文字を区別しないマッチを行います。
- `-indices`：一致した部分のインデックスを返します。
- `-all`：すべての一致を取得します。

## 例
### 基本的な使用法
```tcl
set string "Hello, Tcl World!"
if {[regexp {Tcl} $string]} {
    puts "Match found!"
}
```

### サブマッチの取得
```tcl
set string "2023年10月5日"
if {[regexp {(\d{4})年(\d{1,2})月(\d{1,2})日} $string match year month day]} {
    puts "Year: $year, Month: $month, Day: $day"
}
```

### 大文字小文字を区別しないマッチ
```tcl
set string "Hello, Tcl World!"
if {[regexp -nocase {hello} $string]} {
    puts "Case insensitive match found!"
}
```

## 解説
`regexp`コマンドを使用する際の一般的な落とし穴は、正規表現パターンの構文エラーや、意図しないマッチング結果です。特に、サブマッチを使用する際には、変数のスコープに注意が必要です。また、`options`の指定を忘れると、大文字小文字を区別するマッチになり、意図した結果が得られないことがあります。

## 一言要約
Tclの`regexp`コマンドは、正規表現を用いて文字列のパターンマッチングを行うための強力な機能です。