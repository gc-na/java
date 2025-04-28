<!--
Meta Description: # Câu lệnh "while" trong JAVA: Cách sử dụng và ví dụ ## Tóm tắt Câu lệnh "while" trong JAVA là một cấu trúc lặp cho phép thực hiện một khối mã lặp đi ...
Meta Keywords: điều, lặp, kiện, trong, khi
-->

# Câu lệnh "while" trong JAVA: Cách sử dụng và ví dụ

## Tóm tắt
Câu lệnh "while" trong JAVA là một cấu trúc lặp cho phép thực hiện một khối mã lặp đi lặp lại cho đến khi điều kiện được chỉ định không còn đúng.

## Tài liệu
Câu lệnh "while" trong JAVA được sử dụng để lặp thực hiện một khối mã bao gồm các lệnh khác nhau cho đến khi điều kiện trong biểu thức điều kiện trở thành sai. Cấu trúc cơ bản của cú pháp "while" như sau:

```java
while (điều kiện) {
    // mã lệnh thực thi
}
```

### Mục đích
Mục đích của câu lệnh "while" là để lặp lại một khối lệnh cho đến khi điều kiện xác định không còn đúng. Điều này rất hữu ích trong các tình huống khi số lần lặp không được biết trước, chẳng hạn như khi đọc dữ liệu từ một nguồn bên ngoài hoặc khi thực hiện các phép toán cho đến khi đạt được một kết quả nhất định.

### Cách sử dụng
1. **Khởi tạo biến điều kiện**: Trước khi vào vòng lặp, bạn cần khởi tạo các biến cần thiết cho điều kiện.
2. **Kiểm tra điều kiện**: Khi vòng lặp bắt đầu, điều kiện sẽ được kiểm tra. Nếu đúng, khối mã bên trong sẽ được thực thi.
3. **Cập nhật điều kiện**: Sau khi khối mã thực thi, cần có cách để cập nhật hoặc thay đổi điều kiện. Nếu không, vòng lặp sẽ trở thành vòng lặp vô hạn (infinite loop).

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng câu lệnh "while" trong JAVA.

### Ví dụ 1: Lặp qua số nguyên
```java
int i = 0;
while (i < 5) {
    System.out.println("Giá trị của i: " + i);
    i++;
}
```
*Output:*
```
Giá trị của i: 0
Giá trị của i: 1
Giá trị của i: 2
Giá trị của i: 3
Giá trị của i: 4
```

### Ví dụ 2: Tính tổng các số từ 1 đến n
```java
int n = 10; // tổng đến 10
int sum = 0;
int i = 1;

while (i <= n) {
    sum += i;
    i++;
}
System.out.println("Tổng từ 1 đến " + n + " là: " + sum);
```
*Output:*
```
Tổng từ 1 đến 10 là: 55
```

## Giải thích
### Những cạm bẫy thường gặp
- **Vòng lặp vô hạn**: Một trong những lỗi phổ biến nhất là không cập nhật điều kiện trong vòng lặp, dẫn đến vòng lặp vô hạn. Đảm bảo rằng điều kiện sẽ trở thành sai trong quá trình thực thi.
- **Kiểm tra điều kiện lần đầu**: Luôn luôn kiểm tra điều kiện trước khi vào vòng lặp để đảm bảo rằng ít nhất một lần thực thi nếu điều kiện là sai từ đầu.
- **Sử dụng đúng kiểu dữ liệu**: Đảm bảo rằng bạn đang sử dụng kiểu dữ liệu phù hợp cho điều kiện và các biến lặp để tránh lỗi trong quá trình thực thi.

## Tóm tắt một dòng
Câu lệnh "while" trong JAVA cho phép thực hiện một khối mã lặp đi lặp lại cho đến khi điều kiện chỉ định trở thành sai.