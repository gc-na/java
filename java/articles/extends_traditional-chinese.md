<!--
Meta Description: # Java 中的 "extends" 關鍵字：繼承的力量 ## 摘要 在 Java 程式語言中，`extends` 關鍵字用於實現類別之間的繼承關係，讓一個類別可以繼承另一個類別的屬性和方法。這是物件導向程式設計的核心概念之一，可促進代碼重用與結構化設計。 ## 文檔 ### 目的 `extend...
Meta Keywords: extends, java, class, void, system
-->

# Java 中的 "extends" 關鍵字：繼承的力量

## 摘要
在 Java 程式語言中，`extends` 關鍵字用於實現類別之間的繼承關係，讓一個類別可以繼承另一個類別的屬性和方法。這是物件導向程式設計的核心概念之一，可促進代碼重用與結構化設計。

## 文檔
### 目的
`extends` 關鍵字的主要目的是建立一個子類別（子類）從父類別（超類）繼承屬性和方法。這使得子類可以重用父類的行為，並可以擴展或修改這些行為。

### 用法
在 Java 中，使用 `extends` 來定義一個子類別的語法如下：

```java
class 子類名 extends 父類名 {
    // 子類的屬性和方法
}
```

例如，假設我們有一個 `Animal` 類別，並想要創建一個 `Dog` 類別來繼承它，則可以這樣寫：

```java
class Animal {
    void speak() {
        System.out.println("動物發出聲音");
    }
}

class Dog extends Animal {
    void speak() {
        System.out.println("汪汪");
    }
}
```

### 詳細說明
- **單繼承**：Java 只允許類別進行單一繼承，即一個類別只能有一個直接父類。這是為了避免多重繼承可能引發的複雜性和衝突。
- **超類的屬性**：子類可以訪問父類的公共（public）和受保護（protected）屬性與方法，但無法直接訪問私有（private）屬性和方法。
- **方法覆寫**：子類可以覆寫父類的方法，以提供具體的實現，這是多態性的重要特徵。
- **呼叫父類方法**：在子類中，若需要呼叫父類的方法，可以使用 `super` 關鍵字。

## 範例
以下是一個更完整的範例，展示 `extends` 的使用：

```java
class Vehicle {
    void start() {
        System.out.println("車輛啟動");
    }
}

class Car extends Vehicle {
    void start() {
        super.start(); // 呼叫父類方法
        System.out.println("汽車啟動");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();
        myCar.start();
    }
}
```

### 輸出結果：
```
車輛啟動
汽車啟動
```

## 解釋
- **常見陷阱**：
  - 確保不會在子類中意外隱藏父類的方法，這可能導致意外的行為。
  - 使用 `super` 呼叫父類的構造函數時，必須在子類構造函數的第一行進行呼叫。

- **其他注意事項**：
  - 如果父類是 `final`，則無法繼承該類別。
  - 如果子類不明確指定父類，則自動繼承自 `Object` 類別。

## 一句總結
在 Java 中，`extends` 關鍵字用於建立類別之間的繼承關係，使得子類可以重用和擴展父類的功能。