<!--
Meta Description: # Java中的密封类（sealed classes）及其使用 ## 概述 Java密封类（sealed classes）是Java 15引入的一项特性，旨在提供更严格的类继承控制，增强类型安全性。密封类允许开发者限制哪些类可以扩展该类，从而提高程序的可维护性和可读性。 ## 文档 密封类的主要目的...
Meta Keywords: sealed, public, class, non, final
-->

# Java中的密封类（sealed classes）及其使用

## 概述
Java密封类（sealed classes）是Java 15引入的一项特性，旨在提供更严格的类继承控制，增强类型安全性。密封类允许开发者限制哪些类可以扩展该类，从而提高程序的可维护性和可读性。

## 文档
密封类的主要目的是定义一个受限的类层次结构。通过使用密封类，开发者能够明确指定哪些子类是合法的，从而防止意外的扩展。密封类通过使用`sealed`关键字来声明，而允许扩展该类的子类需要使用`non-sealed`或`final`关键字。

### 用法
1. **声明密封类**：使用`sealed`关键字声明类，并在类声明后指定允许扩展的子类。
2. **定义子类**：在密封类的同一源文件中，使用`final`（不允许进一步扩展）或`non-sealed`（允许扩展）来定义子类。

### 详细信息
- **语法**：
  ```java
  public sealed class Parent permits Child1, Child2 {
      // 类体
  }

  public final class Child1 extends Parent {
      // 子类体
  }

  public non-sealed class Child2 extends Parent {
      // 子类体
  }
  ```

- **关键字**：
  - `sealed`：声明一个密封类。
  - `permits`：列出允许扩展该密封类的子类。
  - `final`：表示该子类不能被进一步扩展。
  - `non-sealed`：表示该子类可以被进一步扩展。

## 示例
以下是一个使用密封类的简单示例：

```java
// 声明一个密封类
public sealed class Shape permits Circle, Rectangle {
    // 类体
}

// 声明一个最终子类
public final class Circle extends Shape {
    // 子类体
}

// 声明一个非密封子类
public non-sealed class Rectangle extends Shape {
    // 子类体
}

// 声明一个进一步扩展的子类
public class Square extends Rectangle {
    // 子类体
}
```

在上面的例子中，`Shape`是一个密封类，`Circle`是一个最终子类，而`Rectangle`是一个非密封子类，它可以被进一步扩展。

## 说明
- **常见问题**：
  - 密封类只能在同一源文件中声明其子类。
  - 如果没有在`permits`中列出所有子类，编译器将报错。
  - `sealed`类不能是抽象类。
  
- **注意事项**：
  - 使用密封类可以提高代码的封装性和类型安全性，但过度使用可能会导致代码结构过于复杂。
  - 尽量在类的设计阶段就考虑是否需要使用密封类，以避免后续重构过程中的麻烦。

## 一句话总结
Java的密封类（sealed classes）功能提供了一种控制类继承关系的方法，增强了类型安全性。