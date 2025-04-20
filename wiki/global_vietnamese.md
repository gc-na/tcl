<!--
Meta Description: # Từ Khóa: Lệnh "global" trong Tcl: Cách sử dụng và ví dụ ## Tóm tắt Lệnh `global` trong Tcl cho phép truy cập và điều chỉnh các biến toàn cục từ bên ...
Meta Keywords: biến, toàn, cục, trong, global
-->

# Từ Khóa: Lệnh "global" trong Tcl: Cách sử dụng và ví dụ

## Tóm tắt
Lệnh `global` trong Tcl cho phép truy cập và điều chỉnh các biến toàn cục từ bên trong các thủ tục, giúp duy trì trạng thái trong toàn bộ chương trình.

## Tài liệu
Lệnh `global` được sử dụng để khai báo rằng một biến nằm trong không gian tên toàn cục. Khi bạn định nghĩa một biến trong một thủ tục mà bạn muốn nó có thể truy cập được từ toàn bộ chương trình, bạn cần khai báo biến đó là toàn cục. 

### Cú pháp
```tcl
global varName1 varName2 ...
```

### Mục đích
Lệnh này cho phép bạn truy cập và sửa đổi các biến toàn cục từ các thủ tục hoặc các ngữ cảnh khác mà không cần phải truyền biến dưới dạng tham số.

### Sử dụng
- Để sử dụng lệnh `global`, bạn chỉ cần gọi nó trong thủ tục nơi bạn muốn sử dụng biến toàn cục.
- Khi biến đã được khai báo là toàn cục, bạn có thể gán giá trị cho nó hoặc đọc giá trị của nó.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng lệnh `global` trong Tcl:

### Ví dụ 1: Khai báo biến toàn cục
```tcl
set myVar 10

proc incrementVar {} {
    global myVar
    set myVar [expr {$myVar + 1}]
}

incrementVar
puts $myVar  ; # Kết quả: 11
```

### Ví dụ 2: Sử dụng nhiều biến toàn cục
```tcl
set varA 5
set varB 10

proc addVars {} {
    global varA varB
    return [expr {$varA + $varB}]
}

puts [addVars]  ; # Kết quả: 15
```

## Giải thích
- **Cạm bẫy Thường Gặp**: Khi bạn không khai báo một biến là toàn cục trong thủ tục, Tcl sẽ tự động tạo một biến cục bộ với cùng tên, điều này có thể gây ra nhầm lẫn.
- **Lưu Ý**: Chỉ nên sử dụng biến toàn cục khi thật sự cần thiết. Sử dụng biến cục bộ hoặc tham số của thủ tục là cách tốt hơn để duy trì tính rõ ràng và tránh xung đột biến.

## Tóm tắt Một Dòng
Lệnh `global` trong Tcl cho phép truy cập và chỉnh sửa các biến toàn cục từ bên trong các thủ tục, giúp quản lý trạng thái của chương trình một cách hiệu quả.