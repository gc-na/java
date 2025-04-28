<!--
Meta Description: # Từ Khóa "finally" trong JAVA: Tất Tần Tật Thông Tin Bạn Cần Biết ## Tóm Tắt Từ khóa `finally` trong JAVA là một phần của cấu trúc xử lý ngoại lệ, đư...
Meta Keywords: finally, khối, trong, ngoại, được
-->

# Từ Khóa "finally" trong JAVA: Tất Tần Tật Thông Tin Bạn Cần Biết

## Tóm Tắt
Từ khóa `finally` trong JAVA là một phần của cấu trúc xử lý ngoại lệ, được sử dụng để đảm bảo rằng một đoạn mã sẽ luôn được thực thi, bất kể có xảy ra ngoại lệ hay không.

## Tài Liệu
### Mục Đích
`finally` được sử dụng trong khối `try-catch` để đảm bảo rằng mã bên trong khối `finally` sẽ được thực thi sau khi khối `try` và `catch` hoàn thành, ngay cả khi có ngoại lệ xảy ra.

### Cách Sử Dụng
Cú pháp cơ bản của `finally` như sau:

```java
try {
    // Mã có thể gây ra ngoại lệ
} catch (ExceptionType e) {
    // Xử lý ngoại lệ
} finally {
    // Mã sẽ luôn được thực thi
}
```

### Chi Tiết
- Khối `finally` là tùy chọn, nhưng khi được định nghĩa, nó sẽ luôn chạy sau khối `try` và `catch`.
- Nếu không có ngoại lệ xảy ra, mã trong `finally` cũng sẽ được thực thi.
- Nếu một ngoại lệ không được xử lý trong khối `try`, mã trong `finally` vẫn sẽ chạy.
- `finally` thường được sử dụng để dọn dẹp tài nguyên như đóng tệp hoặc kết nối cơ sở dữ liệu.

## Ví Dụ
### Ví Dụ Cơ Bản 1: Sử Dụng finally
```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            System.out.println("Khối try đang chạy");
            int result = 10 / 0; // Gây ra ngoại lệ
        } catch (ArithmeticException e) {
            System.out.println("Ngoại lệ: " + e.getMessage());
        } finally {
            System.out.println("Khối finally luôn được thực thi");
        }
    }
}
```
**Kết quả:**
```
Khối try đang chạy
Ngoại lệ: / by zero
Khối finally luôn được thực thi
```

### Ví Dụ Cơ Bản 2: Sử Dụng finally với Tài Nguyên
```java
import java.io.FileReader;
import java.io.IOException;

public class FinallyResourceExample {
    public static void main(String[] args) {
        FileReader file = null;
        try {
            file = new FileReader("file.txt");
            // Đọc tệp
        } catch (IOException e) {
            System.out.println("Lỗi: " + e.getMessage());
        } finally {
            if (file != null) {
                try {
                    file.close();
                } catch (IOException e) {
                    System.out.println("Không thể đóng tệp: " + e.getMessage());
                }
            }
            System.out.println("Khối finally đã thực thi");
        }
    }
}
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Quên Đóng Tài Nguyên:** Khi không sử dụng khối `finally`, có thể dẫn đến rò rỉ tài nguyên.
- **Ngoại Lệ Trong Khối finally:** Nếu có ngoại lệ xảy ra trong khối `finally`, nó có thể che khuất ngoại lệ từ khối `try` hoặc `catch`.
- **Sử Dụng `return` Trong Khối try hoặc catch:** Nếu `return` được sử dụng trong khối `try` hoặc `catch`, mã trong khối `finally` vẫn sẽ được thực thi, nhưng giá trị trả về sẽ là giá trị của `return`.

## Tóm Tắt Một Dòng
Từ khóa `finally` trong JAVA đảm bảo rằng mã trong khối `finally` sẽ được thực thi bất kể có xảy ra ngoại lệ trong khối `try` hay không.