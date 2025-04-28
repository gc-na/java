<!--
Meta Description: # Java中的抽象類別和方法 (Abstract Classes and Methods in Java) ## 概要 在Java中，抽象類別和抽象方法是對物件導向程式設計的重要概念。它們允許開發者定義不完整的類別，並強制子類別實現特定的方法。 ## 文件說明 抽象類別是使用`abstract`關...
Meta Keywords: class, void, abstract, circle, rectangle
-->

# Java中的抽象類別和方法 (Abstract Classes and Methods in Java)

## 概要
在Java中，抽象類別和抽象方法是對物件導向程式設計的重要概念。它們允許開發者定義不完整的類別，並強制子類別實現特定的方法。

## 文件說明
抽象類別是使用`abstract`關鍵字聲明的類別，該類別不能被實例化。抽象方法是沒有實現的方法，僅有方法的聲明，必須在子類別中實現。

### 目的
抽象類別的主要目的是提供一個基礎類別，讓其他類別繼承並提供具體實現。這有助於減少代碼重複並促進代碼的可維護性。

### 使用方式
1. **定義抽象類別**:
   ```java
   abstract class Animal {
       abstract void sound(); // 抽象方法
   }
   ```

2. **實現抽象方法**:
   ```java
   class Dog extends Animal {
       void sound() {
           System.out.println("Woof");
       }
   }
   ```

3. **使用抽象類別**:
   ```java
   public class Main {
       public static void main(String[] args) {
           Animal myDog = new Dog();
           myDog.sound(); // 輸出: Woof
       }
   }
   ```

## 範例
以下是一個完整的使用抽象類別和方法的例子：

```java
abstract class Shape {
    abstract void draw(); // 抽象方法
}

class Circle extends Shape {
    void draw() {
        System.out.println("Drawing a Circle");
    }
}

class Rectangle extends Shape {
    void draw() {
        System.out.println("Drawing a Rectangle");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle();
        Shape rectangle = new Rectangle();
        
        circle.draw(); // 輸出: Drawing a Circle
        rectangle.draw(); // 輸出: Drawing a Rectangle
    }
}
```

## 解釋
使用抽象類別和方法時，開發者應注意以下幾點：
- 抽象類別不能被實例化。如果嘗試直接創建抽象類別的實例，將導致編譯錯誤。
- 抽象類別可以包含具體的方法和屬性，這意味著不必在每個子類別中重複相同的代碼。
- 子類別必須實現所有抽象方法，否則該子類別也必須被聲明為抽象。

## 一句總結
Java中的抽象類別和方法允許開發者定義不完整的類別，並強制子類別提供具體的實現，從而提高代碼的可維護性和可擴展性。