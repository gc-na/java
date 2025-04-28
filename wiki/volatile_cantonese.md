<!--
Meta Description: # Java中的volatile關鍵字：理解佢嘅作用同用法 ## 概述 `volatile`係Java編程語言中一個重要嘅關鍵字，主要用於多執行緒環境下，確保變量嘅可見性同執行順序，避免因為緩存導致數據不一致。 ## 文檔 ### 目的 `volatile`關鍵字用來修飾變量，確保所有執行緒對該變量...
Meta Keywords: volatile, thread, flag, true, public
-->

# Java中的volatile關鍵字：理解佢嘅作用同用法

## 概述
`volatile`係Java編程語言中一個重要嘅關鍵字，主要用於多執行緒環境下，確保變量嘅可見性同執行順序，避免因為緩存導致數據不一致。

## 文檔
### 目的
`volatile`關鍵字用來修飾變量，確保所有執行緒對該變量嘅寫入同讀取都能夠即時反映到主內存中，避免使用本地緩存引起嘅數據不一致問題。

### 用法
當你將一個變量聲明為`volatile`，Java虛擬機（JVM）會確保：
- 當一個執行緒寫入該變量時，其他執行緒能立刻看到更新後嘅值。
- 讀取該變量時，會始終從主內存而非本地緩存中讀取。

### 詳細信息
1. **可見性**：`volatile`確保變量嘅最新值對所有執行緒可見。
2. **禁止指令重排序**：使用`volatile`可以防止指令重排序，確保代碼執行順序。
3. **不支持原子性**：雖然`volatile`能確保可見性，但對於複雜操作（如遞增）唔提供原子性保障。

## 示例
以下係一個簡單嘅使用示例：

```java
public class VolatileExample {
    private static volatile boolean flag = false;

    public static void main(String[] args) {
        Thread t1 = new Thread(() -> {
            while (!flag) {
                // 等待flag變為true
            }
            System.out.println("Thread 1: Flag is true!");
        });

        Thread t2 = new Thread(() -> {
            flag = true; // 改變flag的值
            System.out.println("Thread 2: Flag has been set to true!");
        });

        t1.start();
        t2.start();
    }
}
```

## 解釋
- **常見陷阱**：雖然`volatile`可以保證變量的可見性，但對於多個變量之間的關係，`volatile`並不能保證原子性。例如，對於遞增操作（`count++`），你需要使用`synchronized`來確保原子性。
- **不適用於所有情況**：`volatile`適合於簡單狀態標誌，但對於需要複雜狀態管理的情況，應考慮使用其他同步工具，如`Atomic`類或`Locks`。

## 一句總結
在Java中，`volatile`關鍵字用於確保變量在多執行緒環境下嘅可見性同執行順序，但唔提供原子性保障。