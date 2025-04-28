<!--
Meta Description: # Java의 네이티브(native) 키워드: Java와 C/C++의 연동 ## 개요 Java의 `native` 키워드는 Java 코드와 네이티브 코드(예: C/C++) 간의 상호작용을 가능하게 하는 기능입니다. 이 키워드는 Java에서 정의된 메서드가 자바 가상 머신...
Meta Keywords: 네이티브, native, java, public, nativeexample
-->

# Java의 네이티브(native) 키워드: Java와 C/C++의 연동

## 개요
Java의 `native` 키워드는 Java 코드와 네이티브 코드(예: C/C++) 간의 상호작용을 가능하게 하는 기능입니다. 이 키워드는 Java에서 정의된 메서드가 자바 가상 머신(JVM) 외부에서 구현되어 있음을 나타냅니다. 

## 문서화
`native` 키워드는 주로 성능 최적화나 하드웨어 접근이 필요할 때 사용되며, Java Native Interface (JNI)를 통해 C/C++로 작성된 라이브러리와 연동할 수 있습니다. 네이티브 메서드는 Java 코드에서 호출되지만, 실제 구현은 JVM 외부에서 이루어집니다. 

### 목적
- 성능 향상: CPU 집약적인 작업이나 시스템 자원에 직접 접근할 필요가 있을 때 유용합니다.
- 기존 C/C++ 라이브러리 활용: 기존에 작성된 코드를 재사용하여 개발 시간을 단축할 수 있습니다.

### 사용법
네이티브 메서드를 정의할 때는 메서드 선언에 `native` 키워드를 추가합니다. 다음은 기본적인 사용 예입니다.

```java
public class NativeExample {
    static {
        System.loadLibrary("nativeLib"); // 네이티브 라이브러리 로드
    }

    public native int nativeMethod(); // 네이티브 메서드 선언
}
```

## 예제
아래는 C/C++로 구현된 네이티브 메서드와 Java 코드의 예시입니다.

### C/C++ 코드
```c
#include <jni.h>
#include "NativeExample.h"

JNIEXPORT jint JNICALL Java_NativeExample_nativeMethod(JNIEnv *env, jobject obj) {
    return 42; // 예시로 정수 42 반환
}
```

### Java 코드
```java
public class NativeExample {
    static {
        System.loadLibrary("nativeLib");
    }

    public native int nativeMethod();

    public static void main(String[] args) {
        NativeExample example = new NativeExample();
        System.out.println("Native method returned: " + example.nativeMethod());
    }
}
```

## 설명
- **JNI 사용**: JNI를 통해 Java와 네이티브 코드 간의 데이터 전환이 가능합니다. 그러나 JNI 사용은 복잡할 수 있으며, 메모리 관리에 주의해야 합니다.
- **성능 저하 가능성**: 네이티브 메서드를 호출하는 과정에서 JVM과의 컨텍스트 전환이 발생하므로, 성능이 저하될 수 있습니다. 따라서, 네이티브 메서드는 꼭 필요한 경우에만 사용해야 합니다.
- **플랫폼 의존성**: 네이티브 코드는 특정 플랫폼에 종속적이므로, 이식성이 떨어질 수 있습니다. 이는 Java의 플랫폼 독립성과 상반되는 요소입니다.

## 한 줄 요약
Java의 `native` 키워드는 네이티브 메서드를 정의하여 Java와 C/C++ 간의 상호작용을 가능하게 하는 키워드입니다.