<!--
Meta Description: # Lệnh foreach trong Tcl: Cách sử dụng và ví dụ ## Tóm tắt Lệnh `foreach` trong Tcl cho phép lập trình viên lặp qua các phần tử trong danh sách, thực ...
Meta Keywords: danh, sách, hiện, trong, lặp
-->

# Lệnh foreach trong Tcl: Cách sử dụng và ví dụ

## Tóm tắt
Lệnh `foreach` trong Tcl cho phép lập trình viên lặp qua các phần tử trong danh sách, thực hiện một đoạn mã cho mỗi phần tử đó, giúp xử lý dữ liệu một cách hiệu quả.

## Tài liệu
### Mục đích
Lệnh `foreach` được sử dụng để lặp qua các danh sách trong Tcl. Điều này hữu ích khi bạn cần thực hiện các thao tác trên từng phần tử của danh sách mà không cần phải sử dụng vòng lặp phức tạp hơn.

### Cú pháp
```tcl
foreach variableList list {
    # Các lệnh thực hiện cho từng phần tử
}
```

- `variableList`: Danh sách các biến mà mỗi biến sẽ nhận giá trị từ danh sách lặp qua.
- `list`: Danh sách các phần tử mà bạn muốn lặp qua.

### Chi tiết
Lệnh `foreach` có thể xử lý nhiều biến trong một lần lặp. Nếu `list` có nhiều danh sách con, bạn có thể chỉ định số lượng biến tương ứng. Nếu số lượng biến không khớp với số lượng danh sách, Tcl sẽ ném ra lỗi.

## Ví dụ
### Ví dụ 1: Lặp qua một danh sách đơn giản
```tcl
set myList {1 2 3 4 5}
foreach num $myList {
    puts "Số hiện tại: $num"
}
```
*Đầu ra:*
```
Số hiện tại: 1
Số hiện tại: 2
Số hiện tại: 3
Số hiện tại: 4
Số hiện tại: 5
```

### Ví dụ 2: Lặp qua nhiều danh sách
```tcl
set names {Alice Bob Charlie}
set ages {25 30 35}
foreach name $names age $ages {
    puts "$name is $age years old."
}
```
*Đầu ra:*
```
Alice is 25 years old.
Bob is 30 years old.
Charlie is 35 years old.
```

## Giải thích
### Những điều cần lưu ý
- Nếu số lượng biến trong `variableList` không khớp với số lượng danh sách trong `list`, Tcl sẽ phát sinh lỗi.
- Nếu danh sách rỗng, đoạn mã trong khối lệnh sẽ không được thực hiện.
- Trong trường hợp bạn cần dừng vòng lặp, có thể sử dụng lệnh `break` để thoát khỏi `foreach`.

## Tóm tắt một câu
Lệnh `foreach` trong Tcl là công cụ mạnh mẽ để lặp qua danh sách và thực hiện các thao tác trên từng phần tử một cách dễ dàng và hiệu quả.