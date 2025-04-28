<!--
Meta Description: # Java 中的 "final" 關鍵字詳解 ## 概述 在 Java 程式語言中，`final` 是一個關鍵字，用於聲明變數、方法和類別，表示它們的不可變性或無法被繼承性。 ## 文檔 `final` 關鍵字用於確保變數、方法和類別的行為不會被更改。其主要目的如下： 1. **變數**：當變數被...
Meta Keywords: final, java, class, 這會導致編譯錯誤, void
-->

# Java 中的 "final" 關鍵字詳解

## 概述
在 Java 程式語言中，`final` 是一個關鍵字，用於聲明變數、方法和類別，表示它們的不可變性或無法被繼承性。

## 文檔
`final` 關鍵字用於確保變數、方法和類別的行為不會被更改。其主要目的如下：

1. **變數**：當變數被聲明為 `final` 時，這意味著其值只能被賦值一次，並且無法再被修改。
   
   ```java
   final int x = 10;
   // x = 20; // 這會導致編譯錯誤
   ```

2. **方法**：當方法被聲明為 `final` 時，這意味著該方法無法在子類中被覆寫（override）。

   ```java
   class Parent {
       final void display() {
           System.out.println("這是一個最終方法");
       }
   }

   class Child extends Parent {
       // void display() { // 這會導致編譯錯誤
       //     System.out.println("覆寫的方法");
       // }
   }
   ```

3. **類別**：當類別被聲明為 `final` 時，這意味著該類別無法被繼承。

   ```java
   final class FinalClass {
       // 這是一個最終類別
   }

   // class SubClass extends FinalClass { // 這會導致編譯錯誤
   // }
   ```

## 示例
以下是使用 `final` 的基本範例：

```java
public class FinalExample {
    final int constantValue = 100; // final 變數

    final void show() { // final 方法
        System.out.println("這是一個最終方法。");
    }
}

class TestFinal extends FinalExample {
    // void show() { // 這會導致編譯錯誤
    //     System.out.println("嘗試覆寫最終方法。");
    // }
}
```

## 解釋
在使用 `final` 時，有一些常見的陷阱和注意事項：

- **初始化**：`final` 變數必須在聲明時或在構造函數中初始化，否則會導致編譯錯誤。
- **靜態變數**：`static final` 變數通常用於定義常量，這些變數必須在聲明時初始化。
- **不適用於所有類型**：`final` 僅影響變數的引用，而不是其內容。例如，對於一個 `final` 的引用類型，對象內部的狀態仍然可以改變。

## 一句總結
在 Java 中，`final` 關鍵字用於聲明不可變的變數、無法被覆寫的方法，以及無法被繼承的類別。