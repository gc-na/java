<!--
Meta Description: # Javaにおける「abstract」の完全ガイド ## 概要 Javaの「abstract」は、クラスやメソッドを定義する際に使用されるキーワードであり、抽象的な概念を表現します。これにより、共通のインターフェースを持つクラスの設計が可能となり、オブジェクト指向プログラミングの重要な要素である継...
Meta Keywords: abstract, void, class, shape, draw
-->

# Javaにおける「abstract」の完全ガイド

## 概要
Javaの「abstract」は、クラスやメソッドを定義する際に使用されるキーワードであり、抽象的な概念を表現します。これにより、共通のインターフェースを持つクラスの設計が可能となり、オブジェクト指向プログラミングの重要な要素である継承をサポートします。

## ドキュメンテーション
### 目的
「abstract」は、クラスまたはメソッドが具体的な実装を持たず、サブクラスで実装されることを示します。抽象クラスは、他のクラスが拡張（継承）するための基盤となり、抽象メソッドは、具象クラスで実装されるべきメソッドを定義します。

### 使用法
- **抽象クラス**: `abstract`キーワードを使用して宣言します。抽象クラスはインスタンス化できません。
- **抽象メソッド**: メソッドの宣言に`abstract`を付けることで、具象クラスでの実装を要求します。

### 詳細
1. **抽象クラスの定義**:
    ```java
    abstract class Animal {
        abstract void makeSound();
    }
    ```
2. **抽象メソッドの定義**:
    ```java
    abstract void makeSound();
    ```
   このメソッドは、`Animal`クラスを拡張するすべての具象クラスで実装される必要があります。

3. **使用例**:
    ```java
    class Dog extends Animal {
        void makeSound() {
            System.out.println("ワンワン");
        }
    }
    
    class Cat extends Animal {
        void makeSound() {
            System.out.println("ニャー");
        }
    }
    ```

## 例
以下は、抽象クラスと抽象メソッドを使用した基本的な例です。

```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    void draw() {
        System.out.println("円を描く");
    }
}

class Square extends Shape {
    void draw() {
        System.out.println("四角を描く");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle();
        circle.draw(); // 円を描く
        
        Shape square = new Square();
        square.draw(); // 四角を描く
    }
}
```

## 説明
- **インスタンス化不可**: 抽象クラスは直接インスタンス化できず、必ず具象クラスで実装される必要があります。
- **メソッドの実装**: 抽象メソッドには本体がないため、具象クラスで必ずオーバーライドする必要があります。
- **多重継承不可**: Javaではクラスの多重継承がサポートされていないため、抽象クラスを使用する際は注意が必要です。

## 一文要約
Javaの「abstract」は、抽象クラスやメソッドを定義し、オブジェクト指向プログラミングの継承を促進するためのキーワードです。