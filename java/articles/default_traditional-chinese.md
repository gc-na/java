<!--
Meta Description: # Java 中的 Default 關鍵字：深入解析與用法示例 ## 摘要 在Java中，`default`關鍵字主要用於接口中，為方法提供默認實現。這一特性自Java 8開始引入，旨在提高代碼的靈活性和可維護性。 ## 文檔 ### 目的 `default`關鍵字的使用允許開發者在接口中定義具有實...
Meta Keywords: default, dog, cat, sound, void
-->

# Java 中的 Default 關鍵字：深入解析與用法示例

## 摘要
在Java中，`default`關鍵字主要用於接口中，為方法提供默認實現。這一特性自Java 8開始引入，旨在提高代碼的靈活性和可維護性。

## 文檔
### 目的
`default`關鍵字的使用允許開發者在接口中定義具有實現的方法，這樣即便接口被實現類所使用，也不必強制要求這些類實現所有的方法，從而減少了重複代碼的撰寫。

### 用法
在Java接口中，使用`default`關鍵字來聲明一個默認方法，語法如下：

```java
interface InterfaceName {
    default void methodName() {
        // 方法實現
    }
}
```

當一個類實現這個接口時，它可以選擇覆寫這個默認方法，也可以使用接口中提供的默認實現。

### 詳細資訊
- **接口中的默認方法**：默認方法可以有方法體，這與傳統的接口不同，傳統接口只允許抽象方法。
- **多重繼承**：如果一個類實現了多個接口，且這些接口都定義了同名的默認方法，那麼該類必須覆寫這個方法以消除二義性。
- **兼容性**：默認方法的引入使得接口的版本控制變得更為簡單，開發者可以在不影響老版本的情況下對接口進行擴展。

## 範例
以下是使用`default`關鍵字的基本範例：

```java
interface Animal {
    default void sound() {
        System.out.println("動物發出聲音");
    }
}

class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("汪汪");
    }
}

class Cat implements Animal {
    // 使用默認方法
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // 輸出：汪汪

        Cat cat = new Cat();
        cat.sound(); // 輸出：動物發出聲音
    }
}
```

在上述範例中，`Dog`類覆寫了`sound`方法，而`Cat`類則使用了接口中定義的默認實現。

## 解釋
### 常見陷阱
- **方法衝突**：當實現多個接口時，若這些接口中有同名的默認方法，則實現類必須覆寫這些方法，否則編譯器將報錯。
- **不支持靜態方法**：`default`方法不能在接口中被聲明為靜態方法，這是Java語言的限制。

### 額外注意
使用`default`方法雖然能提高代碼的靈活性，但過度使用可能會導致接口的複雜性增加，因此建議在必要時使用。

## 一句總結
在Java中，`default`關鍵字允許接口定義默認方法實現，從而提升代碼的靈活性與可維護性。