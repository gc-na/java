<!--
Meta Description: # Xuất khẩu (Exports) trong Java: Hiểu Biết Cơ Bản và Ứng Dụng ## Tóm tắt Tính năng "exports" trong Java cho phép các lập trình viên xác định các gói ...
Meta Keywords: module, exports, gói, trong, java
-->

# Xuất khẩu (Exports) trong Java: Hiểu Biết Cơ Bản và Ứng Dụng

## Tóm tắt
Tính năng "exports" trong Java cho phép các lập trình viên xác định các gói mà một module có thể sử dụng bên ngoài, giúp kiểm soát quyền truy cập và tổ chức mã nguồn hiệu quả hơn.

## Tài liệu
### Mục đích
Tính năng exports trong Java được sử dụng để chỉ định các gói (packages) mà module hiện tại cho phép các module khác truy cập. Điều này rất quan trọng trong lập trình module, giúp tăng cường tính bảo mật và tổ chức mã nguồn.

### Cách sử dụng
Để sử dụng tính năng exports, bạn cần khai báo nó trong file module-info.java của module. Cú pháp như sau:

```java
module tên_module {
    exports tên_gói;
}
```

Trong đó:
- `tên_module` là tên của module của bạn.
- `tên_gói` là tên của gói mà bạn muốn xuất khẩu.

### Chi tiết
- Nếu một gói được xuất khẩu, các class và interface trong gói đó có thể được truy cập từ các module khác.
- Bạn có thể xuất khẩu nhiều gói bằng cách liệt kê chúng, ví dụ:
```java
module tên_module {
    exports gói1;
    exports gói2;
}
```
- Bạn cũng có thể sử dụng chỉ định "exports" với điều kiện, cho phép chỉ một module cụ thể truy cập gói đó:
```java
module tên_module {
    exports gói1 to tên_module_khác;
}
```

## Ví dụ
### Ví dụ Cơ Bản
Giả sử bạn có một module tên là `my.module` và bạn muốn xuất khẩu gói `com.example`:

```java
module my.module {
    exports com.example;
}
```

### Ví dụ với Điều Kiện
Nếu bạn chỉ muốn module `another.module` có thể truy cập gói `com.example`:

```java
module my.module {
    exports com.example to another.module;
}
```

## Giải thích
Một số điểm cần lưu ý khi làm việc với exports:
- Nếu không khai báo exports, không module nào có thể truy cập gói trong module của bạn.
- Cần cẩn trọng khi xuất khẩu gói, vì việc này có thể tạo ra sự phụ thuộc không cần thiết giữa các module.
- Nếu đã xuất khẩu một gói, bạn không thể thay đổi quyền truy cập sau này mà không gây ra lỗi biên dịch.

## Tóm tắt một dòng
Tính năng "exports" trong Java cho phép kiểm soát quyền truy cập đến các gói trong module, nâng cao tính bảo mật và tổ chức mã nguồn.