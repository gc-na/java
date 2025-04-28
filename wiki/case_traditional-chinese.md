<!--
Meta Description: # Java 的 switch-case 語句：用於控制流程的高效工具 ## 概述 Java 的 `switch-case` 語句是一種控制流程的結構，允許依據變數的值來執行不同的代碼區塊。這個語句通常用於替代多個 `if-else` 判斷，使代碼更清晰易讀。 ## 文檔 ### 目的 `switc...
Meta Keywords: case, switch, break, java, dayname
-->

# Java 的 switch-case 語句：用於控制流程的高效工具

## 概述
Java 的 `switch-case` 語句是一種控制流程的結構，允許依據變數的值來執行不同的代碼區塊。這個語句通常用於替代多個 `if-else` 判斷，使代碼更清晰易讀。

## 文檔
### 目的
`switch-case` 語句使得根據變數的不同值執行不同代碼片段變得更加簡單和高效。它特別適用於處理多個選項的情況。

### 用法
`switch-case` 的基本語法如下：
```java
switch (expression) {
    case value1:
        // 執行代碼
        break; // 可選
    case value2:
        // 執行代碼
        break; // 可選
    // 可以有任意數量的 case
    default:
        // 如果沒有匹配的 case，執行此代碼
}
```
- **expression**：可以是整數、字符、字串或枚舉類型。
- **case value**：每一個 `case` 的值必須是常量。
- **break**：用於終止 `switch` 區塊，防止執行後續的 `case`。如果省略 `break`，將會執行下方所有 `case` 的代碼，這稱為「fall-through」。

### 詳細信息
- `switch-case` 常用於處理多個選項，但在某些情況下，`if-else` 可能更為合適。
- 在 Java 12 及以後版本，可以使用 `switch` 表達式來返回值，這增強了 `switch` 的功能。

## 示例
基本示例：
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
    default:
        dayName = "未知";
}

System.out.println(dayName); // 輸出：星期三
```

另一個示例，使用字串作為表達式：
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
        System.out.println("未知的水果。");
}
```

## 解釋
- **常見陷阱**：如果在 `case` 中忘記使用 `break`，可能會導致意想不到的結果，因為程序會繼續執行後面的 `case` 區塊。
- **類型限制**：`switch` 語句僅支持整數、字符、字串及枚舉類型，無法用於布林值或浮點數等其他類型。
- **可讀性**：使用 `switch-case` 可以使代碼更具可讀性，尤其是在處理多個選項時。

## 總結
Java 的 `switch-case` 語句是一種有效的控制流程工具，能夠簡化根據變數值執行不同代碼的過程。