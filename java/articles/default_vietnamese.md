<!--
Meta Description: # Từ Khóa "default" Trong JAVA: Cách Sử Dụng và Tính Năng ## Tóm Tắt Từ khóa "default" trong JAVA được sử dụng để định nghĩa các phương thức mặc định ...
Meta Keywords: interface, phương, thức, default, định
-->

# Từ Khóa "default" Trong JAVA: Cách Sử Dụng và Tính Năng

## Tóm Tắt
Từ khóa "default" trong JAVA được sử dụng để định nghĩa các phương thức mặc định trong các interface, cho phép các interface có thể chứa logic cài sẵn mà không cần phải triển khai lại trong từng lớp.

## Tài Liệu
### Mục Đích
Từ khóa "default" được giới thiệu từ phiên bản JAVA 8, cho phép lập trình viên thêm các phương thức vào interface mà không làm ảnh hưởng đến các lớp đã triển khai interface đó. Điều này giúp tăng cường khả năng mở rộng và duy trì mã nguồn.

### Cách Sử Dụng
Để sử dụng từ khóa "default", bạn chỉ cần khai báo phương thức trong interface với từ khóa "default" đi kèm. Cú pháp cơ bản như sau:

```java
interface TênInterface {
    void phươngThứcBìnhThường();
    
    default void phươngThứcMặcĐịnh() {
        // logic mặc định ở đây
    }
}
```

### Chi Tiết
- **Không bắt buộc**: Lớp cài đặt interface không cần phải triển khai phương thức mặc định.
- **Ghi đè**: Nếu lớp cài đặt muốn thay đổi hành vi của phương thức mặc định, nó có thể ghi đè phương thức đó.
- **Đa kế thừa**: Nếu một lớp cài đặt hai interface có cùng một phương thức mặc định, lập trình viên phải ghi đè phương thức đó để tránh xung đột.

## Ví Dụ
### Ví dụ Cơ Bản
Dưới đây là một ví dụ đơn giản về cách sử dụng từ khóa "default":

```java
interface Hinh {
    void ve();
    
    default void moTa() {
        System.out.println("Đây là một hình.");
    }
}

class HinhVuong implements Hinh {
    public void ve() {
        System.out.println("Vẽ hình vuông.");
    }
    
    // Ghi đè phương thức mặc định
    public void moTa() {
        System.out.println("Đây là hình vuông.");
    }
}

public class Main {
    public static void main(String[] args) {
        HinhVuong hinhVuong = new HinhVuong();
        hinhVuong.ve();
        hinhVuong.moTa();  // Kết quả: Đây là hình vuông.
    }
}
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Xung đột phương thức**: Nếu một lớp thực hiện nhiều interface có cùng một phương thức mặc định, lập trình viên phải ghi đè để tránh lỗi biên dịch.
- **Không thể sử dụng từ khóa "default" bên ngoài interface**: Từ khóa này chỉ có thể được sử dụng trong ngữ cảnh của interface.

## Tóm Tắt Một Dòng
Từ khóa "default" trong JAVA cho phép định nghĩa các phương thức mặc định trong interface, giúp tăng cường khả năng mở rộng và dễ dàng bảo trì mã nguồn.