<!--
Meta Description: # Tìm Hiểu Kiểu Dữ Liệu "int" Trong Java ## Tóm tắt Kiểu dữ liệu "int" trong Java là một trong những kiểu dữ liệu nguyên thủy được sử dụng để lưu trữ ...
Meta Keywords: int, kiểu, trong, các, java
-->

# Tìm Hiểu Kiểu Dữ Liệu "int" Trong Java

## Tóm tắt
Kiểu dữ liệu "int" trong Java là một trong những kiểu dữ liệu nguyên thủy được sử dụng để lưu trữ các giá trị số nguyên, có khả năng biểu diễn các số trong khoảng từ -2,147,483,648 đến 2,147,483,647.

## Tài liệu
### Mục đích
Kiểu dữ liệu "int" là một phần quan trọng trong ngôn ngữ lập trình Java, cho phép lập trình viên lưu trữ và thao tác với các số nguyên trong các chương trình của họ. Nó chiếm 4 byte bộ nhớ và được sử dụng rộng rãi trong các phép toán số học, điều kiện và vòng lặp.

### Cách sử dụng
Để khai báo một biến kiểu "int", bạn có thể sử dụng cú pháp sau:

```java
int tenBien;
```

Bạn có thể gán giá trị cho biến này như sau:

```java
tenBien = 10;
```

Hoặc bạn có thể khai báo và gán giá trị cùng một lúc:

```java
int tenBien = 10;
```

### Chi tiết
- **Khoảng giá trị**: Kiểu "int" có thể lưu trữ các giá trị trong khoảng từ -2,147,483,648 đến 2,147,483,647.
- **Phép toán**: Bạn có thể thực hiện các phép toán như cộng, trừ, nhân, chia với các biến kiểu "int".
- **Tự động ép kiểu**: Khi thực hiện phép toán với các kiểu dữ liệu khác (như "double" hay "float"), Java sẽ tự động ép kiểu về một trong các kiểu dữ liệu để thực hiện phép toán.

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng kiểu dữ liệu "int":

```java
public class Main {
    public static void main(String[] args) {
        int a = 5;
        int b = 10;
        int tong = a + b;
        
        System.out.println("Tổng của a và b là: " + tong);
    }
}
```

Kết quả sẽ là: `Tổng của a và b là: 15`.

```java
public class Main {
    public static void main(String[] args) {
        int x = 20;
        int y = 3;
        int chia = x / y;
        
        System.out.println("Kết quả phép chia x/y là: " + chia);
    }
}
```

Kết quả sẽ là: `Kết quả phép chia x/y là: 6`. (Lưu ý rằng phép chia giữa hai số nguyên sẽ làm tròn xuống).

## Giải thích
- **Cảnh báo**: Khi thực hiện phép chia giữa hai số nguyên, kết quả sẽ là một số nguyên, nghĩa là phần thập phân sẽ bị bỏ qua. Điều này có thể gây nhầm lẫn nếu bạn không chú ý.
- **Tràn số**: Nếu bạn cố gắng gán một giá trị vượt quá khoảng giá trị của "int", sẽ xảy ra hiện tượng tràn số (overflow), dẫn đến kết quả không mong muốn.
- **Khi nào nên dùng**: Sử dụng kiểu "int" khi bạn cần lưu trữ các giá trị nguyên mà không cần phần thập phân, và khi giá trị đó nằm trong giới hạn của kiểu "int".

## Tóm tắt một dòng
Kiểu dữ liệu "int" trong Java cho phép lưu trữ các số nguyên trong khoảng -2,147,483,648 đến 2,147,483,647, là một phần thiết yếu trong lập trình Java.