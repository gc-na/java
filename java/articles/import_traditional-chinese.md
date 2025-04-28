<!--
Meta Description: # Java 的 import 語句：有效管理類別和包的關鍵 ## 概述 在 Java 中，`import` 語句是用於引入其他類別或包的工具，這樣開發者就能夠在自己的程序中使用這些類別而不必使用完整的類別名稱。這不僅能提高代碼的可讀性，還能簡化開發過程。 ## 文檔 ### 目的 `import`...
Meta Keywords: java, import, public, string, static
-->

# Java 的 import 語句：有效管理類別和包的關鍵

## 概述
在 Java 中，`import` 語句是用於引入其他類別或包的工具，這樣開發者就能夠在自己的程序中使用這些類別而不必使用完整的類別名稱。這不僅能提高代碼的可讀性，還能簡化開發過程。

## 文檔
### 目的
`import` 語句的主要目的是使開發者能夠輕鬆訪問和使用其他類別和包，這樣可以促進代碼的重用性和組織性。

### 使用法
在 Java 中，`import` 語句通常放置於類別定義之前，並且可以引入單個類別、整個包或靜態成員。

#### 基本語法
1. 引入單個類別：
   ```java
   import packageName.ClassName;
   ```

2. 引入整個包：
   ```java
   import packageName.*;
   ```

3. 引入靜態成員：
   ```java
   import static packageName.ClassName.staticMember;
   ```

### 詳細說明
- `packageName` 是你想要引入的包的名稱。
- `ClassName` 是你想要引入的具體類別名稱。
- 使用 `*` 來表示引入該包中的所有類別，但這並不包括子包中的類別。
- 將靜態成員引入後，可以直接使用該成員的名稱，而不需要前綴類別名稱。

## 範例
### 引入單個類別
```java
import java.util.ArrayList;

public class Example {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Hello, World!");
        System.out.println(list.get(0));
    }
}
```

### 引入整個包
```java
import java.util.*;

public class Example {
    public static void main(String[] args) {
        HashMap<String, String> map = new HashMap<>();
        map.put("key", "value");
        System.out.println(map.get("key"));
    }
}
```

### 引入靜態成員
```java
import static java.lang.Math.PI;

public class Example {
    public static void main(String[] args) {
        System.out.println("圓周率是：" + PI);
    }
}
```

## 解釋
在使用 `import` 語句時，開發者需要注意以下幾點：
- 避免重名：如果兩個不同的包中有相同名稱的類別，則需要使用完整的類名來區分。
- 不要過度使用 `*`：雖然可以使用 `*` 引入整個包，但這樣會降低可讀性，並可能導致命名衝突。
- 順序問題：Java 編譯器在解析 `import` 語句時，會根據其出現的順序來解析類別，因此要注意引入的順序。

## 一句總結
`import` 語句在 Java 中是一個重要的工具，用於簡化類別和包的管理，提高代碼的可讀性和可維護性。