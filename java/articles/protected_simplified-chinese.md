<!--
Meta Description: # Java中的“protected”关键字详解 ## 摘要 “protected”是Java中的访问修饰符之一，它用于控制类成员的可见性，允许子类和同一包中的其他类访问。 ## 文档 在Java中，`protected`修饰符用于定义类的字段、方法和构造函数的访问权限。被声明为`protected...
Meta Keywords: protected, public, child, package, com
-->

# Java中的“protected”关键字详解

## 摘要
“protected”是Java中的访问修饰符之一，它用于控制类成员的可见性，允许子类和同一包中的其他类访问。

## 文档
在Java中，`protected`修饰符用于定义类的字段、方法和构造函数的访问权限。被声明为`protected`的成员可以被以下三种情况的类访问：

1. **同一包中的类**：任何在同一包内的类都可以访问`protected`成员。
2. **子类**：任何继承了该类的子类，即使子类位于不同的包内，也可以访问`protected`成员。
3. **外部类**：在某些情况下，外部类的内部类也可以访问其`protected`成员。

### 用法
`protected`关键字通常在字段、方法或构造函数的声明中使用，语法如下：

```java
protected 数据类型 成员名称;
protected 返回类型 方法名称(参数列表) {
    // 方法体
}
```

## 示例
以下是一个`protected`关键字的基本用法示例：

```java
// 父类
package com.example;

public class Parent {
    protected void show() {
        System.out.println("这是父类的protected方法。");
    }
}

// 子类
package com.example;

public class Child extends Parent {
    public void display() {
        show(); // 访问父类的protected方法
    }
}

// 测试类
package com.example;

public class Test {
    public static void main(String[] args) {
        Child child = new Child();
        child.display(); // 输出: 这是父类的protected方法。
    }
}
```

## 解释
使用`protected`时，需要注意以下几点：

- **不允许公共访问**：`protected`成员不能被完全公共地访问，必须遵循包和继承的限制。
- **与默认访问修饰符的区别**：如果不指定访问修饰符，默认情况下，成员的访问权限仅限于同一包内的类，而`protected`允许跨包访问。
- **与private的区别**：`private`成员只能在其自身类中访问，而`protected`成员可以在子类和同一包中的其他类中访问。

## 一句话总结
`protected`是一个访问修饰符，它允许子类和同一包中的类访问类的成员。