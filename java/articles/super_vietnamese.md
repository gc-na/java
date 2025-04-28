<!--
Meta Description: # Từ Khóa "super" trong Java: Tính Năng Quan Trọng và Cách Sử Dụng ## Tóm tắt Từ khóa "super" trong Java được sử dụng để tham chiếu đến lớp cha của mộ...
Meta Keywords: lớp, cha, của, child, super
-->

# Từ Khóa "super" trong Java: Tính Năng Quan Trọng và Cách Sử Dụng

## Tóm tắt
Từ khóa "super" trong Java được sử dụng để tham chiếu đến lớp cha của một lớp hiện tại, cho phép truy cập các thuộc tính và phương thức của lớp cha.

## Tài Liệu
Trong lập trình hướng đối tượng, Java cho phép một lớp kế thừa từ một lớp khác. Từ khóa "super" được sử dụng để làm rõ ràng rằng bạn đang tham chiếu đến lớp cha. Nó có thể được sử dụng để:

1. **Gọi phương thức của lớp cha**: Khi lớp con ghi đè một phương thức của lớp cha, bạn có thể sử dụng "super" để gọi phương thức của lớp cha.
2. **Truy cập thuộc tính của lớp cha**: Bạn có thể sử dụng "super" để truy cập các thuộc tính không bị ghi đè trong lớp cha.
3. **Gọi constructor của lớp cha**: Khi tạo đối tượng của lớp con, bạn có thể sử dụng "super()" để gọi constructor của lớp cha.

### Cú Pháp
```java
super(); // Gọi constructor của lớp cha
super.methodName(); // Gọi phương thức của lớp cha
super.attributeName; // Truy cập thuộc tính của lớp cha
```

## Ví Dụ
### 1. Gọi phương thức của lớp cha
```java
class Parent {
    void display() {
        System.out.println("This is the Parent class");
    }
}

class Child extends Parent {
    void display() {
        super.display(); // Gọi phương thức display của lớp cha
        System.out.println("This is the Child class");
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.display();
    }
}
```

### 2. Truy cập thuộc tính của lớp cha
```java
class Parent {
    String name = "Parent Name";
}

class Child extends Parent {
    String name = "Child Name";

    void displayNames() {
        System.out.println("Child Name: " + name);
        System.out.println("Parent Name: " + super.name); // Truy cập thuộc tính của lớp cha
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.displayNames();
    }
}
```

### 3. Gọi constructor của lớp cha
```java
class Parent {
    Parent() {
        System.out.println("Constructor of Parent class");
    }
}

class Child extends Parent {
    Child() {
        super(); // Gọi constructor của lớp cha
        System.out.println("Constructor of Child class");
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child();
    }
}
```

## Giải Thích
Khi sử dụng từ khóa "super", hãy lưu ý các điểm sau:

- **Chỉ có thể sử dụng "super" trong lớp con**: "super" không thể được sử dụng trong lớp cha.
- **Gọi constructor của lớp cha phải là dòng đầu tiên trong constructor của lớp con**: Nếu không, bạn sẽ nhận được lỗi biên dịch.
- **Không thể sử dụng "super" để truy cập thuộc tính hoặc phương thức private của lớp cha**: Chỉ những thuộc tính và phương thức được công khai hoặc bảo vệ mới có thể được truy cập.

## Tóm Tắt Một Câu
Từ khóa "super" trong Java cho phép lớp con truy cập phương thức, thuộc tính và constructor của lớp cha, giúp quản lý kế thừa một cách hiệu quả.