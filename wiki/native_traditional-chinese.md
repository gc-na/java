<!--
Meta Description: # Java 中的 native 關鍵字 ## 摘要 在 Java 編程語言中，`native` 關鍵字用於聲明一個方法是由本地代碼（通常是 C 或 C++）實現的，而不是用 Java 語言編寫的。這使得 Java 能夠調用系統級別的功能或使用現有的本地庫。 ## 文檔 ### 目的 `native...
Meta Keywords: java, native, public, jni, nativeexample
-->

# Java 中的 native 關鍵字

## 摘要
在 Java 編程語言中，`native` 關鍵字用於聲明一個方法是由本地代碼（通常是 C 或 C++）實現的，而不是用 Java 語言編寫的。這使得 Java 能夠調用系統級別的功能或使用現有的本地庫。

## 文檔
### 目的
`native` 關鍵字的主要目的是提供一種方式，使 Java 程式可以直接調用本地操作系統的功能，這在需要高性能或使用特定平台資源時特別有用。這通常通過 Java Native Interface (JNI) 實現。

### 用法
要聲明一個本地方法，您需要使用 `native` 關鍵字，並且不需要提供方法體。這通常在類的定義中進行。以下是用法示例：

```java
public class Example {
    // 聲明一個本地方法
    public native void nativeMethod();
}
```

### 詳細信息
- `native` 方法必須在 Java 程式內部聲明，但其實現必須在外部（C/C++）代碼中提供。
- 使用 `System.loadLibrary("libraryName")` 方法來加載本地庫。
- JNI 提供了一個豐富的 API 來支持 Java 和本地代碼之間的交互。
- 本地方法可以接受 Java 基本類型、對象、數組等作為參數，並且可以返回 Java 基本類型或對象。

## 示例
以下是一個簡單的示例，展示如何使用 `native` 關鍵字：

1. Java 類定義：

```java
public class NativeExample {
    static {
        System.loadLibrary("nativeLib");
    }
    
    public native int add(int a, int b);
}
```

2. C 語言實現（nativeLib.c）：

```c
#include <jni.h>
#include "NativeExample.h"

JNIEXPORT jint JNICALL Java_NativeExample_add(JNIEnv *env, jobject obj, jint a, jint b) {
    return a + b;
}
```

3. 使用方法：

```java
public class Main {
    public static void main(String[] args) {
        NativeExample example = new NativeExample();
        int result = example.add(5, 10);
        System.out.println("Result: " + result);
    }
}
```

## 解釋
- **常見陷阱**：
  - 確保本地庫的名稱與 Java 中的 `loadLibrary` 語句一致。
  - 不正確的 JNI 簽名會導致 `UnsatisfiedLinkError`。
  - 跨平台兼容性問題：確保本地代碼在不同操作系統上的適配。

- **備註**：
  - 使用 `native` 方法可能會影響程式的可移植性，因為本地代碼依賴於特定的操作系統和硬體。
  - 除非絕對必要，否則應盡量避免使用本地方法，以保持代碼的可讀性和可維護性。

## 簡單總結
`native` 關鍵字允許 Java 程式調用本地代碼，從而提供對系統功能的直接訪問。