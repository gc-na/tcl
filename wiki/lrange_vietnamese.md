<!--
Meta Description: # Lệnh lrange trong Tcl: Cách sử dụng và ví dụ ## Tóm tắt Lệnh `lrange` trong Tcl được sử dụng để lấy một đoạn con từ danh sách. Nó cho phép người dùn...
Meta Keywords: chỉ, danh, sách, lrange, kết
-->

# Lệnh lrange trong Tcl: Cách sử dụng và ví dụ

## Tóm tắt
Lệnh `lrange` trong Tcl được sử dụng để lấy một đoạn con từ danh sách. Nó cho phép người dùng chỉ định chỉ số bắt đầu và chỉ số kết thúc để trích xuất phần tử từ danh sách.

## Tài liệu hướng dẫn
Lệnh `lrange` có cú pháp như sau:

```
lrange danh_sách chỉ_số_bắt_đầu chỉ_số_kết_thúc
```

### Mục đích
Lệnh này cho phép bạn lấy một đoạn con của danh sách mà bạn đã tạo, từ chỉ số bắt đầu đến chỉ số kết thúc, giúp việc thao tác và xử lý danh sách trở nên linh hoạt hơn.

### Cách sử dụng
- `danh_sách`: Đây là danh sách mà bạn muốn lấy đoạn con.
- `chỉ_số_bắt_đầu`: Chỉ số bắt đầu của đoạn con (bao gồm).
- `chỉ_số_kết_thúc`: Chỉ số kết thúc của đoạn con (bao gồm). Nếu chỉ số này lớn hơn chỉ số cuối cùng của danh sách, Tcl sẽ tự động điều chỉnh nó về chỉ số cuối cùng.

`lrange` trả về một danh sách mới chứa các phần tử trong khoảng từ chỉ số bắt đầu đến chỉ số kết thúc.

## Ví dụ
### Ví dụ cơ bản
```tcl
set danh_sach {a b c d e f g}
set ket_qua [lrange $danh_sach 2 4]
puts $ket_qua  ;# Kết quả: c d e
```

### Ví dụ với chỉ số âm
```tcl
set danh_sach {a b c d e f g}
set ket_qua [lrange $danh_sach -4 -2]
puts $ket_qua  ;# Kết quả: e f g
```

### Ví dụ với chỉ số vượt quá
```tcl
set danh_sach {a b c d e f g}
set ket_qua [lrange $danh_sach 3 10]
puts $ket_qua  ;# Kết quả: d e f g
```

## Giải thích
Một số điều cần lưu ý khi sử dụng lệnh `lrange`:
- Nếu chỉ số bắt đầu lớn hơn chỉ số kết thúc, lệnh sẽ trả về danh sách rỗng.
- Chỉ số trong Tcl bắt đầu từ 0, vì vậy phần tử đầu tiên của danh sách có chỉ số 0.
- Nếu chỉ số bắt đầu hoặc chỉ số kết thúc là âm, Tcl sẽ tính toán từ cuối danh sách. Ví dụ, -1 là phần tử cuối cùng trong danh sách.

## Tóm tắt một dòng
Lệnh `lrange` trong Tcl cho phép bạn trích xuất một đoạn con từ danh sách dựa trên chỉ số bắt đầu và kết thúc.