<!--
Meta Description: # JAVA 中的「case」語句：用於條件判斷的強大工具 ## 簡介 在 JAVA 編程語言中，「case」語句是 switch 語句的一部分，用於根據變數的不同值執行不同的代碼塊。這是一種簡便的條件控制方式，能提升代碼的可讀性和維護性。 ## 文檔 ### 目的 「case」語句主要用於多重選擇...
Meta Keywords: case, switch, break, dayname, java
-->

# JAVA 中的「case」語句：用於條件判斷的強大工具

## 簡介
在 JAVA 編程語言中，「case」語句是 switch 語句的一部分，用於根據變數的不同值執行不同的代碼塊。這是一種簡便的條件控制方式，能提升代碼的可讀性和維護性。

## 文檔
### 目的
「case」語句主要用於多重選擇的情況，通過 switch 語句來簡化多個 if-else 判斷的結構。當需要根據一個變數的多個可能值選擇執行的代碼段時，「case」語句變得特別有用。

### 用法
在 JAVA 中，使用 switch 語句和 case 標籤來實現條件分支。基本語法如下：

```java
switch (expression) {
    case value1:
        // 執行代碼塊1
        break;
    case value2:
        // 執行代碼塊2
        break;
    // 可以有多個 case
    default:
        // 如果沒有匹配的 case，執行這裡的代碼
}
```

- **expression**：這是需要進行判斷的變數。
- **case value**：這是對應於 expression 的具體值。
- **break**：終止 switch 語句的執行，防止執行後續的 case。
- **default**：可選的，當沒有任何 case 匹配時執行的代碼。

## 範例
以下是一個使用 case 語句的簡單範例：

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

在這個範例中，根據變數 `day` 的值，輸出對應的星期名稱。

## 解釋
### 常見陷阱
1. **忘記使用 break**：如果忘記了 `break`，程式將繼續執行後面的 case，可能導致意外的行為。
2. **使用不支援的類型**：在 switch 語句中，表達式只能是整數型別（byte, short, int, char）、String 或枚舉類型，使用其他類型會導致編譯錯誤。
3. **多重 case 標籤**：可以將多個 case 標籤指向同一代碼塊，但需要小心避免重複邏輯。

### 額外說明
在 JAVA 12 及以後版本中，還可以使用 switch 表達式，這樣可以在 switch 中直接返回值，進一步簡化代碼結構。

## 一句總結
在 JAVA 中，「case」語句是 switch 語句的一部分，提供了一種清晰的方式來根據變數的不同值執行相應的代碼塊。