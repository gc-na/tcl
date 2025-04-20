<!--
Meta Description: # expr - Tính toán biểu thức trong Tcl ## Tóm tắt Lệnh `expr` trong Tcl được sử dụng để thực hiện tính toán toán học và xử lý biểu thức. Nó cho phép n...
Meta Keywords: expr, toán, phép, các, tcl
-->

# expr - Tính toán biểu thức trong Tcl

## Tóm tắt
Lệnh `expr` trong Tcl được sử dụng để thực hiện tính toán toán học và xử lý biểu thức. Nó cho phép người dùng thực hiện các phép toán số học, logic và so sánh trong một cú pháp đơn giản và dễ hiểu.

## Tài liệu
Lệnh `expr` trong Tcl cung cấp khả năng thực hiện các phép toán và tính toán biểu thức. Nó hỗ trợ nhiều loại phép toán như cộng, trừ, nhân, chia, và các phép toán logic như AND, OR. Cú pháp cơ bản của lệnh `expr` như sau:

```tcl
expr expression
```

Trong đó, `expression` là một biểu thức mà bạn muốn tính toán. `expr` có thể xử lý các số nguyên, số thực, và các toán tử so sánh. 

### Các phép toán cơ bản:
- **Số học**: `+`, `-`, `*`, `/`, `%`
- **So sánh**: `==`, `!=`, `<`, `>`, `<=`, `>=`
- **Logic**: `&&`, `||`, `!`

Ví dụ, bạn có thể sử dụng `expr` để thực hiện phép cộng hai số:

```tcl
set result [expr 3 + 5]
puts $result  ;# Kết quả: 8
```

## Ví dụ
Dưới đây là một số ví dụ về cách sử dụng lệnh `expr`:

1. **Phép cộng**:
   ```tcl
   set sum [expr 10 + 20]
   puts $sum  ;# Kết quả: 30
   ```

2. **Phép nhân**:
   ```tcl
   set product [expr 5 * 6]
   puts $product  ;# Kết quả: 30
   ```

3. **So sánh**:
   ```tcl
   set isEqual [expr 10 == 10]
   puts $isEqual  ;# Kết quả: 1 (true)
   ```

4. **Sử dụng biến trong biểu thức**:
   ```tcl
   set a 10
   set b 20
   set result [expr $a + $b]
   puts $result  ;# Kết quả: 30
   ```

## Giải thích
Khi sử dụng lệnh `expr`, có một số điều cần lưu ý:

- **Quy tắc ưu tiên**: Các phép toán sẽ được thực hiện theo thứ tự ưu tiên toán học. Bạn có thể sử dụng dấu ngoặc để xác định thứ tự thực hiện.
- **Kiểu dữ liệu**: `expr` tự động chuyển đổi giữa các kiểu dữ liệu nếu cần thiết. Tuy nhiên, việc hiểu rõ kiểu dữ liệu sẽ giúp tránh các lỗi không mong muốn.
- **Biểu thức logic**: Kết quả của các biểu thức logic sẽ là 0 (false) hoặc 1 (true).

Một điều thường gặp là việc quên sử dụng dấu ngoặc trong các biểu thức phức tạp, dẫn đến kết quả không chính xác. Hãy chắc chắn rằng bạn sử dụng dấu ngoặc một cách hợp lý để đảm bảo tính toán đúng theo mong đợi.

## Tóm tắt một dòng
Lệnh `expr` trong Tcl cho phép thực hiện tính toán và xử lý biểu thức đơn giản với cú pháp dễ hiểu, hỗ trợ nhiều phép toán khác nhau.