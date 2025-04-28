<!--
Meta Description: # Java中的finally關鍵字：用於異常處理的終結者 ## 概述 在Java中，`finally`關鍵字用於異常處理，確保無論是否發生異常，特定的代碼塊都會執行。它通常與`try`和`catch`語句一起使用，為資源釋放或清理工作提供了一個可靠的場所。 ## 文檔 ### 目的 `finall...
Meta Keywords: finally, try, catch, system, fis
-->

# Java中的finally關鍵字：用於異常處理的終結者

## 概述
在Java中，`finally`關鍵字用於異常處理，確保無論是否發生異常，特定的代碼塊都會執行。它通常與`try`和`catch`語句一起使用，為資源釋放或清理工作提供了一個可靠的場所。

## 文檔
### 目的
`finally`塊的主要目的是保證即使在異常發生的情況下，某些代碼仍然會被執行。這在處理資源（如文件或網絡連接）時尤其重要，因為即使發生錯誤，仍然需要釋放這些資源。

### 用法
`finally`塊通常與`try`和`catch`結合使用。語法如下：

```java
try {
    // 可能會引發異常的代碼
} catch (ExceptionType e) {
    // 處理異常的代碼
} finally {
    // 總是會執行的代碼
}
```

在這個結構中，`try`塊中的代碼會首先執行。如果該代碼引發了異常，則控制權會轉移到對應的`catch`塊。如果沒有異常發生，`catch`塊將被跳過。無論發生了什麼，`finally`塊中的代碼都會執行。

### 詳細信息
- `finally`塊是可選的，但在處理可能會引發異常的代碼時，推薦使用它。
- 如果在`try`塊或`catch`塊中遇到`System.exit()`或其他終止程序的操作，`finally`塊仍然會執行，除非程序被強制終止。
- `finally`塊可以用來關閉資源，例如關閉文件流或釋放數據庫連接。

## 範例
以下是使用`finally`的基本範例：

```java
import java.io.*;

public class FinallyExample {
    public static void main(String[] args) {
        FileInputStream fis = null;
        try {
            fis = new FileInputStream("test.txt");
            // 讀取文件內容
        } catch (FileNotFoundException e) {
            System.out.println("文件未找到: " + e.getMessage());
        } finally {
            if (fis != null) {
                try {
                    fis.close();
                    System.out.println("文件流已關閉");
                } catch (IOException e) {
                    System.out.println("關閉文件流時出錯: " + e.getMessage());
                }
            }
        }
    }
}
```

在此範例中，即使在讀取文件時發生異常，`finally`塊也會確保文件流被關閉。

## 解釋
- **常見陷阱**：若在`finally`塊中拋出異常，將會覆蓋在`try`或`catch`塊中發生的異常，這可能會使得原始異常信息丟失。
- **代碼可讀性**：過度使用`finally`可能會使代碼複雜化，因此應在確保清晰性的情況下使用。
- **資源管理**：對於資源管理，使用Java 7引入的`try-with-resources`語法是一個更簡單的選擇，因為它會自動關閉資源。

## 一行總結
`finally`關鍵字在Java中確保即使在發生異常的情況下，也能執行重要的清理代碼。