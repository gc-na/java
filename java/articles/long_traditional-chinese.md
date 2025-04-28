<!--
Meta Description: # Java 中的 long 資料型別：詳細指南與使用範例 ## 概述 在 Java 編程語言中，`long` 是一種基本資料型別，用於存儲較大的整數值。它的範圍比 `int` 更廣，可以有效地處理需要更高精度的數值。 ## 文檔 ### 目的 `long` 資料型別的主要目的是提供一個能夠儲存從 ...
Meta Keywords: long, java, public, string, 223
-->

# Java 中的 long 資料型別：詳細指南與使用範例

## 概述
在 Java 編程語言中，`long` 是一種基本資料型別，用於存儲較大的整數值。它的範圍比 `int` 更廣，可以有效地處理需要更高精度的數值。

## 文檔
### 目的
`long` 資料型別的主要目的是提供一個能夠儲存從 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807（即 -2^63 到 2^63-1）之間的整數數值的能力。這使得 `long` 成為需要大量數據處理的計算程序的理想選擇。

### 使用
在 Java 中，`long` 以 64 位元的二進位制形式儲存，並可以透過以下方式來宣告：
```java
long myLongValue = 123456789L;
```
注意，結尾的 `L` 是必需的，表示該數值是 `long` 型別，否則編譯器會將其視為 `int` 型別。

### 詳細信息
- **預設值**：`long` 型別的預設值為 `0L`。
- **自動轉型**：`int` 可以自動轉型為 `long`，但相反則需要顯式轉型。
- **包裝類**：`Long` 是 `long` 的包裝類，提供了多種方法來處理數字，例如 `Long.parseLong(String s)` 來將字串轉換為 `long` 型別。

## 範例
以下是一些 `long` 的基本使用範例：

### 宣告與初始化
```java
public class LongExample {
    public static void main(String[] args) {
        long myLong = 123456789L;
        System.out.println("My long value: " + myLong);
    }
}
```

### 數學運算
```java
public class LongMath {
    public static void main(String[] args) {
        long num1 = 100000L;
        long num2 = 200000L;
        long sum = num1 + num2;
        System.out.println("Sum: " + sum);
    }
}
```

### 字串轉換
```java
public class LongParsing {
    public static void main(String[] args) {
        String numberStr = "9876543210";
        long parsedLong = Long.parseLong(numberStr);
        System.out.println("Parsed long value: " + parsedLong);
    }
}
```

## 解釋
使用 `long` 型別時，開發者需要注意以下幾點常見問題：
- **溢出**：當計算結果超出 `long` 的範圍時，會發生溢出，導致意外的結果。
- **性能**：雖然 `long` 提供了更大的範圍，但在某些應用中，頻繁使用 `long` 可能會影響性能。
- **字串格式**：在解析字串為 `long` 時，如果字串格式不正確，將會引發 `NumberFormatException`。

## 一句話總結
`long` 是 Java 中用於存儲大整數的基本資料型別，範圍從 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807。