<!--
Meta Description: # Java 中的 synchronized 關鍵字：確保線程安全的機制 ## 簡介 `synchronized` 是 Java 中的一個關鍵字，用於實現線程間的同步，確保同一時間只有一個線程能夠訪問特定的資源或代碼區域。這對於多線程應用程序來說至關重要，以防止數據損壞和不一致性。 ## 文檔 ##...
Meta Keywords: synchronized, public, java, count, void
-->

# Java 中的 synchronized 關鍵字：確保線程安全的機制

## 簡介
`synchronized` 是 Java 中的一個關鍵字，用於實現線程間的同步，確保同一時間只有一個線程能夠訪問特定的資源或代碼區域。這對於多線程應用程序來說至關重要，以防止數據損壞和不一致性。

## 文檔
### 目的
`synchronized` 主要用於防止多個線程同時訪問某個方法或代碼區域，從而保護共享資源。當一個線程正在執行被 `synchronized` 修飾的方法或代碼時，其他線程必須等待，直到該線程完成其任務。

### 用法
`synchronized` 可以用於以下兩種情況：
1. **方法同步**：在方法聲明中使用 `synchronized`，以確保整個方法在同一時間內只能由一個線程執行。
2. **代碼塊同步**：在方法內部使用 `synchronized`，以特定的對象作為鎖，這樣只有持有該對象鎖的線程才能執行該代碼塊。

### 詳細說明
- **方法同步**：
  ```java
  public synchronized void synchronizedMethod() {
      // 代碼邏輯
  }
  ```
  這樣的寫法會鎖定當前對象的實例，確保同一時間只有一個線程可以執行此方法。

- **代碼塊同步**：
  ```java
  public void method() {
      synchronized (this) {
          // 代碼邏輯
      }
  }
  ```
  這樣的寫法鎖定了 `this` 對象，只有獲得鎖的線程才能執行代碼塊中的內容。

## 範例
以下是使用 `synchronized` 的基本範例：

### 方法同步範例
```java
public class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int getCount() {
        return count;
    }
}
```

### 代碼塊同步範例
```java
public class Counter {
    private int count = 0;

    public void increment() {
        synchronized (this) {
            count++;
        }
    }

    public int getCount() {
        synchronized (this) {
            return count;
        }
    }
}
```

## 解釋
使用 `synchronized` 時需要注意以下幾點：
- **性能影響**：過度使用 `synchronized` 可能導致性能下降，因為線程需要等待鎖的釋放。
- **死鎖**：如果多個線程相互等待對方釋放鎖，可能會導致死鎖現象。
- **可見性問題**： `synchronized` 不僅提供互斥性，還確保對共享變量的可見性，保證一個線程對變量的更改對其他線程可見。

## 一行總結
`synchronized` 是 Java 中用於保護共享資源的關鍵字，確保線程安全和數據一致性。