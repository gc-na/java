<!--
Meta Description: # Java中的密封類 (Sealed Classes) 的深入探討 ## 摘要 密封類是Java 15引入的一項語言特性，旨在提高類的繼承控制，允許開發者指定哪些類可以繼承自密封類，從而增強程式碼的可讀性和安全性。 ## 文檔 密封類的主要目的是為了限制某個類的繼承權限。通過使用密封類，開發者可以...
Meta Keywords: public, class, sealed, extends, final
-->

# Java中的密封類 (Sealed Classes) 的深入探討

## 摘要
密封類是Java 15引入的一項語言特性，旨在提高類的繼承控制，允許開發者指定哪些類可以繼承自密封類，從而增強程式碼的可讀性和安全性。

## 文檔
密封類的主要目的是為了限制某個類的繼承權限。通過使用密封類，開發者可以明確地指定哪些子類是允許的，這樣可以防止不必要的類擴展，並使API的設計更加清晰。在Java中，密封類使用`sealed`關鍵字來定義，並且必須指定允許繼承的子類。

### 語法
```java
public sealed class ParentClass permits ChildClass1, ChildClass2 {
    // 類的內容
}

public final class ChildClass1 extends ParentClass {
    // ChildClass1的內容
}

public non-sealed class ChildClass2 extends ParentClass {
    // ChildClass2的內容
}
```

### 目的
密封類的設計目的包括但不限於：
- 控制繼承：限制子類的數量及其功能。
- 提高安全性：減少不必要的擴展和範圍問題。
- 增強可讀性：讓API的設計更加明確，使用者可以快速理解哪些類是可擴展的。

## 範例
以下是密封類的基本使用範例：

### 範例 1：定義密封類
```java
public sealed class Shape permits Circle, Rectangle {
    // 形狀類的內容
}

public final class Circle extends Shape {
    // 圓形的內容
}

public final class Rectangle extends Shape {
    // 矩形的內容
}
```

### 範例 2：使用非密封子類
```java
public sealed class Vehicle permits Car, Bike {
}

public final class Car extends Vehicle {
}

public non-sealed class Bike extends Vehicle {
    // 自行車的內容
}
```

## 解釋
使用密封類時需要注意以下幾點：
- **繼承限制**：密封類只能被已明確允許的類繼承。如果嘗試從未被允許的類繼承，編譯器將報錯。
- **非密封子類**：在密封類中，可以使用`non-sealed`關鍵字來標記一個子類，這意味著該子類可以被進一步繼承。
- **性能考量**：雖然密封類在設計上提供了更清晰的繼承結構，但過度使用可能會影響性能，特別是在大型應用中。

## 一句總結
Java中的密封類是一種控制繼承的高效機制，允許開發者明確規範哪些類可以擴展，從而提升程式碼的安全性和可讀性。