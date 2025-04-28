<!--
Meta Description: # Java 中的 yield 關鍵字：用途與示例 ## 概述 在 Java 中，`yield` 是一個關鍵字，用於控制執行緒的執行順序。它可以幫助開發者在多執行緒環境中進行更細緻的執行緒管理，特別是在需要優化性能和資源使用時。 ## 文檔 ### 目的 `yield` 主要用於讓當前執行中的執行緒...
Meta Keywords: yield, java, thread, cpu, yieldexample
-->

# Java 中的 yield 關鍵字：用途與示例

## 概述
在 Java 中，`yield` 是一個關鍵字，用於控制執行緒的執行順序。它可以幫助開發者在多執行緒環境中進行更細緻的執行緒管理，特別是在需要優化性能和資源使用時。

## 文檔
### 目的
`yield` 主要用於讓當前執行中的執行緒暫時讓出 CPU 的執行權，讓其他同等優先級的執行緒有機會運行。這在多執行緒程序中能提高效率，尤其是當某些執行緒需要短暫的等待時間時。

### 用法
在 Java 中，`yield` 是一個靜態方法，屬於 `Thread` 類別。當一個執行緒調用 `Thread.yield()` 時，該執行緒會暫時放棄 CPU 的使用權，並進入就緒狀態，讓其他等待中的執行緒有機會運行。

### 詳細說明
`yield` 方法的行為取決於 Java 虛擬機（JVM）和操作系統的調度策略。並非所有的 JVM 實現都會完全遵循 `yield` 的意圖，因此在實際使用中，開發者應該謹慎應用此關鍵字。

## 示例
以下是使用 `yield` 的基本示例：

```java
class YieldExample extends Thread {
    public void run() {
        System.out.println(Thread.currentThread().getName() + " 開始執行");
        // 讓出當前執行緒的 CPU 時間
        Thread.yield();
        System.out.println(Thread.currentThread().getName() + " 繼續執行");
    }

    public static void main(String[] args) {
        YieldExample thread1 = new YieldExample();
        YieldExample thread2 = new YieldExample();
        
        thread1.start();
        thread2.start();
    }
}
```

在這個示例中，兩個執行緒會交替執行，並在適當的時候放棄 CPU 的使用權。

## 解釋
- **常見陷阱**：`yield` 並不保證當前執行緒會立刻讓出 CPU，具體取決於執行緒調度器的實現。
- **注意事項**：在某些情況下，頻繁使用 `yield` 可能會導致性能下降，因為調度器需要更多的時間來管理執行緒的狀態。

## 總結
`yield` 是 Java 中用於控制執行緒執行順序的關鍵字，能夠幫助開發者在多執行緒環境中優化資源使用。