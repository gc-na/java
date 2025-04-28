<!--
Meta Description: # Java 中的 "implements" 關鍵字：介面實現的全面指南 ## 概述 在 Java 程式語言中，“implements” 是一個關鍵字，用於類別實現介面。這個關鍵字允許開發者創建一個類別，並承諾實現介面中定義的所有方法。 ## 文檔 ### 目的 “implements” 關鍵字的主...
Meta Keywords: implements, java, public, class, animal
-->

# Java 中的 "implements" 關鍵字：介面實現的全面指南

## 概述
在 Java 程式語言中，“implements” 是一個關鍵字，用於類別實現介面。這個關鍵字允許開發者創建一個類別，並承諾實現介面中定義的所有方法。

## 文檔
### 目的
“implements” 關鍵字的主要目的是讓類別遵循某個介面的約定，確保該類別實現所有介面中聲明的方法。這是一種多重繼承的實現方式，因為 Java 不支援類別的多重繼承，但允許類別實現多個介面。

### 用法
在 Java 中使用 “implements” 的基本語法如下：

```java
class ClassName implements InterfaceName {
    // 實現介面中的方法
}
```

- `ClassName` 是你要創建的類別名稱。
- `InterfaceName` 是要實現的介面的名稱。

你可以同時實現多個介面，使用逗號分隔它們：

```java
class ClassName implements InterfaceOne, InterfaceTwo {
    // 實現介面中的方法
}
```

### 詳細介紹
當一個類別實現了一個介面時，它必須提供介面中所有抽象方法的具體實現。這樣可以確保所有使用該類別的代碼都能以一致的方式調用這些方法。

介面也可以繼承其他介面，類別在實現介面時需要實現所有繼承下來的抽象方法。

## 範例
以下是一個簡單的範例，展示如何使用 “implements” 關鍵字來實現介面：

```java
// 定義一個介面
interface Animal {
    void sound();
}

// 實現介面
class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Woof");
    }
}

class Cat implements Animal {
    @Override
    public void sound() {
        System.out.println("Meow");
    }
}

// 使用
public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound(); // 輸出: Woof

        Animal cat = new Cat();
        cat.sound(); // 輸出: Meow
    }
}
```

## 解釋
### 常見陷阱
1. **未實現所有方法**：如果類別沒有實現介面中所有的抽象方法，編譯器會報錯，提示需要實現這些方法。
2. **多重介面實現**：確保在實現多個介面時，沒有方法名稱衝突。若發生衝突，必須在類別中明確指定要實現哪一個介面的方法。

### 附加說明
- 介面中的方法預設為 `public` 和 `abstract`，不需要顯式聲明。
- 介面中的變數預設為 `public static final`，也不需要顯式聲明。

## 一行總結
“implements” 關鍵字用於 Java 類別實現介面，確保類別遵循介面的約定並實現其方法。