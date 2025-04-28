<!--
Meta Description: # Lệnh "break" trong Java: Cách sử dụng và ví dụ ## Tóm tắt Lệnh "break" trong Java được sử dụng để thoát khỏi vòng lặp hoặc khối switch, giúp kiểm so...
Meta Keywords: break, lặp, vòng, trong, dụng
-->

# Lệnh "break" trong Java: Cách sử dụng và ví dụ

## Tóm tắt
Lệnh "break" trong Java được sử dụng để thoát khỏi vòng lặp hoặc khối switch, giúp kiểm soát luồng thực thi của chương trình một cách hiệu quả.

## Tài liệu
### Mục đích
Lệnh "break" cho phép lập trình viên dừng một vòng lặp (for, while, do-while) ngay lập tức hoặc thoát khỏi một khối switch case. Việc sử dụng "break" giúp cải thiện khả năng kiểm soát và giảm thiểu số lần lặp không cần thiết.

### Cú pháp
```java
break;
```

### Sử dụng
- Trong vòng lặp: Khi điều kiện cụ thể được đáp ứng, lệnh "break" sẽ dừng vòng lặp ngay lập tức.
- Trong khối switch: "break" được sử dụng để thoát khỏi một case, ngăn không cho chương trình tiếp tục thực thi các case tiếp theo.

## Ví dụ
### Ví dụ 1: Sử dụng "break" trong vòng lặp
```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break; // Thoát khỏi vòng lặp khi i = 5
    }
    System.out.println(i);
}
```
**Kết quả:** 
```
0
1
2
3
4
```

### Ví dụ 2: Sử dụng "break" trong khối switch
```java
int day = 3;
switch (day) {
    case 1:
        System.out.println("Thứ hai");
        break;
    case 2:
        System.out.println("Thứ ba");
        break;
    case 3:
        System.out.println("Thứ tư");
        break; // Thoát khỏi switch sau khi in ra "Thứ tư"
    default:
        System.out.println("Ngày không hợp lệ");
}
```
**Kết quả:** 
```
Thứ tư
```

## Giải thích
### Những cạm bẫy thường gặp
- **Quên lệnh "break":** Nếu bạn quên lệnh "break" trong khối switch, chương trình sẽ tiếp tục thực thi các case tiếp theo cho đến khi gặp lệnh "break" kế tiếp hoặc kết thúc khối switch.
- **Sử dụng "break" không đúng ngữ cảnh:** Lệnh "break" chỉ có thể được sử dụng trong vòng lặp hoặc khối switch. Nếu cố gắng sử dụng bên ngoài các cấu trúc này, sẽ gây ra lỗi biên dịch.

### Lưu ý
- Trong các vòng lặp lồng nhau, "break" chỉ thoát khỏi vòng lặp gần nhất.
- Đối với việc sử dụng "break" trong vòng lặp, hãy đảm bảo có điều kiện hợp lý để tránh việc vòng lặp không bao giờ dừng lại.

## Tóm tắt một câu
Lệnh "break" trong Java cho phép lập trình viên thoát khỏi vòng lặp hoặc khối switch một cách hiệu quả, giúp kiểm soát luồng thực thi của chương trình.