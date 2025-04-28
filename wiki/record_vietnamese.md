<!--
Meta Description: # Từ Khóa: "Record trong Java: Định Nghĩa, Cách Sử Dụng và Ví Dụ" ## Tóm Tắt Record trong Java là một tính năng mới được giới thiệu từ phiên bản Java ...
Meta Keywords: record, các, java, lớp, không
-->

# Từ Khóa: "Record trong Java: Định Nghĩa, Cách Sử Dụng và Ví Dụ"

## Tóm Tắt
Record trong Java là một tính năng mới được giới thiệu từ phiên bản Java 14, cho phép lập trình viên dễ dàng định nghĩa các lớp không thay đổi (immutable) với cú pháp ngắn gọn và rõ ràng.

## Tài Liệu

### Mục Đích
Record trong Java được thiết kế để đơn giản hóa quá trình tạo ra các lớp dữ liệu, mà không cần phải viết nhiều mã lặp lại. Chúng giúp lập trình viên dễ dàng tạo ra các đối tượng chứa dữ liệu mà không cần phải điều chỉnh các phương thức như getter, equals, hashCode và toString.

### Cách Sử Dụng
Để định nghĩa một record, bạn sử dụng từ khóa `record` theo cú pháp sau:

```java
record TênRecord(TênKiểuTênTrường tênTrường1, TênKiểuTênTrường tênTrường2) {}
```

Khi bạn định nghĩa một record, Java sẽ tự động tạo các phương thức cần thiết như:
- Các phương thức getter cho từng trường.
- Phương thức `equals()` để so sánh các đối tượng.
- Phương thức `hashCode()` để tạo mã băm cho đối tượng.
- Phương thức `toString()` để biểu diễn đối tượng dưới dạng chuỗi.

### Chi Tiết
Record không thể kế thừa từ lớp khác và không thể là lớp cha của các lớp khác. Chúng luôn là lớp con của `java.lang.Record`. Các trường trong record mặc định là `final`, có nghĩa là giá trị của chúng không thể thay đổi sau khi được khởi tạo.

### Ví Dụ
Dưới đây là một ví dụ đơn giản về cách định nghĩa và sử dụng record trong Java:

```java
// Định nghĩa record
record SinhVien(String ten, int tuoi) {}

public class Main {
    public static void main(String[] args) {
        // Tạo đối tượng record
        SinhVien sv = new SinhVien("Nguyen Van A", 20);
        
        // Sử dụng phương thức getter
        System.out.println("Tên: " + sv.ten());
        System.out.println("Tuổi: " + sv.tuoi());
        
        // In ra thông tin của đối tượng
        System.out.println(sv);
    }
}
```

### Giải Thích
- **Common Pitfalls**: Một số lập trình viên có thể nhầm lẫn rằng record có thể thay đổi các giá trị của trường. Tuy nhiên, do bản chất `final`, các trường trong record không thể thay đổi sau khi được khởi tạo.
- **Gotchas**: Khi bạn định nghĩa record, hãy nhớ rằng nó không hỗ trợ kế thừa. Nếu bạn cần kế thừa tính năng từ một lớp khác, bạn sẽ cần sử dụng các lớp thông thường.
- **Ghi chú bổ sung**: Record rất hữu ích cho việc truyền dữ liệu giữa các lớp hoặc khi làm việc với các API mà bạn không cần thay đổi giá trị sau khi tạo.

## Tóm Tắt Một Dòng
Record trong Java là một cách đơn giản và hiệu quả để định nghĩa các lớp chứa dữ liệu mà không cần phải viết quá nhiều mã lặp lại.