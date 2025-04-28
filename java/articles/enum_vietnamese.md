<!--
Meta Description: # Enum trong Java: Tất cả những điều bạn cần biết ## Tóm tắt Enum (liệt kê) trong Java là một loại dữ liệu cho phép bạn định nghĩa một tập hợp các hằn...
Meta Keywords: enum, các, dụng, một, java
-->

# Enum trong Java: Tất cả những điều bạn cần biết

## Tóm tắt
Enum (liệt kê) trong Java là một loại dữ liệu cho phép bạn định nghĩa một tập hợp các hằng số có tên. Nó rất hữu ích để quản lý các giá trị cố định và cải thiện tính rõ ràng của mã nguồn.

## Tài liệu
Enum trong Java được giới thiệu từ phiên bản 5 (Java 5) và cho phép lập trình viên tạo ra một tập hợp các giá trị cố định. Enum giúp mã nguồn trở nên dễ đọc hơn, đồng thời giảm thiểu lỗi khi sử dụng các giá trị không hợp lệ.

### Mục đích
- Để định nghĩa các hằng số có ý nghĩa, giúp mã nguồn dễ hiểu hơn.
- Đảm bảo rằng chỉ có các giá trị đã được định nghĩa mới có thể được sử dụng.
- Tạo ra một kiểu dữ liệu mạnh mẽ hơn so với việc sử dụng các hằng số kiểu int hay String.

### Cách sử dụng
Enum được khai báo bằng từ khóa `enum`, theo sau là tên của enum cùng với danh sách các hằng số được phân cách bằng dấu phẩy.

```java
public enum Màu {
    ĐỎ, XANH, VÀNG;
}
```

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách tạo và sử dụng enum trong Java:

```java
public enum Ngày {
    THỨ_HAI, THỨ_BA, THỨ_TƯ, THỨ_NĂM, THỨ_SÁU, THỨ_BẢY, CHỦ_NHẬT;
}

public class Main {
    public static void main(String[] args) {
        Ngày hômNay = Ngày.THỨ_BA;
        
        switch (hômNay) {
            case THỨ_HAI:
                System.out.println("Hôm nay là thứ Hai.");
                break;
            case THỨ_BA:
                System.out.println("Hôm nay là thứ Ba.");
                break;
            // Các trường hợp khác
            default:
                System.out.println("Hôm nay không phải ngày làm việc.");
        }
    }
}
```

## Giải thích
Khi sử dụng enum, có một số điều cần lưu ý:
- Enum không thể kế thừa từ một lớp khác, nhưng có thể thực hiện các interface.
- Enum có thể có các phương thức và biến, giúp mở rộng chức năng của nó.
- Tránh việc so sánh enum bằng cách sử dụng `==`. Nên sử dụng phương thức `.equals()` để đảm bảo tính chính xác.

Các lỗi phổ biến khi sử dụng enum bao gồm việc quên thêm các trường hợp trong cấu trúc điều kiện `switch`, hoặc sử dụng các giá trị không thuộc enum, dẫn đến lỗi biên dịch.

## Tóm tắt một câu
Enum trong Java cung cấp một cách hiệu quả và an toàn để định nghĩa và sử dụng các hằng số có tên trong mã nguồn.