<!--
Meta Description: # 在 Java 中使用 "throw" 語句的詳細說明 ## 概述 在 Java 語言中，`throw` 語句用於顯示地引發一個異常（Exception）。這使得開發者可以在程式中控制異常的拋出，並為特定的錯誤情況提供更具體的錯誤處理。 ## 文檔 `throw` 語句的主要目的是為了創建自定義的...
Meta Keywords: throw, java, exception, public, main
-->

# 在 Java 中使用 "throw" 語句的詳細說明

## 概述
在 Java 語言中，`throw` 語句用於顯示地引發一個異常（Exception）。這使得開發者可以在程式中控制異常的拋出，並為特定的錯誤情況提供更具體的錯誤處理。

## 文檔
`throw` 語句的主要目的是為了創建自定義的異常處理流程。當某個特定條件不滿足時，開發者可以使用 `throw` 關鍵字來引發異常，這樣可以使程序在遇到錯誤時更加健壯和可控。

### 使用方法
在 Java 中，`throw` 後面必須跟隨一個異常對象。這些異常對象可以是 Java 內置的異常類型，如 `NullPointerException`、`IllegalArgumentException`，也可以是開發者自定義的異常類別。

以下是 `throw` 語句的基本語法：
```java
throw new ExceptionType("錯誤資訊");
```

### 詳細說明
- **異常類型**：可以是任何繼承自 `Throwable` 類的類。通常使用的是 `Exception` 或其子類。
- **錯誤資訊**：在引發異常時，可以傳遞一個描述錯誤的消息，這對於調試十分有幫助。
- **檢查型與非檢查型異常**：Java 的異常分為檢查型異常（checked exception）和非檢查型異常（unchecked exception）。使用 `throw` 時，開發者需要注意異常的類型及其處理方式。

## 範例
以下是一些使用 `throw` 的基本範例：

### 範例1：引發內建異常
```java
public class Main {
    public static void main(String[] args) {
        try {
            checkAge(15);
        } catch (IllegalArgumentException e) {
            System.out.println("捕獲到異常: " + e.getMessage());
        }
    }

    static void checkAge(int age) {
        if (age < 18) {
            throw new IllegalArgumentException("年齡必須大於或等於18");
        }
    }
}
```

### 範例2：自定義異常
```java
class MyException extends Exception {
    public MyException(String message) {
        super(message);
    }
}

public class Main {
    public static void main(String[] args) {
        try {
            throw new MyException("這是一個自定義異常");
        } catch (MyException e) {
            System.out.println("捕獲到異常: " + e.getMessage());
        }
    }
}
```

## 解釋
在使用 `throw` 時，開發者應注意以下幾點常見問題：
- **異常未處理**：如果 `throw` 引發的異常未在當前方法中捕獲，則需要在方法聲明中使用 `throws` 關鍵字來告知調用者這可能會引發異常。
- **性能影響**：過度使用 `throw` 及異常處理可能會對性能造成影響，因此應在必要時使用。
- **使用自定義異常**：當需要傳遞特定的錯誤資訊時，自定義異常是非常有用的，可以提供更具體的錯誤上下文。

## 一句總結
在 Java 中，`throw` 語句用於顯示地引發異常，幫助開發者更好地控制錯誤處理流程。