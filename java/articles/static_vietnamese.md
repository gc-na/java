<!--
Meta Description: # Từ Khóa "static" Trong JAVA: Tính Năng Cốt Lõi Của Ngôn Ngữ Lập Trình ## Tóm Tắt Từ khóa "static" trong JAVA cho phép bạn định nghĩa các thành phần ...
Meta Keywords: tĩnh, biến, static, thể, được
-->

# Từ Khóa "static" Trong JAVA: Tính Năng Cốt Lõi Của Ngôn Ngữ Lập Trình

## Tóm Tắt
Từ khóa "static" trong JAVA cho phép bạn định nghĩa các thành phần tĩnh (static members) của lớp, bao gồm biến và phương thức, có thể được truy cập mà không cần phải tạo ra một đối tượng của lớp đó.

## Tài Liệu
### Mục Đích
Từ khóa "static" trong JAVA được sử dụng để khai báo các thành phần chung cho tất cả các đối tượng của lớp. Điều này có nghĩa là tất cả các đối tượng của lớp sẽ chia sẻ cùng một giá trị của biến tĩnh và phương thức tĩnh có thể được gọi mà không cần khởi tạo một đối tượng.

### Cách Sử Dụng
- **Biến tĩnh**: Biến được khai báo với từ khóa `static` và có thể được truy cập trực tiếp thông qua tên lớp.
- **Phương thức tĩnh**: Phương thức được khai báo với từ khóa `static` và cũng có thể được gọi mà không cần khởi tạo đối tượng.
- **Khối tĩnh**: Khối mã được thực thi khi lớp được nạp vào bộ nhớ, hữu ích cho việc khởi tạo biến tĩnh.

### Chi Tiết
- Các thành phần tĩnh có thể được truy cập bằng cách sử dụng tên lớp, ví dụ: `ClassName.staticVariable` hoặc `ClassName.staticMethod()`.
- Biến tĩnh không thuộc về một đối tượng cụ thể mà thuộc về lớp, do đó, nếu một đối tượng thay đổi giá trị của biến tĩnh, tất cả các đối tượng khác sẽ thấy sự thay đổi này.
- Phương thức tĩnh không thể truy cập vào các biến instance (biến không tĩnh) và phương thức instance vì chúng không thuộc về một đối tượng cụ thể.

## Ví Dụ
### Ví Dụ 1: Biến Tĩnh
```java
class Example {
    static int count = 0;

    Example() {
        count++;
    }

    static void showCount() {
        System.out.println("Count = " + count);
    }
}

public class Main {
    public static void main(String[] args) {
        new Example();
        new Example();
        Example.showCount(); // Output: Count = 2
    }
}
```

### Ví Dụ 2: Phương Thức Tĩnh
```java
class MathUtils {
    static int add(int a, int b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        int sum = MathUtils.add(5, 10);
        System.out.println("Sum = " + sum); // Output: Sum = 15
    }
}
```

## Giải Thích
- **Bẫy Thường Gặp**: Lỗi phổ biến là cố gắng truy cập vào các biến instance từ một phương thức tĩnh. Điều này sẽ dẫn đến lỗi biên dịch, vì không có đối tượng cụ thể để tham chiếu.
- **Sử Dụng Quá Nhiều**: Việc sử dụng quá nhiều biến và phương thức tĩnh có thể dẫn đến việc khó bảo trì và mở rộng mã, vì chúng tạo ra sự phụ thuộc mạnh mẽ giữa các phần của chương trình.

## Tóm Tắt Một Dòng
Từ khóa "static" trong JAVA cho phép khai báo các biến và phương thức tĩnh, có thể được truy cập mà không cần khởi tạo đối tượng, giúp quản lý tài nguyên hiệu quả hơn.