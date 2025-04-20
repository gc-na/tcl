<!--
Meta Description: # Lệnh "while" trong Tcl: Cách Sử Dụng và Ví Dụ Cụ Thể ## Tóm tắt Lệnh "while" trong Tcl được sử dụng để thực hiện một khối mã nhiều lần trong khi một...
Meta Keywords: lệnh, điều, kiện, khi, lặp
-->

# Lệnh "while" trong Tcl: Cách Sử Dụng và Ví Dụ Cụ Thể

## Tóm tắt
Lệnh "while" trong Tcl được sử dụng để thực hiện một khối mã nhiều lần trong khi một điều kiện nhất định vẫn đúng. Đây là một công cụ hữu ích khi bạn cần lặp lại một đoạn mã cho đến khi thỏa mãn một điều kiện cụ thể.

## Tài liệu
### Mục đích
Lệnh "while" cho phép lập trình viên thực hiện lặp lại một khối lệnh cho đến khi điều kiện được chỉ định trở thành sai. Điều này rất hữu ích trong các trường hợp cần xử lý tuần tự các tác vụ cho đến khi đạt được mục tiêu hoặc điều kiện yêu cầu.

### Cú pháp
```tcl
while {điều_kiện} {
    # khối lệnh
}
```

- **điều_kiện**: Biểu thức logic trả về giá trị true (đúng) hoặc false (sai).
- **khối lệnh**: Tập hợp các lệnh sẽ được thực hiện khi điều kiện là true.

### Chi tiết
- Lệnh "while" sẽ kiểm tra điều kiện trước khi thực hiện khối lệnh. Nếu điều kiện là true, khối lệnh sẽ được thực hiện và điều kiện sẽ được kiểm tra lại. Quá trình này tiếp tục cho đến khi điều kiện trở thành false.
- Nếu điều kiện ban đầu là false, khối lệnh sẽ không được thực hiện một lần nào.

## Ví dụ
### Ví dụ 1: Lặp qua số từ 1 đến 5
```tcl
set i 1
while {$i <= 5} {
    puts "Số hiện tại: $i"
    incr i
}
```

### Ví dụ 2: Lặp cho đến khi người dùng nhập đúng mật khẩu
```tcl
set correct_password "123456"
set user_input ""

while {$user_input != $correct_password} {
    set user_input [gets stdin "Nhập mật khẩu: "]
    puts "Mật khẩu không đúng, vui lòng thử lại."
}
puts "Mật khẩu đúng!"
```

## Giải thích
- **Những cạm bẫy phổ biến**: Một số lập trình viên mới có thể quên cập nhật giá trị của điều kiện trong khối lệnh, dẫn đến việc vòng lặp vô hạn. Hãy chắc chắn rằng bạn có cơ chế rõ ràng để thoát khỏi vòng lặp.
- **Cảnh báo hiệu suất**: Nếu điều kiện kiểm tra là phức tạp hoặc khối lệnh bên trong thực hiện các tác vụ nặng, vòng lặp có thể tiêu tốn nhiều tài nguyên. Hãy tối ưu hóa mã của bạn khi cần thiết.
- **Sự khác biệt với lệnh "for"**: Lệnh "while" phù hợp hơn cho các tình huống không xác định số lần lặp, trong khi "for" thường được sử dụng cho các vòng lặp có số lần lặp xác định.

## Tóm tắt một dòng
Lệnh "while" trong Tcl cho phép lập trình viên lặp lại khối lệnh cho đến khi điều kiện chỉ định trở thành sai, là công cụ mạnh mẽ cho lập trình điều kiện trong các ứng dụng.