<!--
Meta Description: # Lệnh switch trong Tcl: Cách sử dụng và ứng dụng ## Tóm tắt Lệnh `switch` trong Tcl cho phép người lập trình thực hiện các lựa chọn điều kiện dựa trê...
Meta Keywords: giá, trị, lệnh, switch, các
-->

# Lệnh switch trong Tcl: Cách sử dụng và ứng dụng

## Tóm tắt
Lệnh `switch` trong Tcl cho phép người lập trình thực hiện các lựa chọn điều kiện dựa trên giá trị của một biến. Đây là một công cụ mạnh mẽ cho việc xử lý các điều kiện phức tạp, giúp mã nguồn trở nên rõ ràng và dễ đọc hơn.

## Tài liệu
Lệnh `switch` được sử dụng để kiểm tra giá trị của một biến và thực hiện các hành động khác nhau dựa trên giá trị đó. Cú pháp cơ bản của lệnh này như sau:

```tcl
switch ?-exact? <biến> {
    <giá trị 1> { <hành động 1> }
    <giá trị 2> { <hành động 2> }
    ...
    default { <hành động mặc định> }
}
```

### Mô tả
- **-exact**: Tùy chọn này cho phép so sánh chính xác (các giá trị sẽ phải giống hệt nhau).
- `<biến>`: Biến mà bạn muốn so sánh giá trị.
- `<giá trị>`: Giá trị mà biến sẽ được so sánh với.
- `<hành động>`: Các lệnh Tcl sẽ được thực hiện nếu giá trị khớp.

Nếu không có giá trị nào khớp, lệnh trong khối `default` sẽ được thực thi (nếu có).

## Ví dụ
### Ví dụ cơ bản
```tcl
set color "red"
switch $color {
    "red" { puts "Màu đỏ" }
    "green" { puts "Màu xanh" }
    "blue" { puts "Màu xanh dương" }
    default { puts "Màu không xác định" }
}
```
Kết quả sẽ là: `Màu đỏ`.

### Ví dụ với tùy chọn -exact
```tcl
set value 2
switch -exact $value {
    1 { puts "Giá trị là 1" }
    2 { puts "Giá trị là 2" }
    3 { puts "Giá trị là 3" }
    default { puts "Giá trị không xác định" }
}
```
Kết quả sẽ là: `Giá trị là 2`.

## Giải thích
Một số điểm cần lưu ý khi sử dụng lệnh `switch`:
- **Tính chính xác**: Khi sử dụng tùy chọn `-exact`, các kiểu dữ liệu khác nhau (ví dụ: số và chuỗi) sẽ không khớp với nhau.
- **Khối default**: Nếu không có khối `default`, không có hành động nào sẽ được thực hiện nếu không có giá trị nào khớp.
- **Nesting**: Bạn có thể lồng nhiều lệnh `switch` bên trong nhau để xử lý các điều kiện phức tạp hơn.

## Tóm tắt một dòng
Lệnh `switch` trong Tcl cho phép bạn kiểm tra giá trị của một biến và thực hiện các hành động khác nhau dựa trên giá trị đó, giúp mã nguồn trở nên rõ ràng và dễ quản lý.