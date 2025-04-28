<!--
Meta Description: # Câu Lệnh "case" Trong Java: Hướng Dẫn Chi Tiết ## Tóm Tắt Câu lệnh `case` trong Java là một phần của cấu trúc điều khiển `switch`, cho phép lập trìn...
Meta Keywords: case, câu, giá, lệnh, không
-->

# Câu Lệnh "case" Trong Java: Hướng Dẫn Chi Tiết

## Tóm Tắt
Câu lệnh `case` trong Java là một phần của cấu trúc điều khiển `switch`, cho phép lập trình viên kiểm tra nhiều điều kiện khác nhau mà không cần phải sử dụng nhiều câu lệnh `if-else`.

## Tài Liệu
### Mục Đích
Câu lệnh `case` được sử dụng trong cấu trúc `switch` để kiểm tra giá trị của một biểu thức và thực thi một khối mã cụ thể dựa trên giá trị đó. Điều này giúp mã trở nên dễ đọc và quản lý hơn khi có nhiều giá trị cần kiểm tra.

### Cách Sử Dụng
Cấu trúc cơ bản của câu lệnh `switch` với các câu lệnh `case` như sau:

```java
switch (biểu_thức) {
    case giá_trị_1:
        // Khối mã thực thi khi biểu thức bằng giá trị_1
        break;
    case giá_trị_2:
        // Khối mã thực thi khi biểu thức bằng giá trị_2
        break;
    // Có thể có nhiều case khác
    default:
        // Khối mã thực thi khi không khớp với bất kỳ case nào
}
```

- **biểu_thức**: Là một giá trị kiểu nguyên (int, char) hoặc một chuỗi (String) được kiểm tra.
- **giá_trị_n**: Là các giá trị mà biểu thức có thể khớp với.
- **break**: Dùng để thoát khỏi cấu trúc `switch`, ngăn không cho thực thi các case tiếp theo.
- **default**: Tùy chọn để xử lý trường hợp không khớp với bất kỳ case nào.

### Chi Tiết
- Câu lệnh `case` có thể kiểm tra các giá trị nguyên, ký tự, và chuỗi, nhưng không thể kiểm tra các giá trị kiểu boolean.
- Các giá trị trong các câu lệnh `case` phải là hằng số (constant) và duy nhất.
- Nếu không sử dụng `break`, chương trình sẽ tiếp tục thực thi các câu lệnh trong các case tiếp theo cho đến khi gặp `break` hoặc kết thúc cấu trúc `switch`.

## Ví Dụ
### Ví Dụ 1: Sử Dụng với Kiểu Nguyên
```java
int day = 3;
switch (day) {
    case 1:
        System.out.println("Thứ Hai");
        break;
    case 2:
        System.out.println("Thứ Ba");
        break;
    case 3:
        System.out.println("Thứ Tư");
        break;
    default:
        System.out.println("Ngày không hợp lệ");
}
```

### Ví Dụ 2: Sử Dụng với Chuỗi
```java
String fruit = "Táo";
switch (fruit) {
    case "Chuối":
        System.out.println("Bạn chọn chuối.");
        break;
    case "Táo":
        System.out.println("Bạn chọn táo.");
        break;
    default:
        System.out.println("Trái cây không hợp lệ.");
}
```

## Giải Thích
- Một số lỗi thường gặp khi sử dụng `case` bao gồm việc quên thêm `break`, dẫn đến việc thực thi nhiều case không mong muốn (hay còn gọi là "fall-through").
- Cấu trúc `switch` không thể xử lý các giá trị kiểu boolean và không hỗ trợ các phép so sánh phức tạp như `>`, `<`, v.v.
- Khi cần kiểm tra nhiều điều kiện phức tạp, có thể nên sử dụng câu lệnh `if-else` thay vì `switch-case`.

## Tóm Tắt Một Câu
Câu lệnh `case` trong Java cung cấp cách thức đơn giản và hiệu quả để kiểm tra và xử lý nhiều giá trị khác nhau trong một biểu thức.