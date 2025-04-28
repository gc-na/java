<!--
Meta Description: # Java中的“super”关键字详解 ## 概述 在Java编程语言中，`super`关键字用于引用父类的成员（属性和方法）。它在继承结构中扮演着重要的角色，帮助子类访问父类的功能和特性。 ## 文档 ### 目的 `super`关键字的主要目的是解决在子类中调用父类的构造函数、方法以及属性的需...
Meta Keywords: super, name, child, string, parent
-->

# Java中的“super”关键字详解

## 概述
在Java编程语言中，`super`关键字用于引用父类的成员（属性和方法）。它在继承结构中扮演着重要的角色，帮助子类访问父类的功能和特性。

## 文档
### 目的
`super`关键字的主要目的是解决在子类中调用父类的构造函数、方法以及属性的需求。当子类需要重用父类的功能或属性时，`super`显得尤为重要。

### 用法
1. **调用父类构造函数**：在子类的构造函数中，使用`super()`来调用父类的构造函数。
2. **访问父类方法**：在子类中，如果重写了父类的方法，可以通过`super.methodName()`调用父类的方法。
3. **访问父类属性**：在子类中，如果存在与父类同名的属性，可以使用`super.attributeName`来访问父类的属性。

### 细节
- `super`必须在子类构造函数的第一行调用。
- 如果父类没有无参构造函数，子类必须显式调用父类的构造函数。
- 使用`super`时，如果父类的属性和方法被子类重写，`super`依然可以访问到父类的原始实现。

## 示例
```java
class Parent {
    String name;

    Parent(String name) {
        this.name = name;
    }

    void display() {
        System.out.println("Parent name: " + name);
    }
}

class Child extends Parent {
    String name;

    Child(String parentName, String childName) {
        super(parentName);  // 调用父类构造函数
        this.name = childName;
    }

    void display() {
        super.display();  // 调用父类方法
        System.out.println("Child name: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child("ParentName", "ChildName");
        child.display();
    }
}
```

## 解释
- **常见陷阱**：在子类构造函数中忘记调用`super()`，会导致编译错误。
- **方法重写注意**：使用`super`调用父类方法时，确保调用的是正确的方法版本，避免意外的行为。
- **属性访问问题**：若父类和子类有同名属性，直接使用属性名会引用子类的属性，使用`super`可以明确访问父类的属性。

## 一句话总结
`super`关键字在Java中用于访问父类的构造函数、方法和属性，帮助子类复用父类的功能。