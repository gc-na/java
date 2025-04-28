<!--
Meta Description: # Java 中的 "continue" 語句：使用指南與範例 ## 概述 在 Java 程式設計中，`continue` 語句用於控制循環的執行流程。當 `continue` 被執行時，當前迴圈的剩餘代碼將被跳過，並進入下一輪迴圈的執行。 ## 文檔 ### 目的 `continue` 語句的主要...
Meta Keywords: continue, java, int, outerloop, public
-->

# Java 中的 "continue" 語句：使用指南與範例

## 概述
在 Java 程式設計中，`continue` 語句用於控制循環的執行流程。當 `continue` 被執行時，當前迴圈的剩餘代碼將被跳過，並進入下一輪迴圈的執行。

## 文檔
### 目的
`continue` 語句的主要目的是提前結束當前迴圈的迭代，並跳過後面的語句，直接進入下一次迭代。這在需要根據特定條件跳過某些操作時非常有用。

### 使用方法
`continue` 可以在 `for`、`while` 和 `do-while` 循環中使用。當 `continue` 被執行時，控制權將立即返回到循環的起始部分。

以下是 `continue` 語句的基本語法：

```java
continue; // 在當前迴圈中使用
```

在嵌套循環中，`continue` 也可以與標籤一起使用，以指定應該跳過的外層循環。

```java
outerLoop: for (int i = 0; i < 5; i++) {
    for (int j = 0; j < 5; j++) {
        if (j == 2) {
            continue outerLoop; // 跳過外層循環的當前迭代
        }
        System.out.println("i = " + i + ", j = " + j);
    }
}
```

### 詳細說明
- `continue` 語句可以用於所有類型的循環。
- 當使用 `continue` 時，請確保在適當的條件下使用，以避免無限循環或邏輯錯誤。

## 範例
### 基本範例

```java
public class ContinueExample {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            if (i % 2 == 0) {
                continue; // 當 i 為偶數時，跳過剩下的代碼
            }
            System.out.println(i); // 只會輸出奇數
        }
    }
}
```

在這個例子中，`continue` 語句使得當 `i` 為偶數時，該迭代的剩餘部分不會執行，從而只輸出奇數。

### 嵌套循環範例

```java
public class NestedContinueExample {
    public static void main(String[] args) {
        outerLoop: for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                if (j == 1) {
                    continue outerLoop; // 跳過外層循環的當前迭代
                }
                System.out.println("i = " + i + ", j = " + j);
            }
        }
    }
}
```

在這個範例中，當 `j` 等於 1 時，使用 `continue` 跳過當前外層迴圈的迭代，僅輸出 `j` 不等於 1 的情況。

## 解釋
- **常見的陷阱**：使用 `continue` 時，務必確保不會導致無限迴圈。特別是當條件判斷不正確時，可能會永遠跳過某個條件，導致無法退出循環。
- **效能考量**：在某些情況下，使用 `continue` 可能會使代碼的可讀性降低，特別是當嵌套循環過多時，因此應謹慎使用。

## 總結
`continue` 語句在 Java 中用於控制循環流程，使得在特定條件下跳過當前迭代的剩餘部分，進而直接進入下一次迭代。