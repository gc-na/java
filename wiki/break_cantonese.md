<!--
Meta Description: # Java 中的 "break" 語句：用法與示例 ## 概述 在 Java 中，`break` 語句是一種控制流語句，用於立即終止循環或 switch 語句。它有助於提高代碼的可讀性和效率，並可用於改變程序的執行路徑。 ## 文檔 ### 目的 `break` 語句的主要目的是在特定條件下退出循...
Meta Keywords: break, system, out, println, switch
-->

# Java 中的 "break" 語句：用法與示例

## 概述
在 Java 中，`break` 語句是一種控制流語句，用於立即終止循環或 switch 語句。它有助於提高代碼的可讀性和效率，並可用於改變程序的執行路徑。

## 文檔

### 目的
`break` 語句的主要目的是在特定條件下退出循環（如 `for`、`while` 或 `do-while` 循環）或 `switch` 語句，避免不必要的迭代或條件判斷。

### 用法
`break` 語句可以在以下情況下使用：

1. **在循環中**：
   - 當滿足某個條件時，使用 `break` 終止循環。
   
   ```java
   for (int i = 0; i < 10; i++) {
       if (i == 5) {
           break;
       }
       System.out.println(i);
   }
   ```

2. **在 switch 語句中**：
   - `break` 用於結束 case 的執行，防止“落入”下一個 case。

   ```java
   int day = 3;
   switch (day) {
       case 1:
           System.out.println("星期一");
           break;
       case 2:
           System.out.println("星期二");
           break;
       case 3:
           System.out.println("星期三");
           break;
       default:
           System.out.println("無效的日子");
   }
   ```

### 詳情
- `break` 語句只能在循環或 switch 語句內部使用。
- 使用 `break` 可以提高代碼的效率，特別是在需要提前退出的情況下。
- 在使用嵌套循環時，`break` 只會終止最近的那一層循環。

## 示例

### 基本用法示例
1. **在 for 循環中使用 break**:
   ```java
   for (int j = 0; j < 10; j++) {
       if (j == 7) {
           break;
       }
       System.out.println(j);
   }
   // 輸出：0 1 2 3 4 5 6
   ```

2. **在 switch 語句中使用 break**:
   ```java
   char grade = 'B';
   switch (grade) {
       case 'A':
           System.out.println("優秀");
           break;
       case 'B':
           System.out.println("良好");
           break;
       case 'C':
           System.out.println("及格");
           break;
       default:
           System.out.println("不及格");
   }
   // 輸出：良好
   ```

## 解釋
- **常見陷阱**：
  - 忘記在 `switch` 語句中使用 `break` 可能導致意外的行為，即“落入”下一個 case。
  - 在嵌套循環中使用 `break` 只會退出最近的循環，可能會導致混淆。

- **注意事項**：
  - `break` 語句應謹慎使用，過度使用可能會使代碼難以閱讀。
  - 在需要跳出多層循環的情況下，考慮使用標籤 `break`，例如 `break label;`。

## 一行總結
`break` 語句在 Java 中用於立即終止循環或 switch 語句，從而控制程序的執行流。