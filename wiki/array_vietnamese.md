<!--
Meta Description: # Mảng trong Tcl: Cách Sử Dụng và Ứng Dụng ## Tóm tắt Mảng trong Tcl là một cấu trúc dữ liệu cho phép lưu trữ và truy cập các giá trị theo khóa (key),...
Meta Keywords: mảng, giá, trị, liệu, khóa
-->

# Mảng trong Tcl: Cách Sử Dụng và Ứng Dụng

## Tóm tắt
Mảng trong Tcl là một cấu trúc dữ liệu cho phép lưu trữ và truy cập các giá trị theo khóa (key), giúp tổ chức dữ liệu một cách hiệu quả và linh hoạt. Mảng hỗ trợ nhiều kiểu dữ liệu và cung cấp các tính năng mạnh mẽ cho lập trình viên.

## Tài liệu
Mảng trong Tcl được sử dụng để lưu trữ các cặp khóa-giá trị, cho phép lập trình viên dễ dàng truy cập và quản lý dữ liệu. Cú pháp cơ bản để khai báo một mảng là sử dụng lệnh `array`. Mảng có thể được khai báo mà không cần xác định kích thước trước, và có thể chứa nhiều kiểu dữ liệu khác nhau.

### Cú pháp
```tcl
array set arrayName {key1 value1 key2 value2 ...}
```

### Chức năng
- **Khai báo mảng**: Bạn có thể sử dụng lệnh `array set` để khởi tạo một mảng mới với các cặp khóa-giá trị.
- **Truy cập giá trị**: Sử dụng cú pháp `arrayName(key)` để truy cập giá trị tương ứng với khóa.
- **Lặp qua mảng**: Sử dụng lệnh `array names` để lấy danh sách các khóa và lệnh `array get` để lấy giá trị của khóa.

### Ví dụ
#### Khai báo và truy cập mảng
```tcl
# Khởi tạo mảng
array set myArray {name "John" age 30 city "Hanoi"}

# Truy cập giá trị
puts "Tên: $myArray(name)"
puts "Tuổi: $myArray(age)"
puts "Thành phố: $myArray(city)"
```

#### Lặp qua mảng
```tcl
# Lặp qua các khóa trong mảng
foreach key [array names myArray] {
    puts "$key: $myArray($key)"
}
```

## Giải thích
Mặc dù mảng trong Tcl rất hữu ích, nhưng có một số điều cần lưu ý:
- **Khóa phải là duy nhất**: Nếu bạn cố gắng thêm một giá trị mới với khóa đã tồn tại, giá trị cũ sẽ bị ghi đè.
- **Không hỗ trợ kiểu dữ liệu phức tạp**: Mảng chỉ hỗ trợ lưu trữ giá trị dạng chuỗi, nên bạn cần chuyển đổi các kiểu dữ liệu phức tạp thành chuỗi nếu cần.
- **Kích thước không giới hạn**: Mảng trong Tcl có thể chứa số lượng phần tử lớn, nhưng cần lưu ý về hiệu suất khi làm việc với các mảng rất lớn.

## Tóm tắt một dòng
Mảng trong Tcl là cấu trúc dữ liệu mạnh mẽ cho phép lưu trữ và truy cập dữ liệu theo cặp khóa-giá trị, giúp lập trình viên quản lý thông tin hiệu quả.