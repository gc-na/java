<!--
Meta Description: # Kiểu Dữ Liệu char trong Java: Hiểu Biết Cần Thiết cho Lập Trình Viên ## Tóm Tắt Trong Java, `char` là một kiểu dữ liệu nguyên thủy dùng để lưu trữ k...
Meta Keywords: char, kiểu, dụng, java, một
-->

# Kiểu Dữ Liệu char trong Java: Hiểu Biết Cần Thiết cho Lập Trình Viên

## Tóm Tắt
Trong Java, `char` là một kiểu dữ liệu nguyên thủy dùng để lưu trữ ký tự. Mỗi giá trị kiểu `char` là một ký tự Unicode, cho phép lập trình viên làm việc với các ký tự từ nhiều ngôn ngữ khác nhau.

## Tài Liệu
### Mục Đích
Kiểu dữ liệu `char` được sử dụng để lưu trữ một ký tự duy nhất. Trong Java, `char` là một kiểu dữ liệu 16-bit, có thể lưu trữ các ký tự từ bảng mã Unicode, cho phép hỗ trợ nhiều ngôn ngữ và ký tự đặc biệt.

### Cách Sử Dụng
Để khai báo một biến kiểu `char`, bạn có thể sử dụng cú pháp sau:
```java
char myChar = 'A';
```
Khi khai báo `char`, bạn phải đặt ký tự trong dấu nháy đơn. Các ký tự có thể là chữ cái, số, hoặc ký tự đặc biệt.

### Chi Tiết
- **Phạm vi:** Kiểu `char` có thể lưu trữ các giá trị từ `'\u0000'` (0) đến `'\uffff'` (65,535).
- **Tạo ký tự từ mã Unicode:** Bạn có thể sử dụng cú pháp sau để tạo ký tự từ mã Unicode:
```java
char unicodeChar = '\u03A9'; // Ký tự Omega (Ω)
```
- **Chuyển đổi giữa char và int:** Bạn có thể dễ dàng chuyển đổi giữa `char` và `int` bằng cách sử dụng phép toán:
```java
char letter = 'A';
int asciiValue = letter; // asciiValue sẽ có giá trị 65
```

## Ví Dụ
```java
public class CharExample {
    public static void main(String[] args) {
        // Khai báo biến kiểu char
        char letter = 'J';
        char number = '5';
        
        // In ra giá trị của biến
        System.out.println("Ký tự: " + letter);
        System.out.println("Ký tự số: " + number);
        
        // Tạo ký tự từ mã Unicode
        char omega = '\u03A9';
        System.out.println("Ký tự Omega: " + omega);
    }
}
```

## Giải Thích
- **Chú Ý:** Khi sử dụng kiểu `char`, cần lưu ý rằng `char` không phải là chuỗi. Nếu bạn muốn làm việc với nhiều ký tự, hãy sử dụng kiểu `String` thay vì `char`.
- **Ký Tự Đặc Biệt:** Đối với các ký tự đặc biệt như dấu nháy đơn hay dấu nháy đôi, bạn cần sử dụng dấu gạch chéo ngược (`\`) để thoát ký tự.
- **Lỗi Phổ Biến:** Một số lập trình viên mới có thể nhầm lẫn giữa ký tự và chuỗi, dẫn đến lỗi biên dịch. Đảm bảo sử dụng dấu nháy đơn cho `char` và dấu nháy đôi cho `String`.

## Tóm Tắt Một Dòng
Kiểu dữ liệu `char` trong Java cho phép lưu trữ và xử lý các ký tự đơn, hỗ trợ đầy đủ các ký tự Unicode.