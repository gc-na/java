<!--
Meta Description: # Câu lệnh "if" trong Java: Hướng dẫn chi tiết và ví dụ ## Tóm tắt Câu lệnh "if" trong Java là một cấu trúc điều kiện quan trọng, cho phép lập trình v...
Meta Keywords: điều, câu, lệnh, kiện, else
-->

# Câu lệnh "if" trong Java: Hướng dẫn chi tiết và ví dụ

## Tóm tắt
Câu lệnh "if" trong Java là một cấu trúc điều kiện quan trọng, cho phép lập trình viên thực hiện các đoạn mã khác nhau dựa trên điều kiện được đánh giá là đúng hay sai.

## Tài liệu
Câu lệnh "if" trong Java được sử dụng để thực hiện các quyết định trong mã nguồn. Cú pháp cơ bản của câu lệnh "if" như sau:

```java
if (điều_kiện) {
    // đoạn mã sẽ được thực thi nếu điều kiện đúng
}
```

### Mục đích
Mục đích chính của câu lệnh "if" là kiểm tra một điều kiện và quyết định xem có nên thực thi một khối mã hay không.

### Cách sử dụng
- **Cú pháp cơ bản**: Như đã nêu ở trên, câu lệnh "if" nhận một biểu thức điều kiện. Nếu biểu thức này trả về `true`, đoạn mã trong khối `{}` sẽ được thực thi.
- **Câu lệnh "if-else"**: Nếu bạn muốn thực hiện một đoạn mã khác khi điều kiện không đúng, bạn có thể sử dụng câu lệnh "if-else":

```java
if (điều_kiện) {
    // đoạn mã nếu điều kiện đúng
} else {
    // đoạn mã nếu điều kiện sai
}
```

- **Câu lệnh "if-else if-else"**: Để kiểm tra nhiều điều kiện, bạn có thể sử dụng cấu trúc này:

```java
if (điều_kiện_1) {
    // đoạn mã nếu điều kiện_1 đúng
} else if (điều_kiện_2) {
    // đoạn mã nếu điều kiện_2 đúng
} else {
    // đoạn mã nếu tất cả điều kiện trên sai
}
```

## Ví dụ
### Ví dụ 1: Câu lệnh "if" đơn giản
```java
int a = 10;
if (a > 5) {
    System.out.println("a lớn hơn 5");
}
```

### Ví dụ 2: Câu lệnh "if-else"
```java
int b = 4;
if (b % 2 == 0) {
    System.out.println("b là số chẵn");
} else {
    System.out.println("b là số lẻ");
}
```

### Ví dụ 3: Câu lệnh "if-else if-else"
```java
int điểm = 85;
if (điểm >= 90) {
    System.out.println("Xuất sắc");
} else if (điểm >= 75) {
    System.out.println("Khá");
} else {
    System.out.println("Cần cải thiện");
}
```

## Giải thích
Một số điều cần lưu ý khi sử dụng câu lệnh "if":
- **Biểu thức điều kiện**: Cần đảm bảo rằng biểu thức điều kiện đúng kiểu boolean. Nếu không, trình biên dịch sẽ báo lỗi.
- **Khối mã**: Nếu chỉ có một câu lệnh cần thực thi, bạn có thể bỏ qua dấu `{}`, nhưng điều này không được khuyến khích vì nó có thể gây nhầm lẫn.
- **Phép toán logic**: Bạn có thể kết hợp nhiều điều kiện với các phép toán logic như `&&` (và), `||` (hoặc) để tăng tính linh hoạt.

## Tóm tắt một dòng
Câu lệnh "if" trong Java cho phép lập trình viên thực hiện các quyết định dựa trên điều kiện, là một phần thiết yếu trong lập trình điều kiện.