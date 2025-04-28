<!--
Meta Description: # Non-Sealed trong Java: Tính Năng Mới Của Lập Trình Hướng Đối Tượng ## Tóm Tắt Từ khóa "non-sealed" trong Java được giới thiệu từ phiên bản Java 17, ...
Meta Keywords: lớp, sealed, non, trong, con
-->

# Non-Sealed trong Java: Tính Năng Mới Của Lập Trình Hướng Đối Tượng

## Tóm Tắt
Từ khóa "non-sealed" trong Java được giới thiệu từ phiên bản Java 17, cho phép các lớp con của một lớp sealed có thể được kế thừa mà không bị giới hạn, tạo ra sự linh hoạt trong việc mở rộng các lớp.

## Tài Liệu
### Mục Đích
"non-sealed" được sử dụng để chỉ định rằng một lớp con của một lớp sealed có thể được kế thừa tự do. Điều này rất hữu ích trong các tình huống mà bạn muốn cho phép một lớp mở rộng mà không cần phải giới hạn số lượng lớp con.

### Cách Sử Dụng
Khi bạn định nghĩa một lớp con của một lớp sealed, bạn có thể sử dụng từ khóa "non-sealed" để chỉ định rằng lớp con này không bị giới hạn trong việc kế thừa. Cú pháp sử dụng như sau:

```java
sealed class Shape permits Circle, Rectangle {
    // ...
}

non-sealed class Circle extends Shape {
    // ...
}

non-sealed class Rectangle extends Shape {
    // ...
}
```

Trong ví dụ trên, cả lớp `Circle` và `Rectangle` đều là các lớp con không bị giới hạn, cho phép chúng có thể được mở rộng thêm bởi các lớp khác.

### Chi Tiết
- **Lớp sealed**: Là lớp mà chỉ định những lớp nào có thể kế thừa nó.
- **Lớp non-sealed**: Là lớp con không bị giới hạn trong việc kế thừa, nghĩa là bạn có thể tạo ra nhiều lớp con hơn từ lớp này.
- **Cú pháp**: Để định nghĩa một lớp là non-sealed, bạn chỉ cần thêm từ khóa "non-sealed" trước từ khóa "class".

## Ví Dụ
Dưới đây là một ví dụ ngắn gọn về cách sử dụng "non-sealed":

```java
sealed class Animal permits Dog, Cat {
    // ...
}

non-sealed class Dog extends Animal {
    // ...
}

class Labrador extends Dog {
    // ...
}

non-sealed class Cat extends Animal {
    // ...
}

class Persian extends Cat {
    // ...
}
```

Trong ví dụ này, lớp `Dog` và lớp `Cat` không bị giới hạn và có thể có thêm các lớp con như `Labrador` và `Persian`.

## Giải Thích
- **Cạm bẫy phổ biến**: Một số lập trình viên có thể nhầm lẫn giữa sealed và non-sealed. Đảm bảo rằng bạn hiểu rõ sự khác biệt giữa chúng.
- **Lợi ích**: Bằng cách sử dụng non-sealed, bạn có thể linh hoạt hơn trong việc thiết kế các hệ thống phức tạp mà không cần lo lắng về việc hạn chế lớp con.

## Tóm Tắt Một Dòng
Từ khóa "non-sealed" trong Java cho phép các lớp con của lớp sealed được mở rộng tự do, tạo ra sự linh hoạt trong thiết kế phần mềm.