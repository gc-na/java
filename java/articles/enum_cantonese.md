<!--
Meta Description: # JAVA 枚舉類型（Enum）完整指南 ## 簡介 在JAVA中，枚舉類型（Enum）是一種特殊的資料類型，用來定義一組常量，使程式碼更加可讀和易於維護。 ## 文檔 ### 目的 枚舉類型允許開發者定義一組固定的常量，這些常量可以是相關的類別。例如，可以用來表示顏色、星期幾、狀態等。 ### ...
Meta Keywords: day, enum, system, out, println
-->

# JAVA 枚舉類型（Enum）完整指南

## 簡介
在JAVA中，枚舉類型（Enum）是一種特殊的資料類型，用來定義一組常量，使程式碼更加可讀和易於維護。

## 文檔
### 目的
枚舉類型允許開發者定義一組固定的常量，這些常量可以是相關的類別。例如，可以用來表示顏色、星期幾、狀態等。

### 使用方法
要定義一個枚舉類型，可以使用`enum`關鍵字，後面跟著枚舉的名稱和常量列表。以下是基本的語法：

```java
enum EnumName {
    CONSTANT1,
    CONSTANT2,
    CONSTANT3
}
```

### 詳細說明
- **定義枚舉**：使用`enum`關鍵字來定義一個枚舉類型。
- **獲取枚舉值**：可以通過`EnumName.CONSTANT`來獲取枚舉的常量。
- **遍歷枚舉**：可以使用`values()`方法來遍歷所有的枚舉常量。
- **傳遞枚舉**：枚舉可以作為方法的參數和返回值。

## 範例
以下是一些基本的枚舉使用範例：

### 定義和使用枚舉
```java
enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}

public class TestEnum {
    Day day;

    public TestEnum(Day day) {
        this.day = day;
    }

    public void tellItLikeItIs() {
        switch (day) {
            case MONDAY:
                System.out.println("Mondays are bad.");
                break;
            case FRIDAY:
                System.out.println("Fridays are better.");
                break;
            case SATURDAY: case SUNDAY:
                System.out.println("Weekends are best.");
                break;
            default:
                System.out.println("Midweek days are so-so.");
                break;
        }
    }

    public static void main(String[] args) {
        TestEnum firstDay = new TestEnum(Day.MONDAY);
        firstDay.tellItLikeItIs();
    }
}
```

### 遍歷枚舉
```java
for (Day d : Day.values()) {
    System.out.println(d);
}
```

## 解釋
- **常見陷阱**：在使用枚舉時，避免在枚舉中使用非靜態方法或屬性，因為這可能會導致不必要的複雜性。
- **擴展性**：枚舉可以擴展，除了定義常量外，還可以為其添加屬性和方法。
- **比較**：枚舉常量是單例的，因此可以使用`==`來進行比較，而不需要使用`equals()`方法。

## 一句總結
JAVA的枚舉類型（Enum）提供了一種簡單而有效的方法來定義一組固定的常量，增強程式碼的可讀性和維護性。