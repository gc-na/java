<!--
Meta Description: # Lệnh "continue" trong JAVA: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể ## Tóm tắt Lệnh "continue" trong JAVA được sử dụng trong các vòng lặp để bỏ qua phần ...
Meta Keywords: lặp, vòng, continue, trong, lệnh
-->

# Lệnh "continue" trong JAVA: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể

## Tóm tắt
Lệnh "continue" trong JAVA được sử dụng trong các vòng lặp để bỏ qua phần còn lại của vòng lặp hiện tại và tiếp tục với vòng lặp tiếp theo. Điều này rất hữu ích khi bạn cần kiểm tra một điều kiện và muốn bỏ qua một số bước trong vòng lặp nếu điều kiện đó không được thỏa mãn.

## Tài liệu
Lệnh "continue" có thể được sử dụng trong các vòng lặp như `for`, `while`, và `do-while`. Khi gặp lệnh "continue", chương trình sẽ không thực hiện các câu lệnh còn lại trong vòng lặp và sẽ quay lại điều kiện của vòng lặp để kiểm tra lại.

### Mục đích
- Đơn giản hóa mã nguồn bằng cách cho phép bỏ qua các bước không cần thiết trong một vòng lặp.
- Giúp kiểm soát luồng thực thi của chương trình một cách dễ dàng hơn.

### Cách sử dụng
Lệnh "continue" có thể được sử dụng như sau:

```java
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        continue; // Bỏ qua các số chẵn
    }
    System.out.println(i); // Chỉ in ra các số lẻ
}
```

Trong ví dụ trên, nếu `i` là số chẵn, lệnh "continue" sẽ bỏ qua câu lệnh `System.out.println(i)` và quay lại kiểm tra điều kiện của vòng lặp.

## Ví dụ
### Ví dụ 1: Sử dụng lệnh "continue" trong vòng lặp for
```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i % 3 == 0) {
                continue; // Bỏ qua các số chia hết cho 3
            }
            System.out.println(i);
        }
    }
}
```
Kết quả: `1, 2, 4, 5, 7, 8, 10`

### Ví dụ 2: Sử dụng lệnh "continue" trong vòng lặp while
```java
public class Main {
    public static void main(String[] args) {
        int i = 0;
        while (i < 10) {
            i++;
            if (i % 2 == 0) {
                continue; // Bỏ qua các số chẵn
            }
            System.out.println(i); // In ra các số lẻ
        }
    }
}
```
Kết quả: `1, 3, 5, 7, 9`

## Giải thích
- **Những điều cần lưu ý**: Khi sử dụng lệnh "continue", cần chú ý rằng nó chỉ ảnh hưởng đến vòng lặp hiện tại mà nó nằm trong đó. Nếu có nhiều vòng lặp lồng nhau, "continue" sẽ chỉ bỏ qua phần còn lại của vòng lặp gần nhất.
- **Tránh sử dụng lặp vô hạn**: Đảm bảo rằng điều kiện trong vòng lặp sẽ được thay đổi, nếu không, bạn có thể gặp phải tình trạng lặp vô hạn.

## Tóm tắt một dòng
Lệnh "continue" trong JAVA cho phép bỏ qua phần còn lại của vòng lặp hiện tại và tiếp tục với vòng lặp tiếp theo, giúp kiểm soát luồng thực thi hiệu quả hơn.