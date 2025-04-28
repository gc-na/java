<!--
Meta Description: # Java 中的 switch 語句：使用指南與範例 ## 簡介 在 Java 程式語言中，`switch` 語句是一種控制流程結構，允許根據變數的值選擇多個可能的執行路徑。此語句通常用於替代多重的 `if-else` 結構，使程式碼更具可讀性與維護性。 ## 文檔 ### 目的 `switch`...
Meta Keywords: case, switch, break, dayname, java
-->

# Java 中的 switch 語句：使用指南與範例

## 簡介
在 Java 程式語言中，`switch` 語句是一種控制流程結構，允許根據變數的值選擇多個可能的執行路徑。此語句通常用於替代多重的 `if-else` 結構，使程式碼更具可讀性與維護性。

## 文檔
### 目的
`switch` 語句的主要目的是在多個選項中根據變數的值執行相應的程式碼區塊。這在需要基於某個變數的具體值來選擇執行路徑的情況下特別有用。

### 使用方法
`switch` 語句的基本語法如下：

```java
switch (expression) {
    case value1:
        // 當 expression 等於 value1 時執行的程式碼
        break;
    case value2:
        // 當 expression 等於 value2 時執行的程式碼
        break;
    // 可以包含更多的 case
    default:
        // 當沒有任何 case 匹配時執行的程式碼
}
```

- **expression**：一個可以評估為字串、整數、枚舉或其他相容類型的表達式。
- **case**：每個 `case` 標籤後跟一個特定值，當 `expression` 匹配該值時，對應的程式碼將被執行。
- **break**：結束 `switch` 區塊，防止執行到下一個 `case`。
- **default**：可選的，當沒有任何 `case` 匹配時執行。

### 注意事項
- `switch` 語句僅支持特定的數據類型（如 `int`, `char`, `String` 和枚舉）。
- 在 `case` 中，值必須是常量表達式。
- 忘記 `break` 語句會導致「fall-through」行為，即會執行後續的 `case` 代碼，這可能不是預期的結果。

## 範例
### 基本範例
以下是一個使用 `switch` 語句的簡單範例：

```java
int day = 3;
String dayName;

switch (day) {
    case 1:
        dayName = "星期一";
        break;
    case 2:
        dayName = "星期二";
        break;
    case 3:
        dayName = "星期三";
        break;
    case 4:
        dayName = "星期四";
        break;
    case 5:
        dayName = "星期五";
        break;
    default:
        dayName = "無效的日子";
}

System.out.println(dayName); // 輸出：星期三
```

### 字串範例
使用 `String` 作為 `switch` 表達式的範例：

```java
String fruit = "蘋果";

switch (fruit) {
    case "香蕉":
        System.out.println("這是一根香蕉。");
        break;
    case "蘋果":
        System.out.println("這是一個蘋果。");
        break;
    default:
        System.out.println("這不是香蕉或蘋果。");
}
```

## 解釋
在使用 `switch` 語句時，開發者應注意以下幾點：
- 省略 `break` 會導致程式碼連續執行，可能會導致錯誤的結果。
- `case` 標籤必須是唯一的，重複的 `case` 會導致編譯錯誤。
- 由於 `switch` 語句只能處理特定類型，對於複雜的條件判斷，仍需使用 `if-else` 結構。

## 總結
Java 中的 `switch` 語句提供了一種高效的方式來根據變數的值選擇執行路徑，提升程式碼的可讀性與結構性。