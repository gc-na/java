<!--
Meta Description: # Java 中的 "while" 迴圈：使用方法與範例 ## 簡介 在 Java 程式設計中，"while" 迴圈是一種基本的控制結構，用於在特定條件為真時重複執行一段程式碼。這使得程式能夠在不斷檢查條件的情況下進行迭代，直至條件不再成立。 ## 文檔 ### 目的 "while" 迴圈的主要目的...
Meta Keywords: while, java, scanner, count, system
-->

# Java 中的 "while" 迴圈：使用方法與範例

## 簡介
在 Java 程式設計中，"while" 迴圈是一種基本的控制結構，用於在特定條件為真時重複執行一段程式碼。這使得程式能夠在不斷檢查條件的情況下進行迭代，直至條件不再成立。

## 文檔
### 目的
"while" 迴圈的主要目的是在條件為真時重複執行程式碼區塊，這對於需要重複操作的情況非常有用，例如：用戶輸入、計算或資料處理等。

### 使用方法
"while" 迴圈的基本語法如下：

```java
while (條件) {
    // 執行的程式碼
}
```

- **條件**：一個布林表達式，當其評估為真時，將執行迴圈內的程式碼。
- **程式碼區塊**：當條件為真時，將被重複執行的程式碼。

### 詳細說明
1. **初始化**：在進入迴圈之前，需要初始化變數。
2. **條件評估**：每次迴圈開始時都會評估條件，如果為真則執行程式碼。
3. **更新**：在程式碼執行後，通常需要更新條件變數，以避免無限迴圈。
4. **退出條件**：當條件評估為假時，迴圈將停止執行。

## 範例
### 基本範例

```java
int count = 0;

while (count < 5) {
    System.out.println("計數: " + count);
    count++;
}
```

這段程式碼將輸出：
```
計數: 0
計數: 1
計數: 2
計數: 3
計數: 4
```

### 使用者輸入範例

```java
import java.util.Scanner;

public class UserInput {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input;

        System.out.println("請輸入 'exit' 以終止程式。");

        while (true) {
            input = scanner.nextLine();
            if (input.equals("exit")) {
                break;
            }
            System.out.println("您輸入的內容是: " + input);
        }
        scanner.close();
    }
}
```

## 解釋
### 常見陷阱
- **無限迴圈**：最常見的錯誤是未正確更新條件變數，導致迴圈無法終止。
- **條件檢查**：確保條件在迴圈的合適時機進行檢查，避免在迴圈內部造成意外的狀況。
- **執行效率**：在某些情況下，過度使用 "while" 迴圈可能會影響程式性能，應根據需求選擇合適的迴圈結構。

## 一句總結
"while" 迴圈是 Java 中用於基於條件重複執行程式碼的簡單且有效的控制結構。