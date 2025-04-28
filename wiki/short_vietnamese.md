<!--
Meta Description: # Tìm Hiểu về Kiểu Dữ Liệu "short" trong Java ## Tóm Tắt Trong ngôn ngữ lập trình Java, `short` là một kiểu dữ liệu nguyên thủy dùng để lưu trữ các số...
Meta Keywords: short, kiểu, dụng, trong, các
-->

# Tìm Hiểu về Kiểu Dữ Liệu "short" trong Java

## Tóm Tắt
Trong ngôn ngữ lập trình Java, `short` là một kiểu dữ liệu nguyên thủy dùng để lưu trữ các số nguyên nhỏ. Nó chiếm 2 byte bộ nhớ và có thể lưu trữ giá trị từ -32,768 đến 32,767. Kiểu dữ liệu này thường được sử dụng để tiết kiệm bộ nhớ trong các ứng dụng cần lưu trữ nhiều giá trị số nguyên nhỏ.

## Tài Liệu
### Mục Đích
Kiểu `short` trong Java được thiết kế để tiết kiệm bộ nhớ hơn so với các kiểu dữ liệu số nguyên khác như `int` hoặc `long`. Nó phù hợp cho các ứng dụng mà yêu cầu lưu trữ số lượng lớn các giá trị nhỏ mà không cần sử dụng đến bộ nhớ quá nhiều.

### Cách Sử Dụng
Để khai báo một biến kiểu `short`, bạn sử dụng cú pháp sau:
```java
short tenBien;
```
Bạn có thể gán giá trị cho biến `short` như sau:
```java
short a = 100;
```

### Chi Tiết
- **Kích thước**: 2 byte (16 bit)
- **Giá trị tối thiểu**: -32,768
- **Giá trị tối đa**: 32,767
- **Phạm vi sử dụng**: Thường được sử dụng trong các ứng dụng nhúng hoặc các chương trình cần tối ưu hóa bộ nhớ.

## Ví Dụ
Dưới đây là một số ví dụ đơn giản về việc sử dụng kiểu `short` trong Java:

### Ví Dụ 1: Khai báo và khởi tạo biến `short`
```java
public class Main {
    public static void main(String[] args) {
        short a = 10;
        short b = 20;
        short tong = (short) (a + b); // Ép kiểu khi cộng
        System.out.println("Tổng: " + tong);
    }
}
```

### Ví Dụ 2: Sử dụng `short` trong vòng lặp
```java
public class Main {
    public static void main(String[] args) {
        for (short i = 1; i <= 5; i++) {
            System.out.println("Giá trị i: " + i);
        }
    }
}
```

## Giải Thích
Khi sử dụng kiểu `short`, có một số điều cần lưu ý:
- **Ép kiểu**: Khi thực hiện các phép toán, kết quả sẽ tự động được nâng lên kiểu `int`. Nếu bạn cần lưu trữ kết quả vào một biến `short`, bạn cần ép kiểu như trong ví dụ trên.
- **Phạm vi giá trị**: Đảm bảo rằng giá trị bạn gán cho biến `short` nằm trong phạm vi cho phép; nếu không, sẽ xảy ra lỗi biên giới (overflow).
- **Tính tương thích**: Kiểu `short` không thể được sử dụng trực tiếp trong các phép toán với các kiểu dữ liệu khác mà không có sự ép kiểu thích hợp.

## Tóm Tắt Một Dòng
Kiểu dữ liệu `short` trong Java là một kiểu số nguyên 16 bit, phù hợp để lưu trữ các giá trị nhỏ và tiết kiệm bộ nhớ.