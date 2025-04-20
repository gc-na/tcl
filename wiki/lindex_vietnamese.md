<!--
Meta Description: # Lindex trong Tcl: Cú Pháp và Cách Sử Dụng ## Tóm tắt Lindex là một lệnh trong Tcl dùng để truy cập phần tử tại một chỉ mục cụ thể trong danh sách. L...
Meta Keywords: danh, sách, lindex, phần, chỉ
-->

# Lindex trong Tcl: Cú Pháp và Cách Sử Dụng

## Tóm tắt
Lindex là một lệnh trong Tcl dùng để truy cập phần tử tại một chỉ mục cụ thể trong danh sách. Lệnh này rất hữu ích khi làm việc với dữ liệu dạng danh sách, cho phép bạn dễ dàng lấy thông tin từ các phần tử khác nhau.

## Tài liệu
Lệnh `lindex` trong Tcl có chức năng chính là truy xuất một phần tử từ danh sách. Cú pháp của lệnh như sau:

```
lindex danh_sách chỉ_mục
```

- **danh_sách**: Đây là danh sách mà bạn muốn truy cập. Danh sách có thể bao gồm các phần tử kiểu chuỗi, số, hay thậm chí là các danh sách lồng nhau.
- **chỉ_mục**: Đây là chỉ số của phần tử bạn muốn lấy từ danh sách. Lưu ý rằng chỉ số bắt đầu từ 0.

### Chi tiết
- Nếu chỉ số nằm ngoài phạm vi của danh sách, lệnh sẽ trả về giá trị rỗng.
- Bạn có thể sử dụng lệnh này với danh sách lồng nhau để truy cập phần tử bên trong các danh sách con.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng lệnh `lindex`:

### Ví dụ 1: Truy cập phần tử trong danh sách
```tcl
set myList {apple banana cherry}
set item [lindex $myList 1]  ; # item sẽ chứa "banana"
puts $item
```

### Ví dụ 2: Truy cập phần tử trong danh sách lồng nhau
```tcl
set nestedList { {apple orange} {banana grape} {cherry peach} }
set item [lindex [lindex $nestedList 1] 0]  ; # item sẽ chứa "banana"
puts $item
```

### Ví dụ 3: Xử lý trường hợp chỉ số ngoài phạm vi
```tcl
set myList {apple banana cherry}
set item [lindex $myList 5]  ; # item sẽ chứa ""
puts $item
```

## Giải thích
Khi sử dụng lệnh `lindex`, có một vài lưu ý quan trọng mà bạn cần chú ý:
- **Chỉ số bắt đầu từ 0**: Như đã đề cập, chỉ số bắt đầu từ 0, vì vậy phần tử đầu tiên có chỉ số 0, phần tử thứ hai có chỉ số 1, và vân vân.
- **Danh sách rỗng**: Nếu danh sách mà bạn cung cấp là rỗng, lệnh sẽ luôn trả về giá trị rỗng, bất kể chỉ số bạn đưa vào.
- **Danh sách lồng nhau**: Khi làm việc với danh sách lồng nhau, cần phải sử dụng `lindex` nhiều lần để truy cập vào các phần tử cụ thể.

## Tóm tắt một dòng
Lệnh `lindex` trong Tcl cho phép bạn truy cập phần tử tại một chỉ mục cụ thể trong danh sách, hỗ trợ thao tác với dữ liệu dạng danh sách một cách hiệu quả.