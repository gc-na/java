<!--
Meta Description: # Java 中的 "default" 關鍵字：用法與示例 ## 概述 在 Java 編程語言中，"default" 是一個關鍵字，主要用於接口中，表示接口的具體實現方法。這一特性使得開發者可以在不影響現有實現的情況下，為接口添加新方法。 ## 文檔 ### 目的 "Default" 關鍵字的引入旨...
Meta Keywords: default, public, java, void, sound
-->

# Java 中的 "default" 關鍵字：用法與示例

## 概述
在 Java 編程語言中，"default" 是一個關鍵字，主要用於接口中，表示接口的具體實現方法。這一特性使得開發者可以在不影響現有實現的情況下，為接口添加新方法。

## 文檔
### 目的
"Default" 關鍵字的引入旨在解決接口方法的演進問題。當需要在接口中添加新方法時，使用 "default" 可以為現有的接口提供默認實現，這樣不必強迫實現該接口的類去實現新增的方法。

### 用法
在 Java 中，"default" 關鍵字用於接口定義中，格式如下：

```java
public interface MyInterface {
    default void myDefaultMethod() {
        System.out.println("這是默認方法的實現");
    }
}
```

在這個例子中，`myDefaultMethod` 是 `MyInterface` 的一個默認實現，任何實現這個接口的類都可以選擇重寫這個方法，或者直接使用默認的實現。

### 詳細信息
- "default" 方法可以有方法體，這一特性是 Java 8 引入的。
- 默認方法可以被子類重寫，但如果子類實現了多個接口中相同的默認方法，則會出現衝突，需要進行顯式重寫。
- "default" 方法可以與 static 方法一起使用，並且可以在接口中定義多個默認方法。

## 示例
以下是一些基本的使用示例：

### 示例 1：接口中的默認方法
```java
public interface Animal {
    default void sound() {
        System.out.println("這是動物的聲音");
    }
}

public class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("汪汪!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // 輸出: 汪汪!
    }
}
```

### 示例 2：如果不重寫默認方法
```java
public class Cat implements Animal {
    // 不重寫 sound 方法
}

public class Main {
    public static void main(String[] args) {
        Cat cat = new Cat();
        cat.sound(); // 輸出: 這是動物的聲音
    }
}
```

## 解釋
### 常見陷阱和注意事項
- 確保在實現類中使用 "default" 方法時，理解其行為。如果重寫了默認方法，將不會調用接口中的原始實現。
- 如果多個接口有相同的默認方法，則在實現類中必須明確指定使用哪一個接口的方法，否則會導致編譯錯誤。
- "default" 方法不能在抽象類中使用，僅能在接口中使用。

## 一句總結
"Default" 關鍵字在 Java 中用於為接口提供默認方法的實現，使接口的擴展更具靈活性。