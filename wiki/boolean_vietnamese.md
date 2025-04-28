<!--
Meta Description: # Boolean trong JAVA: Kiểu Dữ Liệu Cơ Bản và Cách Sử Dụng ## Tóm tắt Trong ngôn ngữ lập trình JAVA, kiểu dữ liệu `boolean` là một trong những kiểu dữ ...
Meta Keywords: boolean, dụng, các, kiểu, điều
-->

# Boolean trong JAVA: Kiểu Dữ Liệu Cơ Bản và Cách Sử Dụng

## Tóm tắt
Trong ngôn ngữ lập trình JAVA, kiểu dữ liệu `boolean` là một trong những kiểu dữ liệu cơ bản, được sử dụng để lưu trữ hai giá trị: `true` (đúng) và `false` (sai). Kiểu dữ liệu này rất quan trọng trong việc điều khiển luồng thực thi của chương trình thông qua các cấu trúc điều kiện.

## Tài liệu
### Mục đích
Kiểu `boolean` trong JAVA được sử dụng để biểu diễn các giá trị logic. Nó giúp lập trình viên thực hiện các phép so sánh và quyết định có nên thực thi một đoạn mã hay không dựa vào kết quả của các biểu thức điều kiện.

### Cách sử dụng
- **Khai báo**: Để khai báo một biến kiểu `boolean`, bạn sử dụng cú pháp sau:
  ```java
  boolean isActive = true;
  ```
- **Biểu thức điều kiện**: Bạn có thể sử dụng các toán tử so sánh (như `==`, `!=`, `>`, `<`, `>=`, `<=`) để tạo ra các biểu thức trả về giá trị `boolean`.
- **Cấu trúc điều kiện**: Kiểu dữ liệu `boolean` thường được sử dụng trong các cấu trúc điều kiện như `if`, `while`, và `for`.

### Chi tiết
- **Giá trị**: Biến `boolean` chỉ có thể nhận hai giá trị: `true` hoặc `false`. 
- **Phép so sánh**: Các phép so sánh giữa các biến kiểu số nguyên, số thực, hoặc chuỗi sẽ trả về giá trị `boolean`.
- **Boolean Logic**: Bạn có thể sử dụng các phép toán logic như `AND`, `OR`, và `NOT` để kết hợp nhiều biểu thức `boolean`.

## Ví dụ
### Ví dụ 1: Khai báo và sử dụng biến boolean
```java
public class BooleanExample {
    public static void main(String[] args) {
        boolean isSunny = true;
        if (isSunny) {
            System.out.println("Hôm nay trời nắng!");
        } else {
            System.out.println("Hôm nay trời mưa!");
        }
    }
}
```

### Ví dụ 2: Sử dụng biểu thức điều kiện
```java
public class ComparisonExample {
    public static void main(String[] args) {
        int a = 5;
        int b = 10;
        boolean result = a < b;
        System.out.println("Kết quả so sánh: " + result); // In ra: Kết quả so sánh: true
    }
}
```

## Giải thích
### Những cạm bẫy phổ biến
- **Khởi tạo giá trị**: Đảm bảo rằng biến `boolean` được khởi tạo trước khi sử dụng. Nếu không, bạn có thể gặp lỗi biên dịch.
- **So sánh không chính xác**: Khi so sánh các giá trị, hãy chắc chắn rằng bạn sử dụng đúng toán tử so sánh. Sử dụng `=` thay vì `==` sẽ dẫn đến lỗi không mong muốn.
- **Logic phức tạp**: Khi kết hợp nhiều biểu thức `boolean`, hãy cẩn thận với thứ tự thực hiện của các phép toán logic, vì điều này có thể ảnh hưởng đến kết quả cuối cùng.

## Tóm tắt một dòng
Kiểu dữ liệu `boolean` trong JAVA là kiểu cơ bản dùng để biểu diễn giá trị logic, cho phép lập trình viên điều khiển luồng thực thi của chương trình thông qua các biểu thức điều kiện.