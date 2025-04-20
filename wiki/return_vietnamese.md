<!--
Meta Description: # Lệnh "return" trong Tcl: Cách sử dụng và ý nghĩa ## Tóm tắt Lệnh `return` trong Tcl được sử dụng để trả về giá trị từ một thủ tục (procedure) hoặc l...
Meta Keywords: return, lệnh, trả, giá, trị
-->

# Lệnh "return" trong Tcl: Cách sử dụng và ý nghĩa

## Tóm tắt
Lệnh `return` trong Tcl được sử dụng để trả về giá trị từ một thủ tục (procedure) hoặc lệnh. Điều này cho phép bạn quản lý luồng điều khiển trong chương trình Tcl của mình một cách hiệu quả.

## Tài liệu
Lệnh `return` có mục đích chính là kết thúc việc thực thi của một thủ tục và trả về một hoặc nhiều giá trị cho nơi gọi thủ tục đó. Cú pháp cơ bản của lệnh `return` như sau:

```tcl
return ?value?
```

Trong đó:
- `value`: Giá trị mà bạn muốn trả về. Bạn có thể trả về nhiều giá trị bằng cách tách chúng bằng khoảng trắng.

### Chi tiết:
- `return` sẽ kết thúc thủ tục ngay lập tức và không thực hiện các lệnh còn lại trong thủ tục.
- Nếu không có giá trị nào được chỉ định, lệnh `return` sẽ trả về giá trị `""` (chuỗi rỗng).
- Bạn có thể sử dụng `return` trong các thủ tục được định nghĩa bằng lệnh `proc` hoặc trong các lệnh khác có ngữ cảnh tương tự.

## Ví dụ
1. Ví dụ cơ bản với một thủ tục trả về một giá trị:
```tcl
proc add {a b} {
    return [expr {$a + $b}]
}

set result [add 5 10]
puts "Kết quả: $result"  ;# In ra "Kết quả: 15"
```

2. Ví dụ với nhiều giá trị trả về:
```tcl
proc divide {a b} {
    if {$b == 0} {
        return "Không thể chia cho 0"
    }
    return [expr {$a / $b}] [expr {$a % $b}]
}

set result [divide 10 3]
puts "Kết quả: $result"  ;# In ra "Kết quả: 3 1"
```

## Giải thích
Một số điều cần lưu ý khi sử dụng lệnh `return`:
- Nếu bạn quên thêm giá trị trả về, thủ tục sẽ trả về chuỗi rỗng, điều này có thể gây nhầm lẫn nếu bạn không nhận ra rằng không có giá trị nào được trả về.
- Lệnh `return` không chỉ dừng thủ tục mà còn có thể được sử dụng để kết thúc một khối lệnh trong một ngữ cảnh nhất định, điều này có thể dẫn đến việc không mong muốn nếu bạn không cẩn thận.
- Hãy chắc chắn rằng các giá trị được trả về phù hợp với cách mà bạn dự định sử dụng chúng ở nơi gọi thủ tục.

## Tóm tắt một dòng
Lệnh `return` trong Tcl cho phép bạn kết thúc thủ tục và trả về giá trị cho nơi gọi, giúp quản lý luồng điều khiển trong chương trình.