<!--
Meta Description: # Java 類別 (Class) 的詳細介紹 ## 簡介 在 Java 程式語言中，「類別」（Class）是一種用來定義物件的藍圖。所有的物件都是透過類別來建立的，類別提供了物件的屬性和行為的定義。 ## 文件說明 類別是 Java 的核心概念之一，負責封裝數據和行為。使用類別可以創建物件，這些物...
Meta Keywords: java, class, car, model, year
-->

# Java 類別 (Class) 的詳細介紹

## 簡介
在 Java 程式語言中，「類別」（Class）是一種用來定義物件的藍圖。所有的物件都是透過類別來建立的，類別提供了物件的屬性和行為的定義。

## 文件說明
類別是 Java 的核心概念之一，負責封裝數據和行為。使用類別可以創建物件，這些物件可以具有狀態（屬性）和行為（方法）。類別可以從其他類別繼承，這樣可以重用代碼，並促進多態性。

### 目的
- 定義物件的屬性和行為。
- 實現代碼的重用和組織。

### 用法
在 Java 中，可以使用 `class` 關鍵字來定義一個類別。例如：

```java
public class Dog {
    String name;
    int age;

    void bark() {
        System.out.println("Woof!");
    }
}
```

在這個例子中，`Dog` 是一個類別，它有兩個屬性（`name` 和 `age`）和一個方法（`bark`）。

## 例子
以下是一個簡單的類別使用範例：

```java
public class Car {
    String model;
    int year;

    void displayInfo() {
        System.out.println("Model: " + model + ", Year: " + year);
    }

    public static void main(String[] args) {
        Car myCar = new Car();
        myCar.model = "Toyota";
        myCar.year = 2020;
        myCar.displayInfo(); // 輸出: Model: Toyota, Year: 2020
    }
}
```

在這個例子中，我們定義了一個 `Car` 類別，然後在 `main` 方法中創建了一個 `Car` 物件並顯示其資訊。

## 解釋
**常見陷阱：**
1. **未初始化的屬性**：如果類別屬性未被初始化，則會使用預設值（如數字為 0，布林為 false）。
2. **訪問修飾符**：類別的屬性和方法需要適當的訪問修飾符（如 `public`, `private`），以控制可見性。
3. **靜態與非靜態**：靜態方法和屬性屬於類別本身，而非靜態則屬於物件。理解這一點對於正確使用類別至關重要。

## 一句總結
Java 類別是一種定義物件藍圖的結構，封裝屬性和行為，實現代碼的重用和組織。