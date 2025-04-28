<!--
Meta Description: # Java中的「super」關鍵字：功能與用法 ## 概述 在Java編程語言中，「super」是一個重要的關鍵字，用於訪問父類別的屬性和方法。它使得子類可以方便地存取父類的成員，支持繼承和多態的特性。 ## 文檔 ### 目的 「super」關鍵字的主要目的是提供對父類別成員的直接訪問，這在覆寫...
Meta Keywords: super, parent, class, system, out
-->

# Java中的「super」關鍵字：功能與用法

## 概述
在Java編程語言中，「super」是一個重要的關鍵字，用於訪問父類別的屬性和方法。它使得子類可以方便地存取父類的成員，支持繼承和多態的特性。

## 文檔
### 目的
「super」關鍵字的主要目的是提供對父類別成員的直接訪問，這在覆寫父類方法時特別有用。使用「super」，開發者可以清晰地指明調用父類的方法或屬性，避免與子類成員發生混淆。

### 用法
1. **訪問父類屬性**：
   當子類與父類有相同名稱的屬性時，可以使用「super.屬性名」方式來訪問父類的屬性。

2. **調用父類方法**：
   當子類覆寫了父類的方法，但需要在子類方法中調用父類的方法時，可以使用「super.方法名()」來實現。

3. **呼叫父類構造器**：
   在子類的構造器中，可以使用「super(參數)」來調用父類的構造器，以初始化父類的屬性。

### 詳細說明
- **語法**：
  ```java
  super.屬性名;
  super.方法名(參數);
  super(參數);
  ```
- **注意事項**：
  - 在子類的構造器中，使用「super」必須是第一行。
  - 如果父類沒有預設的構造器，則必須明確調用帶參數的構造器。

## 範例
### 訪問父類屬性
```java
class Parent {
    String name = "父類";
}

class Child extends Parent {
    String name = "子類";
    
    void display() {
        System.out.println("子類名稱: " + name); // 輸出子類名稱
        System.out.println("父類名稱: " + super.name); // 輸出父類名稱
    }
}
```

### 調用父類方法
```java
class Parent {
    void display() {
        System.out.println("父類方法");
    }
}

class Child extends Parent {
    void display() {
        super.display(); // 調用父類的方法
        System.out.println("子類方法");
    }
}
```

### 呼叫父類構造器
```java
class Parent {
    Parent() {
        System.out.println("父類構造器");
    }
}

class Child extends Parent {
    Child() {
        super(); // 呼叫父類構造器
        System.out.println("子類構造器");
    }
}
```

## 解釋
- **常見陷阱**：
  - 在子類中，若不小心覆寫了父類的方法，可能會導致無法訪問父類的屬性或方法，這時需小心使用「super」以免混淆。
  - 在多重繼承的情境中，Java不支持多重繼承，但若使用接口可導致方法解析的複雜性，需特別謹慎。

- **附加說明**：
  - 「super」關鍵字不僅限於方法和屬性，也可以用於訪問父類的嵌套類。
  - 在使用「super」時，開發者應該了解父類和子類的關係，以避免邏輯錯誤。

## 一句總結
「super」關鍵字在Java中用於訪問父類的屬性和方法，是實現繼承的重要工具。