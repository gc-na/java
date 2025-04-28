<!--
Meta Description: # Java 中的 catch：異常處理的關鍵字 ## 簡介 在 Java 程式設計中，`catch` 是用於處理異常的重要關鍵字。它允許開發者捕捉程式執行期間發生的錯誤，從而避免程式崩潰並提供應對措施。 ## 文檔 `catch` 關鍵字是 Java 異常處理機制的一部分，通常與 `try` 和 ...
Meta Keywords: catch, java, try, ioexception, nullpointerexception
-->

# Java 中的 catch：異常處理的關鍵字

## 簡介
在 Java 程式設計中，`catch` 是用於處理異常的重要關鍵字。它允許開發者捕捉程式執行期間發生的錯誤，從而避免程式崩潰並提供應對措施。

## 文檔
`catch` 關鍵字是 Java 異常處理機制的一部分，通常與 `try` 和 `finally` 共同使用。當程式碼塊中的某個操作引發異常時，`catch` 允許開發者捕捉該異常並執行相應的處理邏輯。

### 目的
`catch` 的主要目的是為了捕捉和處理異常，以保證程式的穩定性和用戶體驗。通過適當的異常處理，開發者可以避免程式崩潰、提示用戶友好的錯誤信息，並可能進行後續的錯誤修正或資源釋放。

### 用法
`catch` 的基本語法如下：

```java
try {
    // 可能引發異常的程式碼
} catch (ExceptionType e) {
    // 異常處理邏輯
}
```

在此語法中，`ExceptionType` 是具體的異常類型，比如 `IOException` 或 `NullPointerException`，`e` 是捕捉到的異常對象，可以用來獲取異常的詳細信息。

## 示例
以下是一個簡單的示例，演示如何使用 `catch` 捕捉異常：

```java
public class CatchExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // 此行將引發 ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("發生錯誤：除以零不允許");
        }
    }
}
```

在這個示例中，當嘗試除以零時，`catch` 捕捉到了 `ArithmeticException`，並打印出友好的錯誤消息。

## 解釋
在使用 `catch` 時，開發者需注意以下幾點：

1. **多個 catch 塊**：可以為一個 `try` 塊指定多個 `catch` 塊，以處理不同類型的異常。例如：
   ```java
   try {
       // 可能引發多種異常的程式碼
   } catch (IOException e) {
       // 處理 IOException
   } catch (NullPointerException e) {
       // 處理 NullPointerException
   }
   ```

2. **捕捉子類異常**：如果同時有父類和子類異常，應該將子類異常的 `catch` 塊放在前面，否則父類異常將捕捉所有的子類異常。

3. **不捕捉 Throwable**：避免捕捉 `Throwable`，因為它會捕捉所有的異常，包括系統異常，這可能會導致更難以調試的情況。

## 一句總結
`catch` 是 Java 中用於捕捉和處理異常的關鍵字，幫助開發者提高程式的穩定性和用戶體驗。