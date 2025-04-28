<!--
Meta Description: # Câu Lệnh Switch Trong Java: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm Tắt Câu lệnh `switch` trong Java là một cấu trúc điều kiện giúp lựa chọn một trong nh...
Meta Keywords: switch, câu, lệnh, case, break
-->

# Câu Lệnh Switch Trong Java: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm Tắt
Câu lệnh `switch` trong Java là một cấu trúc điều kiện giúp lựa chọn một trong nhiều khối mã để thực thi dựa trên giá trị của một biến. Đây là một công cụ hữu ích để thay thế cho nhiều câu lệnh `if-else` phức tạp.

## Tài Liệu
### Mục Đích
Câu lệnh `switch` cho phép lập trình viên kiểm tra một biến với nhiều giá trị khác nhau, từ đó thực thi khối mã tương ứng mà không cần phải viết nhiều câu lệnh `if-else`. Nó giúp mã nguồn dễ đọc và quản lý hơn.

### Cách Sử Dụng
Câu lệnh `switch` có cấu trúc như sau:

```java
switch (biến) {
    case giá_trị_1:
        // khối mã thực thi khi biến bằng giá_trị_1
        break;
    case giá_trị_2:
        // khối mã thực thi khi biến bằng giá_trị_2
        break;
    // có thể thêm nhiều case khác
    default:
        // khối mã thực thi khi không khớp với bất kỳ case nào
}
```

### Chi Tiết
- **Biến**: Có thể là kiểu nguyên thủy như `int`, `char`, hoặc kiểu đối tượng `String`.
- **case**: Mỗi `case` kiểm tra một giá trị cụ thể và thực thi khối mã tương ứng nếu điều kiện đúng.
- **break**: Dùng để thoát khỏi câu lệnh `switch`. Nếu không có `break`, chương trình sẽ tiếp tục thực thi các khối mã phía dưới (tính năng "fall-through").
- **default**: Khối mã này sẽ được thực thi nếu không có `case` nào khớp.

## Ví Dụ
### Ví Dụ 1: Sử Dụng Câu Lệnh Switch Với Kiểu Số Nguyên
```java
int ngay = 3;
switch (ngay) {
    case 1:
        System.out.println("Thứ Hai");
        break;
    case 2:
        System.out.println("Thứ Ba");
        break;
    case 3:
        System.out.println("Thứ Tư");
        break;
    default:
        System.out.println("Ngày không hợp lệ");
}
```

### Ví Dụ 2: Sử Dụng Câu Lệnh Switch Với Kiểu String
```java
String phuongTien = "xe hơi";
switch (phuongTien) {
    case "xe đạp":
        System.out.println("Phương tiện thân thiện với môi trường");
        break;
    case "xe hơi":
        System.out.println("Phương tiện di chuyển nhanh");
        break;
    default:
        System.out.println("Phương tiện không xác định");
}
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Thiếu break**: Nếu bạn quên câu lệnh `break`, chương trình sẽ tiếp tục thực thi các `case` phía dưới, có thể dẫn đến kết quả không mong muốn.
- **Giá trị không khớp**: Nếu không có giá trị nào khớp với biến trong `switch`, khối mã `default` sẽ được thực thi. Điều này đôi khi có thể gây nhầm lẫn.

### Ghi Chú Bổ Sung
- Câu lệnh `switch` có thể xử lý nhiều loại giá trị khác nhau nhưng không hỗ trợ kiểu `boolean`.
- Từ Java 12, có tính năng `switch expression` cho phép trả về giá trị trực tiếp từ câu lệnh `switch`.

## Tóm Tắt Một Dòng
Câu lệnh `switch` trong Java là một công cụ mạnh mẽ giúp xử lý nhiều điều kiện khác nhau một cách hiệu quả và dễ đọc.