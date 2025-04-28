<!--
Meta Description: # JAVA 中的 Record：簡化資料結構的語法糖 ## 概述 在 JAVA 14 中引入的 Record 是一種新型別，用於簡化不可變資料類別的創建。透過 Record，開發者可以更方便地定義資料載體，並自動生成必要的方法，如 getters、hashCode() 和 equals()。 ##...
Meta Keywords: record, java, point, int, system
-->

# JAVA 中的 Record：簡化資料結構的語法糖

## 概述
在 JAVA 14 中引入的 Record 是一種新型別，用於簡化不可變資料類別的創建。透過 Record，開發者可以更方便地定義資料載體，並自動生成必要的方法，如 getters、hashCode() 和 equals()。

## 文件說明
### 目的
Record 的目的是減少樣板代碼，提高開發效率，特別是在需要儲存資料的類別中。使用 Record，可以輕鬆創建不可變的資料結構，並且具備良好的可讀性。

### 用法
要定義一個 Record，只需使用 `record` 關鍵字，後接類別名稱及其欄位。Record 自動提供許多功能，如：

- 自動生成欄位的 getter 方法
- 自動生成 `toString()` 方法
- 自動生成 `hashCode()` 和 `equals()` 方法

語法範例如下：
```java
record Person(String name, int age) {}
```

### 詳細說明
當創建 Record 時，所有的欄位都會被視為 `final`，這意味著它們的值在初始化後無法更改。Record 也不支持繼承，但可以實現介面。每個 Record 都隱含一個隱式的 constructor，允許傳入欄位值。

使用 Record 的好處包括：
- 減少樣板代碼
- 自動處理不可變性
- 增強資料結構的清晰度

### 注意事項
儘管 Record 為資料類別提供了許多便利，但仍需注意以下幾點：
- Record 不允許繼承其他類別，但可以實現介面。
- Record 的欄位必須是 `final`，一旦設置後無法更改。
- Record 不支持可變資料結構，應謹慎選擇使用場景。

## 範例
以下是使用 Record 的基本範例：

```java
record Point(int x, int y) {}

public class Main {
    public static void main(String[] args) {
        Point p1 = new Point(10, 20);
        System.out.println(p1); // 輸出: Point[x=10, y=20]
        
        // 獲取欄位值
        System.out.println("X Coordinate: " + p1.x());
        System.out.println("Y Coordinate: " + p1.y());
    }
}
```

## 總結
Record 是 JAVA 中用於簡化資料結構定義的強大工具，提供了良好的可讀性和自動化功能。透過 Record，開發者可以更簡單地創建不可變的資料類別，從而提升開發效率。

## 一句總結
JAVA 的 Record 提供了一種簡單的方式來創建不可變資料類別，減少樣板代碼並提高程式的可讀性。