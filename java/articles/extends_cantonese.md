<!--
Meta Description: # 在 JAVA 中的 "extends" 關鍵字：繼承的基礎 ## 簡介 "extends" 是 JAVA 程式語言中用於類別繼承的重要關鍵字。它允許一個類別繼承另一個類別的屬性和方法，從而促進代碼重用和組織結構。 ## 文檔 在 JAVA 中，"extends" 關鍵字的主要目的是實現類別之間的...
Meta Keywords: extends, java, dog, class, parentclass
-->

# 在 JAVA 中的 "extends" 關鍵字：繼承的基礎

## 簡介
"extends" 是 JAVA 程式語言中用於類別繼承的重要關鍵字。它允許一個類別繼承另一個類別的屬性和方法，從而促進代碼重用和組織結構。

## 文檔
在 JAVA 中，"extends" 關鍵字的主要目的是實現類別之間的繼承。當一個類別使用 "extends" 關鍵字時，它便成為一個子類別（子類），而被繼承的類別則稱為父類別（超類）。這種關係使得子類可以使用父類的公有和保護成員（方法和屬性），同時還可以擴展或覆蓋這些成員，以實現特定的功能。

### 使用方式
在定義一個類別時，可以這樣使用 "extends" 關鍵字：
```java
class ParentClass {
    // 父類的屬性和方法
}

class ChildClass extends ParentClass {
    // 子類的屬性和方法
}
```
在這個例子中，`ChildClass` 繼承自 `ParentClass`，這意味著 `ChildClass` 可以訪問 `ParentClass` 中定義的公有和保護成員。

### 詳細說明
- **單繼承**：JAVA 不支持多重繼承，即一個類只能繼承一個父類，但可以實現多個介面。
- **覆寫方法**：子類可以使用 `@Override` 註解來覆寫父類的方法，這樣可以提供特定的實現。
- **構造函數**：子類的構造函數會自動調用父類的構造函數，除非使用 `super()` 明確指定其他構造函數。

## 例子
### 基本範例
```java
class Animal {
    void sound() {
        System.out.println("動物發出聲音");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("狗叫：汪汪！");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();  // 輸出：狗叫：汪汪！
    }
}
```
在這個範例中，`Dog` 類繼承自 `Animal` 類，並覆寫了 `sound()` 方法。

## 解釋
使用 "extends" 時，有幾個常見的注意事項：
- **父類的訪問權限**：子類只能訪問父類中公有（public）和保護（protected）層級的成員，私有（private）成員無法直接訪問。
- **構造函數的繼承**：子類必須顯式調用父類的構造函數，否則編譯器會自動調用無參數的構造函數。
- **父類的靜態方法**：靜態方法不能被覆寫，雖然子類可以定義同名的靜態方法。

## 一句總結
在 JAVA 中，"extends" 關鍵字用於實現類別的繼承，促進了代碼的重用與結構的清晰化。