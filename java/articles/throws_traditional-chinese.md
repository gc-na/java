<!--
Meta Description: # Java 中的 "throws" 關鍵字 ## 摘要 在 Java 中，"throws" 關鍵字用於方法聲明中，以指示該方法可能會拋出某種異常，從而允許調用者處理這些異常。 ## 文檔 "throws" 關鍵字主要用於異常處理。當一個方法可能會導致異常發生時，可以在方法的聲明中使用 "throw...
Meta Keywords: throws, java, ioexception, public, void
-->

# Java 中的 "throws" 關鍵字

## 摘要
在 Java 中，"throws" 關鍵字用於方法聲明中，以指示該方法可能會拋出某種異常，從而允許調用者處理這些異常。

## 文檔
"throws" 關鍵字主要用於異常處理。當一個方法可能會導致異常發生時，可以在方法的聲明中使用 "throws" 來告訴調用該方法的代碼，該方法不會處理這些異常，而是將其拋出，讓調用者來處理。

### 用法
在方法聲明中，"throws" 後面跟著一個或多個異常類型，用逗號分隔。這告訴編譯器和使用者，這些異常是該方法可能會拋出的。例如：

```java
public void myMethod() throws IOException, SQLException {
    // 方法實現
}
```

在以上示例中，myMethod 方法聲明它可能會拋出 IOException 和 SQLException 這兩種異常。如果調用者調用此方法，則必須使用 try-catch 語句來捕獲和處理這些異常。

## 範例
以下是使用 "throws" 的基本示例：

```java
import java.io.*;

public class ThrowsExample {
    public static void main(String[] args) {
        try {
            readFile("example.txt");
        } catch (IOException e) {
            System.out.println("發生IO異常: " + e.getMessage());
        }
    }

    public static void readFile(String fileName) throws IOException {
        FileReader file = new FileReader(fileName);
        BufferedReader br = new BufferedReader(file);
        String line;
        while ((line = br.readLine()) != null) {
            System.out.println(line);
        }
        br.close();
    }
}
```

在這個示例中，readFile 方法聲明它可能會拋出 IOException，因此在 main 方法中需要捕獲此異常。

## 解釋
使用 "throws" 時，有一些常見的注意事項：

1. **異常類型**：在使用 "throws" 時，必須確保所聲明的異常類型是檢查異常（checked exceptions），因為未檢查異常（unchecked exceptions）不需要使用 "throws" 進行聲明。

2. **多個異常**：可以在方法中使用 "throws" 聲明多個異常，但這會增加調用者處理異常的複雜性。

3. **異常處理**：調用該方法的代碼必須適當處理 "throws" 中聲明的異常，否則編譯器會報錯。

4. **方法重寫**：如果子類重寫一個父類的方法，則子類方法可以拋出父類方法聲明的異常，或是更具體的異常，但不能拋出更廣泛的異常。

## 一句總結
在 Java 中，"throws" 關鍵字用於聲明一個方法可能拋出的異常，協助調用者進行適當的異常處理。