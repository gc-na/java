<!--
Meta Description: # Boolean 在 Java 中的應用 ## 概述 在 Java 編程語言中，`boolean` 是一種基本數據類型，用於表示真（`true`）或假（`false`）的邏輯值。它是控制程式流程和條件判斷的核心元素。 ## 文檔 ### 目的 `boolean` 類型的主要目的是提供一種方式來表示...
Meta Keywords: boolean, java, system, out, println
-->

# Boolean 在 Java 中的應用

## 概述
在 Java 編程語言中，`boolean` 是一種基本數據類型，用於表示真（`true`）或假（`false`）的邏輯值。它是控制程式流程和條件判斷的核心元素。

## 文檔
### 目的
`boolean` 類型的主要目的是提供一種方式來表示邏輯狀態，並在程式中執行條件判斷。這是許多控制結構（例如 `if` 語句、`while` 迴圈等）的基礎。

### 使用
在 Java 中，`boolean` 變量只能持有兩種值：`true` 或 `false`。你可以使用關係運算符來生成布林值，例如 `==`、`!=`、`>`、`<` 等。

```java
boolean isJavaFun = true;
boolean isFishTasty = false;
```

### 詳細說明
- **聲明和初始化**：可以使用 `boolean` 來聲明變量，並在同一行中進行初始化。
- **邏輯運算**：Java 還提供了邏輯運算符，例如 `&&`（與）、`||`（或）、`!`（非），這些運算符可用於組合布林表達式。
- **條件語句**：在 `if` 語句中，條件表達式的結果必須是 `boolean` 類型。

```java
if (isJavaFun) {
    System.out.println("Java 是有趣的!");
} else {
    System.out.println("Java 不是有趣的!");
}
```

## 範例
### 基本用法
```java
public class BooleanExample {
    public static void main(String[] args) {
        boolean isSunny = true;

        if (isSunny) {
            System.out.println("今天是個陽光明媚的日子!");
        } else {
            System.out.println("今天可能會下雨!");
        }
    }
}
```

### 邏輯運算符範例
```java
public class LogicalOperatorsExample {
    public static void main(String[] args) {
        boolean isRaining = false;
        boolean isWeekend = true;

        if (!isRaining && isWeekend) {
            System.out.println("可以出去玩!");
        } else {
            System.out.println("留在家裡比較好!");
        }
    }
}
```

## 解釋
- **常見陷阱**：在使用布林值時，確保你的條件表達式正確。比如，將 `=` 用於比較時，會引發編譯錯誤，因為 `=` 是賦值運算符，而非比較運算符。
- **自動裝箱**：Java 會自動將 `boolean` 轉換為 `Boolean` 對象，這在需要對象的情況下非常方便，但要注意性能影響。
- **空指針異常**：使用 `Boolean` 對象時，若未初始化可能會導致空指針異常。

## 簡短總結
`boolean` 是 Java 中用於表示邏輯真值（真或假）的基本數據類型，廣泛應用於條件判斷和控制結構中。