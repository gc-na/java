<!--
Meta Description: # JAVA의 "return" 키워드: 함수와 메서드에서의 사용법 ## 개요 JAVA 프로그래밍 언어에서 "return" 키워드는 함수나 메서드의 실행을 종료하고, 호출한 곳으로 값을 반환하는 데 사용됩니다. 이 키워드는 프로그래밍의 흐름을 제어하며, 함수의 결과를 다...
Meta Keywords: return, int, void, 메서드, 메서드의
-->

# JAVA의 "return" 키워드: 함수와 메서드에서의 사용법

## 개요
JAVA 프로그래밍 언어에서 "return" 키워드는 함수나 메서드의 실행을 종료하고, 호출한 곳으로 값을 반환하는 데 사용됩니다. 이 키워드는 프로그래밍의 흐름을 제어하며, 함수의 결과를 다른 부분에서 사용할 수 있게 합니다.

## 문서화
"return" 키워드는 JAVA의 모든 메서드에서 필수적으로 사용될 수 있으며, 메서드의 반환 타입에 따라 다르게 적용될 수 있습니다. 메서드의 반환 타입이 `void`인 경우, "return" 키워드는 값을 반환하지 않고 단순히 메서드의 실행을 종료하는 데 사용됩니다. 반면, 특정 데이터 타입을 반환하는 메서드에서는 "return" 뒤에 해당 값이 명시되어야 합니다.

### 사용법
- **반환 타입이 void인 메서드**:
  ```java
  public void myMethod() {
      // 수행할 작업
      return; // 메서드 종료
  }
  ```

- **반환 타입이 있는 메서드**:
  ```java
  public int add(int a, int b) {
      return a + b; // 두 수의 합을 반환
  }
  ```

## 예제
아래의 예제는 "return" 키워드를 사용하는 두 가지 메서드를 보여줍니다.

```java
public class Example {
    // void 메서드
    public void printMessage() {
        System.out.println("Hello, World!");
        return; // 이 부분은 선택적
    }

    // int 반환 메서드
    public int multiply(int x, int y) {
        return x * y; // 두 수의 곱을 반환
    }

    public static void main(String[] args) {
        Example ex = new Example();
        ex.printMessage(); // 메시지 출력
        int result = ex.multiply(5, 3); // 5와 3의 곱을 계산
        System.out.println("결과: " + result); // 결과 출력
    }
}
```

## 설명
"return" 키워드를 사용할 때 주의해야 할 점은 다음과 같습니다:
1. **메서드 반환 타입과의 일치**: 반환하는 값의 타입이 메서드의 정의된 반환 타입과 일치해야 합니다. 예를 들어, 메서드가 `int` 타입을 반환하도록 정의되었다면, 반드시 `int` 값을 반환해야 합니다.
2. **void 메서드에서의 사용**: `void` 반환 타입의 메서드에서는 "return" 키워드를 사용할 수 있지만, 반드시 필요한 것은 아닙니다. 메서드가 끝나면 자동으로 종료되기 때문입니다.
3. **여러 개의 return 문**: 메서드 내에 여러 개의 "return" 문이 있을 수 있으나, 조건문에 따라 어떤 "return"이 실행될지 주의해야 합니다. 모든 경로에서 값이 반환되지 않으면 컴파일 오류가 발생합니다.

## 한 문장 요약
JAVA에서 "return" 키워드는 메서드의 실행을 종료하고, 값을 호출한 곳으로 반환하는 데 사용되는 필수적인 키워드입니다.