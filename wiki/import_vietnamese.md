<!--
Meta Description: # Lệnh import trong Java: Cách sử dụng và ý nghĩa ## Tóm tắt Lệnh `import` trong Java cho phép lập trình viên sử dụng các lớp và gói (packages) từ thư...
Meta Keywords: lớp, java, các, nhập, import
-->

# Lệnh import trong Java: Cách sử dụng và ý nghĩa

## Tóm tắt
Lệnh `import` trong Java cho phép lập trình viên sử dụng các lớp và gói (packages) từ thư viện bên ngoài hoặc từ chính các gói do họ tạo ra mà không cần phải chỉ định đầy đủ tên lớp mỗi khi sử dụng.

## Tài liệu
Lệnh `import` được sử dụng để khai báo rằng một lớp trong mã nguồn Java cần sử dụng các lớp khác từ các gói khác. Việc sử dụng lệnh này giúp mã nguồn trở nên ngắn gọn và dễ hiểu hơn. 

### Mục đích
- **Giảm độ dài mã nguồn**: Thay vì phải viết toàn bộ tên gói mỗi khi sử dụng một lớp, bạn chỉ cần sử dụng lệnh `import` để chỉ định một lần.
- **Tăng khả năng đọc hiểu**: Mã nguồn trở nên dễ đọc hơn khi không phải lặp lại tên gói dài dòng.

### Cách sử dụng
Lệnh `import` được đặt ở đầu file Java, trước khi khai báo lớp. Cú pháp cơ bản như sau:
```java
import packageName.ClassName; // Nhập một lớp cụ thể
import packageName.*; // Nhập tất cả các lớp trong gói
```

**Ví dụ**: 
```java
import java.util.ArrayList; // Nhập lớp ArrayList
import java.util.*; // Nhập tất cả các lớp trong gói java.util
```

## Ví dụ
### Ví dụ 1: Nhập một lớp cụ thể
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Nhập tên của bạn:");
        String name = scanner.nextLine();
        System.out.println("Xin chào, " + name + "!");
    }
}
```

### Ví dụ 2: Nhập tất cả các lớp trong một gói
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Java");
        list.add("Python");
        System.out.println(list);
    }
}
```

## Giải thích
- **Nhập một lớp cụ thể**: Khi bạn chỉ định một lớp cụ thể để nhập, bạn có thể tránh xung đột tên với các lớp khác có tên tương tự từ các gói khác.
- **Nhập tất cả các lớp**: Mặc dù nhập tất cả các lớp trong một gói có thể tiện lợi, nhưng điều này có thể dẫn đến xung đột tên nếu có nhiều lớp có tên giống nhau trong các gói khác nhau.
- **Lưu ý về hiệu suất**: Việc nhập một lớp cụ thể không ảnh hưởng đến hiệu suất chạy chương trình, nhưng việc nhập tất cả các lớp có thể làm phức tạp mã nguồn nếu không quản lý tốt.

## Tóm tắt một dòng
Lệnh `import` trong Java giúp lập trình viên dễ dàng sử dụng các lớp từ các gói khác mà không cần chỉ định tên đầy đủ, làm cho mã nguồn gọn gàng và dễ hiểu hơn.