<!--
Meta Description: # Java 中的 "synchronized": 了解同步鎖的使用 ## 簡介 在 Java 編程中，`synchronized` 關鍵字用於實現線程安全，確保同一時間內只有一個線程可以執行某個特定的代碼區域。這對於多線程環境中的資源共享至關重要，可以防止數據不一致和競爭條件的發生。 ## 文檔說...
Meta Keywords: synchronized, java, public, counter, void
-->

# Java 中的 "synchronized": 了解同步鎖的使用

## 簡介
在 Java 編程中，`synchronized` 關鍵字用於實現線程安全，確保同一時間內只有一個線程可以執行某個特定的代碼區域。這對於多線程環境中的資源共享至關重要，可以防止數據不一致和競爭條件的發生。

## 文檔說明
### 目的
`synchronized` 關鍵字的主要目的是保護共享資源，防止多個線程同時訪問並修改該資源。這樣可以避免潛在的數據損壞和不一致性。

### 使用方式
`synchronized` 可以用於方法或代碼塊中。使用方法時，它會鎖定整個方法，而使用代碼塊時，則可以鎖定特定的對象。

1. **同步方法**：
   ```java
   public synchronized void synchronizedMethod() {
       // 這裡是需要保護的代碼
   }
   ```

2. **同步代碼塊**：
   ```java
   public void someMethod() {
       synchronized (this) {
           // 這裡是需要保護的代碼
       }
   }
   ```

### 詳細說明
- **鎖定對象**：當一個線程執行 `synchronized` 方法或代碼塊時，它會獲得該對象的鎖。其他試圖進入相同的 `synchronized` 方法或代碼塊的線程將被阻塞，直到鎖被釋放。
- **靜態同步方法**：如果使用 `synchronized` 在靜態方法上，則鎖定的是該類的 Class 對象，而不是實例對象。
  
```java
public static synchronized void staticSynchronizedMethod() {
   // 這裡是靜態同步方法的代碼
}
```

## 範例
以下是一個使用 `synchronized` 的基本範例：

```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public synchronized int getCount() {
        return count;
    }
}

public class Main {
    public static void main(String[] args) {
        Counter counter = new Counter();
        
        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) {
                counter.increment();
            }
        });

        t1.start();
        t2.start();

        try {
            t1.join();
            t2.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println("Final count: " + counter.getCount());
    }
}
```

## 解釋
### 常見陷阱
1. **死鎖**：如果不當使用 `synchronized`，可能會導致死鎖情況，特別是當多個線程互相等待對方釋放鎖時。
2. **性能影響**：過度使用 `synchronized` 可能會影響應用程序的性能，因為它會降低並行性。應謹慎使用，必要時考慮其他並發工具，如 `ReentrantLock`。
3. **可見性問題**：在 `synchronized` 代碼塊內部的變量對其他線程是可見的，但在外部代碼塊中的變量在沒有同步的情況下可能不會立即反映變化。

## 總結
Java 中的 `synchronized` 關鍵字是一種有效的線程同步機制，能夠確保在多線程環境中共享資源的安全性。