<!--
Meta Description: # Từ Khóa "throws" trong JAVA: Hiểu và Sử Dụng ## Tóm Tắt Từ khóa `throws` trong Java được sử dụng để khai báo rằng một phương thức có thể ném một hoặ...
Meta Keywords: throws, ngoại, dụng, phương, thức
-->

# Từ Khóa "throws" trong JAVA: Hiểu và Sử Dụng

## Tóm Tắt
Từ khóa `throws` trong Java được sử dụng để khai báo rằng một phương thức có thể ném một hoặc nhiều ngoại lệ trong quá trình thực thi. Nó giúp lập trình viên quản lý ngoại lệ và xây dựng mã nguồn dễ bảo trì hơn.

## Tài Liệu
### Mục Đích
Từ khóa `throws` cho phép lập trình viên thông báo cho người dùng phương thức rằng có khả năng xảy ra ngoại lệ. Điều này buộc người gọi phương thức phải xử lý ngoại lệ đó, giúp tăng cường tính ổn định và độ tin cậy của ứng dụng.

### Cách Sử Dụng
- Từ khóa `throws` được sử dụng trong phần khai báo phương thức.
- Cú pháp chung: 
  ```java
  public returnType methodName(parameters) throws ExceptionType1, ExceptionType2 {
      // code
  }
  ```
- Tại đây, `ExceptionType1`, `ExceptionType2` là các loại ngoại lệ mà phương thức có thể ném ra.

### Chi Tiết
- `throws` thường được sử dụng với các ngoại lệ đã kiểm tra (checked exceptions). 
- Nếu một ngoại lệ không được xử lý trong phương thức, nó phải được khai báo với `throws`.
- Ví dụ, nếu một phương thức có khả năng ném `IOException`, bạn cần khai báo như sau:
  ```java
  public void readFile(String filePath) throws IOException {
      // code để đọc file
  }
  ```

## Ví Dụ
### Ví dụ 1: Sử dụng `throws` với IOException
```java
import java.io.*;

public class FileReaderExample {
    public void readFile(String filePath) throws IOException {
        BufferedReader reader = new BufferedReader(new FileReader(filePath));
        String line = reader.readLine();
        System.out.println(line);
        reader.close();
    }
}
```

### Ví dụ 2: Nhiều loại ngoại lệ
```java
public class MultiExceptionExample {
    public void processFile(String filePath) throws IOException, NumberFormatException {
        // code để đọc file và xử lý số
    }
}
```

## Giải Thích
- **Những cạm bẫy thường gặp**: Nếu không khai báo ngoại lệ, biên dịch sẽ xảy ra lỗi. Do đó, hãy chắc chắn rằng bạn đã khai báo tất cả các ngoại lệ có thể xảy ra.
- **Nên sử dụng `throws` khi nào?**: Sử dụng `throws` khi bạn không thể hoặc không muốn xử lý ngoại lệ trong phương thức đó và muốn truyền nó lên cho phương thức gọi.
- **Cần lưu ý**: Nếu bạn muốn xử lý ngoại lệ trong phương thức, thay vì sử dụng `throws`, bạn có thể sử dụng khối `try-catch`.

## Tóm Tắt Một Dòng
Từ khóa `throws` trong Java được sử dụng để thông báo rằng một phương thức có thể ném ra một hoặc nhiều ngoại lệ, buộc người gọi phải xử lý chúng.