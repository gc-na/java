<!--
Meta Description: # Từ Khóa: "sealed" trong Java: Tính năng mới trong lập trình hướng đối tượng ## Tóm tắt Tính năng "sealed" trong Java cho phép lập trình viên kiểm so...
Meta Keywords: lớp, sealed, class, trong, các
-->

# Từ Khóa: "sealed" trong Java: Tính năng mới trong lập trình hướng đối tượng

## Tóm tắt
Tính năng "sealed" trong Java cho phép lập trình viên kiểm soát việc kế thừa các lớp, giúp xây dựng các cấu trúc lớp an toàn và dễ bảo trì hơn. Nó được giới thiệu trong Java 15 và là một phần của cải tiến lập trình hướng đối tượng.

## Tài liệu
Tính năng "sealed" trong Java cho phép bạn đánh dấu một lớp (class) hoặc giao diện (interface) là "sealed", nghĩa là chỉ những lớp hoặc giao diện con cụ thể mà bạn chỉ định mới có thể kế thừa nó. Điều này giúp hạn chế các lớp con được phép tạo ra, từ đó tối ưu hóa quá trình kiểm soát và bảo trì mã nguồn.

### Mục đích
Mục đích của sealed class là để giới hạn các lớp con, cho phép lập trình viên có thể kiểm soát tốt hơn cách mà các lớp con có thể được tạo ra và sử dụng trong ứng dụng.

### Cách sử dụng
Để khai báo một lớp hoặc giao diện là sealed, bạn cần sử dụng từ khóa `sealed` trước từ khóa `class` hoặc `interface`. Bạn cũng cần chỉ định các lớp con được phép kế thừa lớp sealed bằng cách sử dụng từ khóa `permits`.

```java
sealed class Animal permits Dog, Cat {
    // Nội dung lớp
}

final class Dog extends Animal {
    // Nội dung lớp Dog
}

final class Cat extends Animal {
    // Nội dung lớp Cat
}
```

Trong ví dụ trên, lớp `Animal` là một sealed class, chỉ cho phép các lớp `Dog` và `Cat` kế thừa.

## Ví dụ
```java
sealed class Shape permits Circle, Rectangle {
    // Nội dung lớp
}

final class Circle extends Shape {
    // Nội dung lớp Circle
}

final class Rectangle extends Shape {
    // Nội dung lớp Rectangle
}

class Main {
    public static void main(String[] args) {
        Shape shape1 = new Circle();
        Shape shape2 = new Rectangle();
    }
}
```

Trong ví dụ trên, lớp `Shape` chỉ có thể được kế thừa bởi các lớp `Circle` và `Rectangle`.

## Giải thích
Một số điểm cần lưu ý khi sử dụng sealed classes:
- Lớp sealed không thể được mở rộng bởi các lớp khác ngoài những lớp bạn đã chỉ định trong phần `permits`.
- Tất cả các lớp con của một sealed class phải được khai báo là `final`, `sealed`, hoặc `non-sealed`.
- Việc sử dụng sealed classes có thể làm giảm tính linh hoạt của mã nguồn, nhưng đồng thời cải thiện tính an toàn và khả năng bảo trì.

## Tóm tắt một dòng
Tính năng "sealed" trong Java cho phép lập trình viên kiểm soát việc kế thừa lớp, tạo ra cấu trúc lớp an toàn và dễ bảo trì hơn.