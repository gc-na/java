<!--
Meta Description: # Java中的"return"關鍵字：功能與用法詳解 ## 簡介 在Java程式語言中，`return`關鍵字是用來結束方法的執行並返回指定值的關鍵指令。它在控制流程中扮演著重要的角色，特別是在需要從方法中傳遞結果的情況下。 ## 文檔 ### 目的 `return`關鍵字的主要目的是結束當前方法...
Meta Keywords: return, void, int, java, public
-->

# Java中的"return"關鍵字：功能與用法詳解

## 簡介
在Java程式語言中，`return`關鍵字是用來結束方法的執行並返回指定值的關鍵指令。它在控制流程中扮演著重要的角色，特別是在需要從方法中傳遞結果的情況下。

## 文檔
### 目的
`return`關鍵字的主要目的是結束當前方法的執行，並將控制權返回給調用該方法的上下文。如果方法聲明了返回類型，則必須使用`return`來返回對應類型的值，否則編譯器將發出錯誤。

### 用法
在Java中，`return`的基本語法如下：
```java
return [expression];
```
- `expression`：可選，表示要返回的值。當方法的返回類型為`void`時，此部分可以省略。

### 詳細說明
- **返回類型**：方法的返回類型必須與`return`語句中的表達式類型相符。例如，若方法宣告為`int`類型，則`return`後必須跟一個整數值。
- **void 方法**：對於返回類型為`void`的方法，`return`可以不帶任何值使用，只需寫作`return;`即可。
- **多重返回**：方法中可以包含多個`return`語句，根據條件不同可以在不同狀況下返回不同的值。

## 示例
以下是使用`return`的基本示例：

### 示例1：返回整數
```java
public int add(int a, int b) {
    return a + b;  // 返回兩個整數的和
}
```

### 示例2：void 方法
```java
public void printMessage() {
    System.out.println("Hello, World!");
    return;  // 可選的return語句
}
```

### 示例3：條件返回
```java
public String checkNumber(int number) {
    if (number > 0) {
        return "正數";
    } else if (number < 0) {
        return "負數";
    } else {
        return "零";
    }
}
```

## 解釋
### 常見陷阱
- **未返回值的錯誤**：如果方法聲明了返回類型，但缺少`return`語句，將會導致編譯錯誤。
- **無法返回多個值**：Java方法只能返回一個值，如果需要返回多個值，應考慮使用物件、數組或資料結構。
- **提前返回**：在方法中使用多個`return`可能導致程式碼可讀性降低，建議在設計方法時考慮清晰的邏輯流。

## 一句總結
`return`關鍵字在Java中用於結束方法執行並返回值，是控制流程的重要工具。