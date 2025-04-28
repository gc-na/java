<!--
Meta Description: # Java 中的 "protected" 訪問修飾符：功能與用法 ## 概述 在 Java 語言中，`protected` 是一種訪問修飾符，用於控制對類成員（變量和方法）的訪問權限。它允許在同一包中，以及從其他包中的子類中訪問該成員。 ## 文檔 `protected` 訪問修飾符的主要目的在於...
Meta Keywords: protected, java, dog, void, animal
-->

# Java 中的 "protected" 訪問修飾符：功能與用法

## 概述
在 Java 語言中，`protected` 是一種訪問修飾符，用於控制對類成員（變量和方法）的訪問權限。它允許在同一包中，以及從其他包中的子類中訪問該成員。

## 文檔
`protected` 訪問修飾符的主要目的在於提供一種中級的訪問控制。具體來說，當一個類的成員被聲明為 `protected` 時，該成員可以在以下幾種情況下被訪問：

1. **同一包內的類**：如果兩個類在同一個包內，則它們可以訪問彼此的 `protected` 成員。
2. **子類**：即使子類位於不同的包中，它仍然可以訪問其父類的 `protected` 成員，這使得子類可以擴展或修改父類的行為。

### 使用方法
使用 `protected` 修飾符的基本語法如下：

```java
protected <dataType> <memberName>;
```

例如：

```java
protected int age;
protected void displayAge() {
    System.out.println("Age: " + age);
}
```

## 示例
以下是使用 `protected` 的基本示例：

```java
// 父類
class Animal {
    protected void sound() {
        System.out.println("Animal sound");
    }
}

// 子類
class Dog extends Animal {
    void bark() {
        sound(); // 可以訪問父類的 protected 方法
        System.out.println("Woof!");
    }
}

// 主類
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.bark();
    }
}
```

在這個例子中，`Dog` 類能夠訪問 `Animal` 類中的 `protected` 方法 `sound()`，從而實現了對父類行為的擴展。

## 解釋
使用 `protected` 訪問修飾符時，有幾個常見的陷阱和注意事項：

1. **不適用於非子類**：非子類即使在同一包內也無法訪問 `protected` 成員，這可能會導致一些設計上的困惑。
2. **包私有（default）的區別**：如果不使用任何訪問修飾符，則該成員的訪問權限是包私有，這意味著只有同一包內的類可以訪問，無法被子類訪問。
3. **設計考量**：過度使用 `protected` 可能會導致類之間的耦合增加，建議謹慎使用，以保持良好的設計原則。

## 總結
在 Java 中，`protected` 訪問修飾符允許在同一包和子類中訪問類成員，提供了靈活的訪問控制。