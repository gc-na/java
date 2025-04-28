<!--
Meta Description: # Câu Lệnh "for" Trong JAVA: Cách Sử Dụng và Ví Dụ ## Tóm tắt Câu lệnh "for" trong JAVA là một cấu trúc điều khiển cho phép lặp qua một đoạn mã nhiều ...
Meta Keywords: câu, lệnh, điều, lặp, java
-->

# Câu Lệnh "for" Trong JAVA: Cách Sử Dụng và Ví Dụ

## Tóm tắt
Câu lệnh "for" trong JAVA là một cấu trúc điều khiển cho phép lặp qua một đoạn mã nhiều lần. Nó thường được sử dụng để duyệt qua các mảng hoặc danh sách, giúp đơn giản hóa các tác vụ lặp đi lặp lại.

## Tài liệu
Câu lệnh "for" trong JAVA có ba phần chính: khởi tạo, điều kiện và cập nhật. Cú pháp cơ bản của câu lệnh "for" như sau:

```java
for (khởi_tạo; điều_kiện; cập_nhật) {
    // đoạn mã cần thực thi
}
```

- **Khởi Tạo**: Đây là nơi bạn khai báo và khởi tạo biến điều khiển. Biến này thường được sử dụng để đếm số lần lặp.
  
- **Điều Kiện**: Trước mỗi vòng lặp, điều kiện này sẽ được kiểm tra. Nếu điều kiện trả về `true`, đoạn mã trong thân vòng lặp sẽ được thực thi. Nếu `false`, vòng lặp sẽ kết thúc.
  
- **Cập Nhật**: Sau mỗi lần thực thi đoạn mã trong thân vòng lặp, phần này sẽ được thực hiện. Nó thường được sử dụng để thay đổi biến điều khiển, ví dụ như tăng giá trị của biến lên 1.

Ví dụ, nếu bạn muốn lặp từ 0 đến 9, bạn có thể viết:

```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

## Ví dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng câu lệnh "for":

### Ví dụ 1: In số từ 0 đến 4
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

### Ví dụ 2: Duyệt qua một mảng
```java
String[] fruits = {"Táo", "Chuối", "Cam"};
for (int i = 0; i < fruits.length; i++) {
    System.out.println(fruits[i]);
}
```

### Ví dụ 3: Sử dụng câu lệnh "for" mở rộng (Enhanced for loop)
```java
for (String fruit : fruits) {
    System.out.println(fruit);
}
```

## Giải thích
Một số lưu ý khi sử dụng câu lệnh "for":

- **Lỗi phổ biến**: Một trong những lỗi thường gặp là không cập nhật biến điều khiển, dẫn đến vòng lặp vô hạn. Hãy chắc chắn rằng điều kiện sẽ trở thành `false` tại một thời điểm nào đó.
  
- **Kiểm tra điều kiện**: Đảm bảo rằng điều kiện trong câu lệnh "for" luôn có thể trở thành `false`. Nếu không, chương trình sẽ không bao giờ dừng lại.
  
- **Sử dụng câu lệnh "for" mở rộng**: Khi làm việc với các mảng hoặc danh sách, bạn có thể sử dụng câu lệnh "for" mở rộng để làm cho mã ngắn gọn và dễ đọc hơn.

## Tóm tắt Một Dòng
Câu lệnh "for" trong JAVA cho phép lập trình viên dễ dàng lặp qua các đoạn mã, đặc biệt khi làm việc với mảng và danh sách.