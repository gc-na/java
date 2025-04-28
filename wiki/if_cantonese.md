<!--
Meta Description: # Java 中的 "if" 條件語句: 用法與示例 ## 概要 在 Java 編程語言中，`if` 條件語句是一種控制結構，允許開發者根據特定條件執行不同的代碼塊。這使得程序能夠根據輸入或其他條件做出決策，從而增強了靈活性。 ## 文件說明 ### 目的 `if` 語句的主要目的是根據布爾表達式的...
Meta Keywords: else, java, number, system, out
-->

# Java 中的 "if" 條件語句: 用法與示例

## 概要
在 Java 編程語言中，`if` 條件語句是一種控制結構，允許開發者根據特定條件執行不同的代碼塊。這使得程序能夠根據輸入或其他條件做出決策，從而增強了靈活性。

## 文件說明
### 目的
`if` 語句的主要目的是根據布爾表達式的結果決定執行哪部分代碼。當條件為真時，執行相應的代碼塊；當條件為假時，則可以選擇不執行或執行其他代碼。

### 用法
在 Java 中，`if` 語句的基本語法如下：

```java
if (condition) {
    // 當 condition 為 true 時執行的代碼
}
```

此外，還可以使用 `else` 和 `else if` 來處理多個條件：

```java
if (condition1) {
    // 當 condition1 為 true 時執行的代碼
} else if (condition2) {
    // 當 condition2 為 true 時執行的代碼
} else {
    // 當 condition1 和 condition2 都為 false 時執行的代碼
}
```

### 詳細說明
- `condition` 必須是一個返回布爾值的表達式（即 `true` 或 `false`）。
- 可以在 `if` 語句中嵌套其他 `if` 語句，以處理更複雜的邏輯。
- Java 還支持三元運算符（`?:`），這是一種簡化的 `if-else` 的寫法，用於簡單條件的處理。

## 範例
### 簡單範例
```java
int number = 10;
if (number > 5) {
    System.out.println("數字大於 5");
}
```

### 使用 `else` 和 `else if`
```java
int number = 10;
if (number > 10) {
    System.out.println("數字大於 10");
} else if (number == 10) {
    System.out.println("數字等於 10");
} else {
    System.out.println("數字小於 10");
}
```

### 嵌套 `if`
```java
int number = 15;
if (number > 10) {
    if (number > 20) {
        System.out.println("數字大於 20");
    } else {
        System.out.println("數字在 11 到 20 之間");
    }
} else {
    System.out.println("數字小於或等於 10");
}
```

## 解釋
- **常見陷阱**：在 `if` 條件中使用賦值運算符（`=`）而不是比較運算符（`==`）會導致錯誤。確保使用正確的運算符來避免邏輯錯誤。
- **可讀性**：在複雜的條件中，保持代碼的可讀性非常重要。使用明確的變量名和清晰的邏輯結構有助於維護代碼。
- **布爾運算**：可以使用邏輯運算符（如 `&&` 和 `||`）來組合多個條件。

## 一句總結
`if` 條件語句是 Java 中一個強大的工具，用於根據條件執行不同的代碼塊，從而增強程序的靈活性和智能性。