<!--
Meta Description: # Java Record：Java 中的記錄類型 ## 簡介 在 Java 語言中，`record` 是一種特殊的類型，用於簡化數據載體的創建。這項功能於 Java 14 引入並在 Java 16 中正式成為標準特性，旨在提高數據的不可變性和簡化代碼的可讀性。 ## 文檔 `record` 類型的...
Meta Keywords: record, java, person, public, name
-->

# Java Record：Java 中的記錄類型

## 簡介
在 Java 語言中，`record` 是一種特殊的類型，用於簡化數據載體的創建。這項功能於 Java 14 引入並在 Java 16 中正式成為標準特性，旨在提高數據的不可變性和簡化代碼的可讀性。

## 文檔
`record` 類型的主要目的是提供一種簡單的方法來創建不可變的數據類型。使用 `record`，開發者可以輕鬆定義一個數據載體，無需顯示編寫 getter 方法、`equals`、`hashCode` 和 `toString` 方法，因為這些方法會自動生成。

### 使用方法
要定義一個記錄類型，只需使用 `record` 關鍵字，後跟類型名稱和屬性。以下是 `record` 的基本語法：

```java
public record RecordName(Type1 field1, Type2 field2) { }
```

### 詳細說明
- **不可變性**：一旦創建，記錄的屬性值不能被更改。這使得`record` 特別適合用於多線程環境。
- **簡化代碼**：`record` 自動生成所需的方法，開發者無需手動編寫，從而減少了樣板代碼的數量。
- **解構**：記錄類型支持直接解構，允許開發者快速訪問記錄中的元素。

## 示例
以下是創建和使用 `record` 的基本範例：

```java
public record Person(String name, int age) { }

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 30);
        System.out.println(person.name()); // 輸出: Alice
        System.out.println(person.age()); // 輸出: 30
        System.out.println(person); // 輸出: Person[name=Alice, age=30]
    }
}
```

## 解釋
使用 `record` 時需要注意以下幾點：
- **不支持繼承**：`record` 類型不能繼承其他類型，這限制了它們的使用範圍。
- **不支持可變性**：記錄的屬性是不可變的，因此在需要可變屬性的情況下，開發者需要考慮使用普通類別。
- **構造函數的使用**：雖然 `record` 自動生成了構造函數，但開發者仍然可以自定義構造函數來添加額外的驗證或邏輯。

## 總結
`record` 是 Java 中一種強大且簡便的數據載體類型，旨在提高代碼的可讀性和數據的安全性。