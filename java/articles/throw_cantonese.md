<!--
Meta Description: # 在JAVA中使用的「throw」關鍵字 ## 簡介 「throw」是一個在JAVA程式語言中用來顯示地拋出異常（Exception）的關鍵字。它使開發者能夠在程式中指定異常情況，並將控制權轉移到異常處理器。 ## 文檔 ### 目的 「throw」關鍵字的主要目的是在程式運行時主動拋出異常，這樣...
Meta Keywords: throw, exception, illegalargumentexception, public, java
-->

# 在JAVA中使用的「throw」關鍵字

## 簡介
「throw」是一個在JAVA程式語言中用來顯示地拋出異常（Exception）的關鍵字。它使開發者能夠在程式中指定異常情況，並將控制權轉移到異常處理器。

## 文檔
### 目的
「throw」關鍵字的主要目的是在程式運行時主動拋出異常，這樣可以讓程式具備更好的錯誤處理能力。當某個條件不符合預期時，例如無效輸入或業務邏輯錯誤，開發者可以使用「throw」來拋出自定義或內建的異常。

### 使用方法
在JAVA中，使用「throw」的基本語法如下：
```java
throw new ExceptionType("Error Message");
```
這裡，`ExceptionType`可以是任何可拋出的異常類型，例如`IllegalArgumentException`或`NullPointerException`，而`"Error Message"`則是錯誤的描述信息。

### 詳細說明
- **異常類型**：可以使用自定義的異常類型，這需要創建一個繼承自`Exception`或其子類的類。
- **檢查型異常與非檢查型異常**：檢查型異常（Checked Exception）需要在方法聲明中使用`throws`關鍵字聲明，而非檢查型異常（Unchecked Exception）則不需要。
- **控制流**：拋出異常後，該方法的執行將立即終止，控制權會轉移到最近的異常處理器。

## 示例
以下是使用「throw」的基本範例：

```java
public class Example {
    public static void validateAge(int age) {
        if (age < 18) {
            throw new IllegalArgumentException("年齡必須大於或等於18歲");
        }
    }

    public static void main(String[] args) {
        try {
            validateAge(15);
        } catch (IllegalArgumentException e) {
            System.out.println("捕獲到異常: " + e.getMessage());
        }
    }
}
```

## 解釋
### 常見陷阱
- **未捕獲的異常**：如果使用「throw」拋出異常而沒有適當的異常處理，則程式會終止。開發者應該確保有對應的`try-catch`塊來處理可能的異常。
- **回傳型別不匹配**：對於檢查型異常，若方法聲明中未包含`throws`，將無法編譯。
- **自定義異常的使用**：使用自定義異常時，應確保提供清晰的錯誤信息，以便後續的錯誤排查。

## 一句話總結
「throw」關鍵字在JAVA中用於顯示地拋出異常，從而提高程式的錯誤處理能力。