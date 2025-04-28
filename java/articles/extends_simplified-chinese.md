<!--
Meta Description: # Java中的“extends”关键字详解 ## 概述 在Java编程语言中，“extends”关键字用于实现类的继承关系。它允许一个类继承另一个类的属性和方法，从而促进代码重用和逻辑组织。 ## 文档 ### 目的 “extends”关键字的主要目的是实现类之间的继承，使得子类可以继承父类的所有...
Meta Keywords: extends, dog, class, animal, void
-->

# Java中的“extends”关键字详解

## 概述
在Java编程语言中，“extends”关键字用于实现类的继承关系。它允许一个类继承另一个类的属性和方法，从而促进代码重用和逻辑组织。

## 文档
### 目的
“extends”关键字的主要目的是实现类之间的继承，使得子类可以继承父类的所有非私有（private）属性和方法。这种机制使得开发者能够创建更为复杂的类，同时保持代码的简洁性和可维护性。

### 用法
在Java中，定义一个类时，可以使用“extends”关键字来指定它所继承的父类。基本语法如下：

```java
class 子类名 extends 父类名 {
    // 子类的属性和方法
}
```

### 详细信息
- **单继承**: Java不支持多重继承，即一个子类只能继承一个父类。
- **构造函数**: 子类的构造函数必须调用父类的构造函数（通过使用`super()`），以确保父类的属性被正确初始化。
- **方法重写**: 子类可以重写（Override）父类的方法，以提供特定的实现。
- **访问修饰符**: 只有父类中非私有的属性和方法可以被子类访问。

## 示例
下面是一个简单的示例，展示了如何使用“extends”关键字：

```java
// 定义父类
class Animal {
    void eat() {
        System.out.println("动物在吃");
    }
}

// 定义子类
class Dog extends Animal {
    void bark() {
        System.out.println("狗在叫");
    }
}

// 主方法
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat(); // 调用继承自Animal类的方法
        dog.bark(); // 调用Dog类的方法
    }
}
```

在这个例子中，`Dog`类继承了`Animal`类，因此它可以访问`Animal`类的`eat()`方法。

## 说明
- **常见误区**: 有些初学者可能会误解“extends”的使用，认为子类可以访问父类的所有成员。实际上，只有非私有成员能被继承。
- **抽象类与接口**: 在使用“extends”时，子类可以继承抽象类，但不能直接继承接口。实现接口时使用“implements”关键字。
- **构造函数调用**: 子类的构造函数如果不显式调用父类构造函数，Java会自动调用父类的无参数构造函数。

## 一句话总结
“extends”关键字在Java中用于实现类的继承，使得子类能够继承父类的属性和方法，从而促进代码重用。