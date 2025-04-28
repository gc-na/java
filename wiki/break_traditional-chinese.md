<!--
Meta Description: # Java 中的 "break" 語句：用於控制流程的關鍵字 ## 簡介 在 Java 程式設計中，`break` 語句是一個重要的控制流程關鍵字，用於提前退出循環或 `switch` 陳述。它能夠提高程式的可讀性和效率，並使得控制流程更加靈活。 ## 文件說明 ### 目的 `break` 語句...
Meta Keywords: break, switch, case, system, out
-->

# Java 中的 "break" 語句：用於控制流程的關鍵字

## 簡介
在 Java 程式設計中，`break` 語句是一個重要的控制流程關鍵字，用於提前退出循環或 `switch` 陳述。它能夠提高程式的可讀性和效率，並使得控制流程更加靈活。

## 文件說明
### 目的
`break` 語句的主要目的是立即終止當前的循環（如 `for`、`while` 或 `do-while`）或 `switch` 陳述的執行，並跳出其外層的結構。

### 使用方法
- **在循環中使用**：當滿足特定條件時，可以使用 `break` 來結束循環。
- **在 switch 陳述中使用**：`break` 可用於終止一個 `case` 的執行，防止執行後續的 `case`。

### 詳細說明
- **語法**：
  ```java
  break;
  ```

- **使用範例**：
  ```java
  for (int i = 0; i < 10; i++) {
      if (i == 5) {
          break; // 當 i 等於 5 時，退出循環
      }
      System.out.println(i);
  }
  ```

- **在 switch 中的使用**：
  ```java
  int day = 3;
  switch (day) {
      case 1:
          System.out.println("星期一");
          break; // 退出 switch
      case 2:
          System.out.println("星期二");
          break; // 退出 switch
      case 3:
          System.out.println("星期三");
          break; // 退出 switch
      default:
          System.out.println("無效的日子");
  }
  ```

## 示例
以下是 `break` 語句在不同情境下的基本用法示例：

1. **在 for 循環中使用**：
   ```java
   for (int i = 0; i < 10; i++) {
       if (i == 3) {
           break; // 當 i 等於 3 時，跳出循環
       }
       System.out.println(i); // 輸出 0, 1, 2
   }
   ```

2. **在 switch 陳述中使用**：
   ```java
   char grade = 'B';
   switch (grade) {
       case 'A':
           System.out.println("優秀");
           break;
       case 'B':
           System.out.println("良好");
           break; // 此處將退出 switch，不會執行後面的 case
       case 'C':
           System.out.println("及格");
           break;
       default:
           System.out.println("不及格");
   }
   ```

## 解釋
- **常見陷阱**：
  - 忘記在 `switch` 陳述的 `case` 結束時加上 `break` 會導致「fall-through」行為，這意味著控制流程會繼續執行下一個 `case` 的內容，可能會導致意外的結果。
  
- **額外注意事項**：
  - `break` 語句只能在循環或 `switch` 內部使用，若在其他地方使用會導致編譯錯誤。
  - 在嵌套循環中，`break` 只會結束最內層的循環，若需要退出外層循環，可以使用標籤（label）結合 `break`。

## 一句總結
`break` 語句在 Java 中用於立即終止循環或 `switch` 陳述，從而提供靈活的控制流程方式。