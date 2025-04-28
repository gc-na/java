<!--
Meta Description: # Từ Khóa "protected" trong JAVA: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa "protected" trong JAVA được sử dụng để xác định phạm vi truy cập của các ...
Meta Keywords: lớp, protected, các, truy, cập
-->

# Từ Khóa "protected" trong JAVA: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa "protected" trong JAVA được sử dụng để xác định phạm vi truy cập của các thành phần (biến, phương thức) trong lớp, cho phép các thành phần này có thể được truy cập từ các lớp con và các lớp trong cùng một gói.

## Tài Liệu
### Mục Đích
Từ khóa "protected" giúp quản lý quyền truy cập cho các thuộc tính và phương thức của lớp. Khi một thành phần được khai báo là "protected", nó có thể được truy cập từ:
- Lớp con (subclass) của lớp đó, ngay cả khi lớp con nằm ở gói khác.
- Các lớp khác trong cùng một gói.

### Cách Sử Dụng
Để sử dụng từ khóa "protected", bạn chỉ cần thêm từ khóa này trước khai báo của biến hoặc phương thức trong lớp. Ví dụ:

```java
class Animal {
    protected String name;

    protected void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void display() {
        System.out.println("Dog name: " + name);
        sound();
    }
}
```

### Chi Tiết
- **Khi nào nên sử dụng "protected"?**: Sử dụng "protected" khi bạn muốn cho phép các lớp con trong các gói khác có thể truy cập vào các thành phần của lớp cha, nhưng không muốn cho phép quyền truy cập từ các lớp không liên quan.
- **Khác với các từ khóa khác**:
  - **public**: Có thể truy cập từ bất kỳ đâu.
  - **private**: Chỉ có thể truy cập trong cùng một lớp.
  - **default** (không có từ khóa): Chỉ có thể truy cập trong cùng một gói.

## Ví Dụ
Dưới đây là một ví dụ đơn giản về cách sử dụng "protected":

```java
class Vehicle {
    protected int speed;

    protected void setSpeed(int speed) {
        this.speed = speed;
    }
}

class Car extends Vehicle {
    void showSpeed() {
        setSpeed(100);
        System.out.println("Car speed: " + speed);
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.showSpeed();
    }
}
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Không thể truy cập**: Nếu bạn cố gắng truy cập một thành phần "protected" từ một lớp không phải là lớp con và không ở cùng một gói, bạn sẽ gặp lỗi biên dịch.
- **Sử dụng không đúng ngữ cảnh**: Nên cân nhắc kỹ lưỡng trước khi sử dụng "protected" để tránh việc lộ thông tin không mong muốn cho các lớp không liên quan.

## Tóm Tắt Một Dòng
Từ khóa "protected" trong JAVA cho phép truy cập đến các thành phần của lớp từ các lớp con và các lớp trong cùng một gói, giúp quản lý quyền truy cập một cách hiệu quả.