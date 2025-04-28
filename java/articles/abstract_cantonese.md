<!--
Meta Description: # Java 中的抽象 (Abstract) － 了解抽象類別及介面 ## 概述 在 Java 編程中，抽象（Abstract）是一個強大的概念，用於定義不完全的類別及其行為，促進代碼的重用性和可擴展性。 ## 文檔 ### 目的 抽象類別和介面允許開發者定義一些方法的基本框架，而具體的實現則由子類...
Meta Keywords: void, java, abstract, animal, class
-->

# Java 中的抽象 (Abstract) － 了解抽象類別及介面

## 概述
在 Java 編程中，抽象（Abstract）是一個強大的概念，用於定義不完全的類別及其行為，促進代碼的重用性和可擴展性。

## 文檔
### 目的
抽象類別和介面允許開發者定義一些方法的基本框架，而具體的實現則由子類別來完成。這促進了多態性（Polymorphism），使代碼更加靈活和可維護。

### 使用方式
- **抽象類別**：使用 `abstract` 關鍵字來定義，不能實例化。可包含抽象方法（沒有實現）和具體方法（有實現）。
- **介面**：也可以看作是一種抽象類型，所有方法默認為抽象，並可包含常數和默認方法。

### 詳細說明
1. **抽象類別**：
   - 定義：一個包含至少一個抽象方法的類別。
   - 語法：
     ```java
     abstract class ClassName {
         abstract void abstractMethod(); // 抽象方法
         
         void concreteMethod() { // 具體方法
             // 實現
         }
     }
     ```

2. **介面**：
   - 定義：只包含抽象方法和常數的類型。
   - 語法：
     ```java
     interface InterfaceName {
         void method(); // 抽象方法
     }
     ```

## 範例
### 抽象類別範例
```java
abstract class Animal {
    abstract void makeSound(); // 抽象方法

    void eat() { // 具體方法
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Woof!");
    }
}

// 使用
Animal myDog = new Dog();
myDog.makeSound(); // 輸出: Woof!
myDog.eat(); // 輸出: This animal eats food.
```

### 介面範例
```java
interface Vehicle {
    void drive(); // 抽象方法
}

class Car implements Vehicle {
    public void drive() {
        System.out.println("Driving a car.");
    }
}

// 使用
Vehicle myCar = new Car();
myCar.drive(); // 輸出: Driving a car.
```

## 解釋
- **常見陷阱**：抽象類別不能被實例化，如果試圖這樣做，編譯器會報錯。確保子類別正確實現所有的抽象方法。
- **注意事項**：介面可以被多個類別實現，而一個類別只能繼承一個抽象類別。考慮使用介面來實現多重繼承的行為。

## 一句總結
Java 中的抽象提供了一種強大的方式來定義類別和介面的基本結構，促進代碼的靈活性和可重用性。