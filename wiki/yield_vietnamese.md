<!--
Meta Description: # Từ khóa "yield" trong Java: Cách sử dụng và ý nghĩa ## Tóm tắt Từ khóa `yield` trong Java được sử dụng trong các khối mã của `switch` để trả về giá ...
Meta Keywords: yield, trong, dụng, switch, một
-->

# Từ khóa "yield" trong Java: Cách sử dụng và ý nghĩa

## Tóm tắt
Từ khóa `yield` trong Java được sử dụng trong các khối mã của `switch` để trả về giá trị từ một nhánh cụ thể. Tính năng này giúp cải thiện khả năng đọc và bảo trì mã, đồng thời cho phép lập trình viên viết mã ngắn gọn hơn.

## Tài liệu
### Mục đích
`yield` là một từ khóa được giới thiệu trong Java 12 như một phần của cú pháp `switch` mới. Nó cho phép lập trình viên trả về giá trị từ một biểu thức `switch` một cách rõ ràng và trực quan hơn.

### Cách sử dụng
Để sử dụng `yield`, bạn cần định nghĩa một biểu thức `switch` và sử dụng từ khóa này trong các nhánh của nó. Dưới đây là cú pháp cơ bản:

```java
int result = switch (variable) {
    case value1 -> yield value1Result;
    case value2 -> yield value2Result;
    default -> yield defaultResult;
};
```

### Chi tiết
- `yield` chỉ có thể sử dụng trong các biểu thức `switch` và không thể dùng ngoài khuôn khổ này.
- Nó giúp loại bỏ sự cần thiết phải sử dụng lệnh `return` trong các nhánh `case`, làm cho mã trở nên dễ hiểu hơn.

## Ví dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng `yield` trong biểu thức `switch`:

```java
public class YieldExample {
    public static void main(String[] args) {
        int day = 3;
        String dayName = switch (day) {
            case 1 -> yield "Thứ Hai";
            case 2 -> yield "Thứ Ba";
            case 3 -> yield "Thứ Tư";
            case 4 -> yield "Thứ Năm";
            case 5 -> yield "Thứ Sáu";
            case 6 -> yield "Thứ Bảy";
            case 7 -> yield "Chủ Nhật";
            default -> yield "Ngày không hợp lệ";
        };
        System.out.println(dayName);
    }
}
```

### Giải thích
- **Cạm bẫy phổ biến**: Một số lập trình viên có thể nhầm lẫn giữa `yield` và `return`. Lưu ý rằng `yield` chỉ có thể được sử dụng trong biểu thức `switch`, trong khi `return` có thể được sử dụng trong bất kỳ phương thức nào.
- **Khả năng tương thích**: Từ khóa `yield` có thể không được hỗ trợ trong các phiên bản Java cũ hơn (trước Java 12). Đảm bảo rằng bạn đang sử dụng phiên bản Java 12 hoặc cao hơn.

## Tóm tắt một dòng
Từ khóa `yield` trong Java cho phép lập trình viên trả về giá trị từ các nhánh của biểu thức `switch` một cách rõ ràng và trực quan hơn.