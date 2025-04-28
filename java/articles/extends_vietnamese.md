<!--
Meta Description: # Từ Khóa "extends" trong JAVA: Khám Phá Tính Kế Thừa ## Tóm Tắt Từ khóa "extends" trong JAVA được sử dụng để khai báo mối quan hệ kế thừa giữa các lớ...
Meta Keywords: lớp, phương, thức, thừa, cho
-->

# Từ Khóa "extends" trong JAVA: Khám Phá Tính Kế Thừa

## Tóm Tắt
Từ khóa "extends" trong JAVA được sử dụng để khai báo mối quan hệ kế thừa giữa các lớp, cho phép một lớp (lớp con) thừa hưởng thuộc tính và phương thức từ một lớp khác (lớp cha).

## Tài Liệu
### Mục Đích
Từ khóa "extends" giúp lập trình viên xây dựng cấu trúc phân cấp cho các lớp trong JAVA, cho phép tái sử dụng mã nguồn và tổ chức mã theo cách hợp lý hơn.

### Cách Sử Dụng
Cú pháp của từ khóa "extends" được sử dụng trong khai báo lớp như sau:

```java
class TênLớpCon extends TênLớpCha {
    // Thuộc tính và phương thức của lớp con
}
```

Khi một lớp con kế thừa từ lớp cha, nó có thể sử dụng tất cả các phương thức và thuộc tính công khai (public) và bảo vệ (protected) của lớp cha. Lớp con cũng có thể ghi đè (override) các phương thức của lớp cha để thay đổi hành vi.

### Chi Tiết
- **Chỉ Một Lớp Cha:** Trong JAVA, một lớp chỉ có thể kế thừa từ một lớp cha duy nhất (kế thừa đơn), mặc dù nó có thể thực hiện nhiều giao diện.
- **Phương Thức Khởi Tạo:** Khi lớp con được tạo, phương thức khởi tạo của lớp cha sẽ được gọi trước.
- **Kế Thừa và Đối Tượng:** Lớp con sẽ có tất cả các thuộc tính và phương thức của lớp cha, cũng như có thể thêm các thuộc tính và phương thức mới.

## Ví Dụ
### Ví Dụ Cơ Bản
Dưới đây là một ví dụ đơn giản minh họa cách sử dụng từ khóa "extends":

```java
class DongVat {
    void keu() {
        System.out.println("Động vật phát ra tiếng kêu.");
    }
}

class Cho extends DongVat {
    void keu() {
        System.out.println("Chó sủa.");
    }
}

public class Main {
    public static void main(String[] args) {
        Cho cho = new Cho();
        cho.keu(); // Kết quả: Chó sủa.
    }
}
```

Trong ví dụ trên, lớp `Cho` kế thừa từ lớp `DongVat` và ghi đè phương thức `keu`.

## Giải Thích
### Những Lỗi Thường Gặp
- **Không thể kế thừa từ nhiều lớp:** JAVA không hỗ trợ kế thừa đa lớp, vì vậy bạn không thể sử dụng từ khóa "extends" cho nhiều lớp cùng lúc.
- **Thiếu phương thức khởi tạo:** Nếu bạn không gọi phương thức khởi tạo của lớp cha trong lớp con, có thể dẫn đến lỗi khi khởi tạo đối tượng.

### Ghi Đè Phương Thức
Khi ghi đè phương thức, bạn cần sử dụng từ khóa `@Override` để chỉ định rõ ràng rằng bạn đang ghi đè một phương thức từ lớp cha. Điều này giúp tăng cường tính rõ ràng và giảm thiểu lỗi:

```java
@Override
void keu() {
    System.out.println("Chó sủa.");
}
```

## Tóm Tắt Một Dòng
Từ khóa "extends" trong JAVA cho phép một lớp kế thừa thuộc tính và phương thức từ một lớp cha, thúc đẩy tính tái sử dụng mã và tổ chức cấu trúc lớp.