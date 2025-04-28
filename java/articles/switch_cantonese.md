<!--
Meta Description: # JAVA 中的 Switch 語句：用於控制流的有效工具 ## 簡介 Switch 語句是 JAVA 中的一種控制流結構，允許根據變量的值執行不同的程式碼塊。這使得代碼更易於閱讀和維護，特別是在需要多條選擇的情況下。 ## 文檔 ### 目的 Switch 語句的主要目的是提供一種替代多重 if...
Meta Keywords: switch, case, break, java, dayname
-->

# JAVA 中的 Switch 語句：用於控制流的有效工具

## 簡介
Switch 語句是 JAVA 中的一種控制流結構，允許根據變量的值執行不同的程式碼塊。這使得代碼更易於閱讀和維護，特別是在需要多條選擇的情況下。

## 文檔
### 目的
Switch 語句的主要目的是提供一種替代多重 if-else 語句的方式，以簡化代碼結構並提高可讀性。

### 使用
Switch 語句的基本語法如下：

```java
switch (表達式) {
    case 值1:
        // 執行的代碼
        break;
    case 值2:
        // 執行的代碼
        break;
    default:
        // 默認執行的代碼
}
```

- **表達式**：可以是整數、字符、字符串或枚舉類型。
- **case**：每個 case 標籤後面都跟著一個常量值，當表達式的值匹配時，對應的代碼會被執行。
- **break**：用於退出 switch 塊，防止執行後續的 case。
- **default**：可選項，當沒有任何 case 匹配時執行的代碼。

### 詳情
Switch 語句的特性包括：
- 可以包含多個 case 標籤。
- 可以不使用 break，這將導致 "fall-through" 行為，即會執行後面所有的 case 代碼，直到遇到 break 或 switch 結束。
- 在 JAVA 12 及以後版本，支持使用 switch 表達式，這使得 switch 可以返回值，並且語法更為簡潔。

## 例子
### 基本用法
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
        dayName = "無效的日子";
        break;
}

System.out.println(dayName);  // 輸出：星期三
```

### 使用 Switch 表達式（Java 12+）
```java
String dayType = switch (day) {
    case 1, 7 -> "週末";
    case 2, 3, 4, 5, 6 -> "工作日";
    default -> "無效的日子";
};

System.out.println(dayType);  // 輸出：工作日
```

## 解釋
在使用 switch 語句時，開發者需注意以下幾點：
- 忘記使用 break 可能導致意外的行為，尤其是在多個 case 之間共享代碼時。
- 使用 switch 表達式可以提高代碼的簡潔性，但需要確保使用的 JAVA 版本支持此特性。
- switch 語句的表達式值必須是整數類型、字符類型、字符串類型或枚舉類型，不能使用浮點數或其他非支援類型。

## 總結
Switch 語句是 JAVA 中一個強大的控制流工具，可以使代碼更清晰，特別是在面對多重選擇的情況下。