<!--
Meta Description: # Java中的Sealed類型：功能、用途與範例 ## 概述 Sealed類型是Java 15引入的一項功能，旨在提供更精確的類型控制及繼承限制，讓開發者能夠定義哪些類別可以繼承一個特定的類型。這對於建立更加安全和可維護的代碼結構至關重要。 ## 文檔 Sealed類型的主要目的是為了控制類別的繼...
Meta Keywords: class, final, shape, extends, vehicle
-->

# Java中的Sealed類型：功能、用途與範例

## 概述
Sealed類型是Java 15引入的一項功能，旨在提供更精確的類型控制及繼承限制，讓開發者能夠定義哪些類別可以繼承一個特定的類型。這對於建立更加安全和可維護的代碼結構至關重要。

## 文檔
Sealed類型的主要目的是為了控制類別的繼承關係。通過使用sealed關鍵字，開發者可以指定哪些類別可以繼承該類型。這樣的設計有助於強化API的穩定性，並確保只有經過批准的子類型能夠擴展此類型。

### 用法
在Java中，使用sealed關鍵字來定義一個密封的類型。這個類型必須指定一個或多個允許繼承的類別，這些類別必須是同一個模組或包內的。以下是sealed類型的基本語法：

```java
sealed class Shape permits Circle, Square {
    // 類別內容
}

final class Circle extends Shape {
    // 類別內容
}

final class Square extends Shape {
    // 類別內容
}
```

在這個例子中，`Shape`是密封類型，只有`Circle`和`Square`這兩個類別被允許擴展它。

### 詳細說明
1. **密封類型（Sealed Classes）**：使用sealed關鍵字來定義，這樣的類型無法被隨意繼承，只有已明確許可的類別才能繼承。
2. **許可類型（Permitted Subclasses）**：這些類型必須在類定義中列出，並且必須是同一個包或模組中的類別。
3. **最終類型（Final Classes）**：被允許繼承的類別可以是final類型，這意味著它們不能再被繼承。

## 範例
以下是一個使用sealed類型的簡單範例：

```java
sealed class Vehicle permits Car, Bike {
    // Vehicle的屬性和方法
}

final class Car extends Vehicle {
    // Car的屬性和方法
}

final class Bike extends Vehicle {
    // Bike的屬性和方法
}
```

在這個例子中，`Vehicle`是一個密封類型，只允許`Car`和`Bike`作為其子類型。

## 解釋
- **常見陷阱**：如果嘗試讓未列出的類別繼承sealed類型，編譯器將會報錯。
- **模組限制**：所有的許可類型必須在同一個模組或包中，這可能會限制某些設計的靈活性。
- **兼容性問題**：在使用舊版Java的環境中，sealed類型可能無法正確工作，因此需要注意Java版本的兼容性。

## 一句總結
Java中的sealed類型允許開發者精確控制類別的繼承關係，從而增強代碼的安全性和可維護性。