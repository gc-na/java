<!--
Meta Description: # Java 中的「static」關鍵字：定義、用法與示例 ## 概要 在 Java 程式設計中，「static」關鍵字用於定義靜態變數和靜態方法，使其不依賴於物件實例，而是屬於類別本身。本篇文章將深入探討「static」的用途與使用方式。 ## 文件說明 「static」關鍵字主要用於以下幾個方面...
Meta Keywords: static, java, staticcount, example, incrementcount
-->

# Java 中的「static」關鍵字：定義、用法與示例

## 概要
在 Java 程式設計中，「static」關鍵字用於定義靜態變數和靜態方法，使其不依賴於物件實例，而是屬於類別本身。本篇文章將深入探討「static」的用途與使用方式。

## 文件說明
「static」關鍵字主要用於以下幾個方面：

1. **靜態變數**：屬於類別，而非某個具體的物件。這意味著所有該類別的物件都共享同一個靜態變數。
2. **靜態方法**：可以直接通過類別名稱調用，而不需要創建類別的實例。靜態方法不能訪問非靜態的變數或方法。
3. **靜態區塊**：在類別加載時執行的程式碼區塊，用於初始化靜態變數。

### 用途
- 降低內存使用：靜態變數僅存儲一份。
- 提高程式的可讀性：可通過類別名稱直接訪問靜態方法。
- 初始化共享資源或執行類別層級的操作。

## 示例
以下是靜態變數與靜態方法的基本使用範例：

```java
public class Example {
    // 靜態變數
    static int staticCount = 0;

    // 靜態方法
    static void incrementCount() {
        staticCount++;
    }

    public static void main(String[] args) {
        // 調用靜態方法
        Example.incrementCount();
        System.out.println("靜態計數器: " + Example.staticCount);
    }
}
```

在此範例中，我們定義了一個靜態變數 `staticCount` 和一個靜態方法 `incrementCount()`，通過類別名稱直接調用靜態方法並輸出靜態變數的值。

## 解釋
在使用「static」時，有一些常見的陷阱和注意事項：

- **靜態方法無法訪問非靜態變數**：靜態方法屬於類別，無法引用實例變數。
- **靜態變數的共享性**：所有實例共享同一靜態變數，可能會導致意外的行為，尤其在多執行緒環境中。
- **靜態區塊執行順序**：靜態區塊在類別加載時執行，可能在主方法之前執行。

## 一行總結
Java 中的「static」關鍵字使變數和方法屬於類別而非實例，並提供了內存管理和可訪問性的優勢。