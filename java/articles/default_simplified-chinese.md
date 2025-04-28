<!--
Meta Description: # Java 中的 default 关键字详解 ## 摘要 在 Java 编程语言中，`default` 是一个关键字，主要用于接口中定义默认方法。这一特性使得接口能够提供方法的默认实现，从而增强了代码的灵活性与可维护性。 ## 文档 ### 目的 `default` 关键字允许在接口中定义具有具体...
Meta Keywords: default, java, public, animal, void
-->

# Java 中的 default 关键字详解

## 摘要
在 Java 编程语言中，`default` 是一个关键字，主要用于接口中定义默认方法。这一特性使得接口能够提供方法的默认实现，从而增强了代码的灵活性与可维护性。

## 文档
### 目的
`default` 关键字允许在接口中定义具有具体实现的方法。这使得开发者可以在不影响接口的实现类的情况下，向接口添加新方法。

### 用法
在 Java 中，使用 `default` 关键字时，必须在接口中声明一个方法，并提供其实现。语法如下：

```java
public interface InterfaceName {
    default void methodName() {
        // 默认实现
    }
}
```

实现该接口的类可以选择使用默认实现，或者重写该方法以提供自定义行为。

### 详细信息
- **版本要求**：`default` 关键字是在 Java 8 中引入的。
- **多继承**：如果一个类实现了多个接口，并且这些接口都定义了同名的默认方法，编译器将会报错。开发者需要在实现类中显式重写该方法来解决冲突。
- **接口可以包含**：除了默认方法，接口还可以包含静态方法、常量和抽象方法。

## 示例
以下是如何在接口中使用 `default` 关键字的示例：

```java
public interface Animal {
    default void sound() {
        System.out.println("动物发出声音");
    }
}

public class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("汪汪");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.sound();  // 输出: 汪汪
        
        Animal myAnimal = new Animal() {}; // 匿名类实现
        myAnimal.sound();  // 输出: 动物发出声音
    }
}
```

## 说明
- **常见误区**：许多开发者可能会误以为接口中的所有方法都必须是抽象的，但 `default` 方法的引入改变了这一点。
- **适用场景**：使用 `default` 方法可以帮助在不打破现有实现的情况下，向接口添加新功能。
- **不适用场景**：如果接口的设计不需要给出默认实现，则不应使用 `default`，因为这可能会导致不必要的复杂性。

## 一句话总结
Java 中的 `default` 关键字允许在接口中提供方法的默认实现，从而增强了接口的灵活性和可扩展性。