<!--
Meta Description: # Java中的"protected"存取修飾符 ## 概述 "protected" 是 Java 語言中的一種存取修飾符，用於控制變數和方法的可見性。使用 "protected" 修飾符可以讓成員在同一個包內或在子類中被訪問。 ## 文檔說明 在 Java 中，"protected" 修飾符的主要...
Meta Keywords: protected, java, child, public, class
-->

# Java中的"protected"存取修飾符

## 概述
"protected" 是 Java 語言中的一種存取修飾符，用於控制變數和方法的可見性。使用 "protected" 修飾符可以讓成員在同一個包內或在子類中被訪問。

## 文檔說明
在 Java 中，"protected" 修飾符的主要目的是提供比 "private" 更寬鬆的存取控制，卻又比 "public" 嚴格。當一個類的成員（變數或方法）被標記為 "protected" 時：
- 這個成員可以被同一個包中的其他類訪問。
- 這個成員也可以被任何子類（即使這些子類位於其他包中）訪問。

這樣的設計有助於實現封裝性和繼承性，允許子類擴展父類的功能。

### 用法
以下是使用 "protected" 的基本語法：
```java
protected dataType memberName;
```
在類中定義方法時，則如下：
```java
protected returnType methodName(parameters) {
    // 方法體
}
```

## 範例
以下是一個簡單的範例，演示如何使用 "protected" 修飾符：

```java
// 父類
class Parent {
    protected void display() {
        System.out.println("這是父類的方法");
    }
}

// 子類
class Child extends Parent {
    public void show() {
        display(); // 能夠訪問父類的 protected 方法
    }
}

// 主類
public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.show(); // 輸出: 這是父類的方法
    }
}
```

## 解釋
使用 "protected" 修飾符時，開發者需要注意以下幾點：
1. **包的影響**：如果子類與父類不在同一個包中，則只有子類中的成員才能訪問父類的 "protected" 成員。
2. **無法訪問**：在非子類且不在同一包內的類中，無法訪問 "protected" 成員。
3. **靜態成員**：靜態變數和靜態方法若被標記為 "protected"，則同樣遵循上述規則。

這些特性使 "protected" 成為一種靈活的存取控制機制，但也可能會導致誤解，特別是在大型應用程式中。

## 一句總結
在 Java 中，"protected" 修飾符允許類成員在同一包內及子類中被訪問，提供了靈活的存取控制。