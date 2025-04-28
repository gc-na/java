<!--
Meta Description: # 在 Java 中使用 "finally" 的完整指南 ## 概述 在 Java 編程語言中，`finally` 是一個用於異常處理的關鍵字，它定義了一段代碼，無論是否發生異常，這段代碼都會被執行。它通常與 `try` 和 `catch` 塊搭配使用，以確保資源的正確釋放或其他必要的清理操作。 #...
Meta Keywords: finally, try, catch, java, system
-->

# 在 Java 中使用 "finally" 的完整指南

## 概述
在 Java 編程語言中，`finally` 是一個用於異常處理的關鍵字，它定義了一段代碼，無論是否發生異常，這段代碼都會被執行。它通常與 `try` 和 `catch` 塊搭配使用，以確保資源的正確釋放或其他必要的清理操作。

## 文檔
`finally` 區塊的主要目的是保證即使在異常發生的情況下，特定的代碼仍然會被執行。在 Java 中，異常處理通常使用 `try-catch` 結構來捕獲和處理異常，`finally` 區塊通常用於清理代碼，例如關閉文件流或釋放資源。

### 用法
以下是 `finally` 的基本語法結構：

```java
try {
    // 可能會拋出異常的代碼
} catch (ExceptionType e) {
    // 處理異常的代碼
} finally {
    // 總是執行的代碼
}
```

在 `try` 區塊中，開發者可以放置可能會引發異常的代碼。如果發生異常，則控制權將轉移到相應的 `catch` 區塊，然後無論是否發生異常，`finally` 區塊中的代碼都會執行。

## 範例
以下是一個基本的 `finally` 使用範例：

```java
import java.io.FileReader;
import java.io.IOException;

public class FinallyExample {
    public static void main(String[] args) {
        FileReader fr = null;
        try {
            fr = new FileReader("file.txt");
            // 進行文件操作
        } catch (IOException e) {
            System.out.println("捕獲到異常: " + e.getMessage());
        } finally {
            // 確保 FileReader 被關閉
            if (fr != null) {
                try {
                    fr.close();
                } catch (IOException e) {
                    System.out.println("關閉文件時出錯: " + e.getMessage());
                }
            }
            System.out.println("清理工作完成。");
        }
    }
}
```

在這個例子中，即使在 `try` 區塊中發生異常，`finally` 區塊中的代碼仍將執行，確保資源的正確釋放。

## 解釋
### 常見問題
1. **`finally` 是否會在 `System.exit()` 中執行？**
   - 如果在 `try` 或 `catch` 區塊中調用了 `System.exit()`，則 `finally` 區塊將不會執行。

2. **使用 `return` 語句時的行為？**
   - 如果在 `try` 或 `catch` 區塊中使用 `return`，`finally` 區塊仍然會執行。在這種情況下，`finally` 區塊的執行將發生在返回語句之前。

3. **可以不使用 `catch` 區塊嗎？**
   - 是的，可以僅使用 `try` 和 `finally`，但是這樣做的話，異常將不會被處理。

## 一句總結
在 Java 中，`finally` 區塊確保無論是否發生異常，特定的清理代碼都會被執行。