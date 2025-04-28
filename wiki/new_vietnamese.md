<!--
Meta Description: # Từ Khóa "new" trong JAVA: Khởi Tạo Đối Tượng ## Tóm Tắt Từ khóa "new" trong JAVA được sử dụng để tạo ra các đối tượng mới từ các lớp đã định nghĩa. ...
Meta Keywords: tạo, đối, tượng, khởi, new
-->

# Từ Khóa "new" trong JAVA: Khởi Tạo Đối Tượng

## Tóm Tắt
Từ khóa "new" trong JAVA được sử dụng để tạo ra các đối tượng mới từ các lớp đã định nghĩa. Đây là một phần quan trọng trong lập trình hướng đối tượng, giúp lập trình viên khởi tạo và quản lý bộ nhớ cho các đối tượng.

## Tài Liệu
### Mục Đích
Từ khóa "new" cho phép lập trình viên khởi tạo một đối tượng mới từ một lớp cụ thể. Khi bạn sử dụng từ khóa này, JAVA sẽ cấp phát bộ nhớ cho đối tượng và gọi hàm khởi tạo để thiết lập trạng thái ban đầu của đối tượng.

### Cú Pháp
Cú pháp để sử dụng từ khóa "new" trong JAVA như sau:
```java
ClassName objectName = new ClassName();
```
Trong đó:
- `ClassName`: Tên của lớp mà bạn muốn tạo đối tượng.
- `objectName`: Tên biến mà bạn sẽ sử dụng để tham chiếu tới đối tượng mới tạo.

### Chi Tiết
Khi bạn sử dụng từ khóa "new", JAVA thực hiện các bước sau:
1. Cấp phát bộ nhớ cho đối tượng.
2. Gọi hàm khởi tạo (constructor) của lớp để thiết lập các thuộc tính của đối tượng.
3. Trả về tham chiếu tới đối tượng mới tạo.

Từ khóa "new" có thể được sử dụng để tạo ra các đối tượng từ bất kỳ lớp nào, bao gồm cả các lớp do người dùng định nghĩa và các lớp có sẵn trong thư viện JAVA.

## Ví Dụ
### Ví Dụ Cơ Bản
```java
class Dog {
    String name;

    Dog(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Buddy");
        System.out.println("Tên chó của tôi là: " + myDog.name);
    }
}
```
Trong ví dụ trên, chúng ta đã sử dụng từ khóa "new" để khởi tạo đối tượng `Dog` với tên "Buddy".

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Không gọi hàm khởi tạo**: Nếu bạn không định nghĩa hàm khởi tạo trong lớp, JAVA sẽ tự động tạo một hàm khởi tạo mặc định. Tuy nhiên, nếu bạn định nghĩa một hàm khởi tạo có tham số mà không định nghĩa hàm khởi tạo không tham số, bạn sẽ gặp lỗi khi cố gắng tạo đối tượng mà không cung cấp tham số.
- **Bộ nhớ không được giải phóng**: Đối tượng được tạo ra bằng từ khóa "new" sẽ chiếm dụng bộ nhớ cho đến khi không còn tham chiếu tới nó và được Garbage Collector thu hồi. Do đó, việc quản lý bộ nhớ là rất quan trọng trong JAVA.

## Tóm Tắt Một Dòng
Từ khóa "new" trong JAVA cho phép lập trình viên khởi tạo và quản lý các đối tượng mới từ các lớp đã định nghĩa, là một phần thiết yếu trong lập trình hướng đối tượng.