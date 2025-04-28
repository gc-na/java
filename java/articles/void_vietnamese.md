<!--
Meta Description: # Từ Khóa "void" trong Java: Hiểu Rõ Khái Niệm và Cách Sử Dụng ## Tóm tắt Trong ngôn ngữ lập trình Java, từ khóa "void" được sử dụng để chỉ định rằng ...
Meta Keywords: phương, thức, void, một, giá
-->

# Từ Khóa "void" trong Java: Hiểu Rõ Khái Niệm và Cách Sử Dụng

## Tóm tắt
Trong ngôn ngữ lập trình Java, từ khóa "void" được sử dụng để chỉ định rằng một phương thức không trả về giá trị nào. Đây là một phần quan trọng trong việc định nghĩa các phương thức trong Java, giúp lập trình viên xác định rõ ràng mục đích và chức năng của phương thức.

## Tài liệu
### Mục đích
Từ khóa "void" được sử dụng để định nghĩa phương thức không trả về giá trị. Khi một phương thức được khai báo với từ khóa "void", nó thực hiện các thao tác, nhưng không trả về bất kỳ giá trị nào cho nơi gọi phương thức đó.

### Cách Sử Dụng
Khi bạn muốn tạo một phương thức mà không cần trả về giá trị, bạn sẽ sử dụng từ khóa "void" trong phần định nghĩa phương thức. Cú pháp chung như sau:

```java
void tenPhuongThuc() {
    // Thực hiện các thao tác
}
```

### Chi Tiết
- **Phương thức void**: Một phương thức khai báo với từ khóa "void" có thể thực hiện một loạt các thao tác, như in ra màn hình, thay đổi giá trị của biến toàn cục, hoặc thực hiện một số tính toán mà không cần phải trả về kết quả.
- **Không có giá trị trả về**: Nếu bạn cố gắng trả về một giá trị từ một phương thức void, trình biên dịch sẽ báo lỗi. Ví dụ: `return 5;` trong một phương thức void sẽ gây lỗi.

## Ví dụ
Dưới đây là một số ví dụ đơn giản về cách sử dụng từ khóa "void" trong Java:

### Ví dụ 1: Phương thức in ra thông báo
```java
public class ThongDiep {
    void hienThiThongDiep() {
        System.out.println("Chào mừng bạn đến với Java!");
    }

    public static void main(String[] args) {
        ThongDiep td = new ThongDiep();
        td.hienThiThongDiep();
    }
}
```

### Ví dụ 2: Phương thức thay đổi giá trị biến
```java
public class Bien {
    int giaTri = 0;

    void thayDoiGiaTri(int giaTriMoi) {
        giaTri = giaTriMoi;
    }

    public static void main(String[] args) {
        Bien b = new Bien();
        b.thayDoiGiaTri(10);
        System.out.println(b.giaTri); // Kết quả: 10
    }
}
```

## Giải Thích
- **Cảnh báo về việc trả giá trị**: Một số lập trình viên mới có thể nhầm lẫn và cố gắng trả về giá trị từ một phương thức void, điều này sẽ dẫn đến lỗi biên dịch. Hãy nhớ rằng nếu phương thức của bạn được khai báo với từ khóa "void", bạn không thể sử dụng từ khóa `return` với một giá trị.
- **Tính linh hoạt**: Phương thức void rất hữu ích trong nhiều tình huống, đặc biệt là khi bạn chỉ cần thực hiện một số tác vụ mà không cần phải trả về kết quả cho người gọi phương thức.

## Tóm Tắt Một Dòng
Từ khóa "void" trong Java được sử dụng để định nghĩa các phương thức không trả về giá trị, giúp lập trình viên xác định rõ ràng mục đích và chức năng của phương thức trong chương trình.