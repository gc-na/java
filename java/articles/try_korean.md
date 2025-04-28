<!--
Meta Description: # Java의 try 문: 예외 처리의 핵심 ## 개요 Java에서 `try` 문은 예외 처리를 위한 중요한 구성 요소로, 프로그램 실행 중 발생할 수 있는 오류를 관리하고, 프로그램의 안정성을 높이는 데 기여합니다. ## 문서화 ### 목적 `try` 문은 예외를 감...
Meta Keywords: try, catch, 예외를, 예외가, system
-->

# Java의 try 문: 예외 처리의 핵심

## 개요
Java에서 `try` 문은 예외 처리를 위한 중요한 구성 요소로, 프로그램 실행 중 발생할 수 있는 오류를 관리하고, 프로그램의 안정성을 높이는 데 기여합니다.

## 문서화

### 목적
`try` 문은 예외를 감지하고 처리하기 위한 블록을 정의하여, 프로그램이 오류로 인해 중단되지 않도록 합니다. 사용자가 예상치 못한 상황에서도 프로그램이 정상적으로 작동할 수 있도록 돕습니다.

### 사용법
`try` 문은 다음과 같은 구조를 가집니다:

```java
try {
    // 예외가 발생할 수 있는 코드
} catch (ExceptionType e) {
    // 예외 처리 코드
} finally {
    // 항상 실행되는 코드 (선택 사항)
}
```

- **try 블록**: 예외가 발생할 가능성이 있는 코드를 포함합니다.
- **catch 블록**: 특정 예외가 발생했을 때 실행될 코드를 정의합니다. 여러 개의 catch 블록을 사용하여 다양한 예외를 처리할 수 있습니다.
- **finally 블록**: 예외 발생 여부와 관계없이 항상 실행되는 코드를 포함합니다. 주로 리소스 해제에 사용됩니다.

## 예제

### 기본 예제
다음은 `try` 문을 사용한 기본적인 예외 처리 예제입니다:

```java
public class TryExample {
    public static void main(String[] args) {
        try {
            int[] numbers = {1, 2, 3};
            System.out.println(numbers[3]); // ArrayIndexOutOfBoundsException 발생
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("인덱스 범위를 벗어났습니다: " + e.getMessage());
        }
    }
}
```

### 여러 개의 catch 블록 사용
여러 개의 예외를 처리하는 예제:

```java
public class MultiCatchExample {
    public static void main(String[] args) {
        try {
            String str = null;
            System.out.println(str.length()); // NullPointerException 발생
        } catch (NullPointerException e) {
            System.out.println("Null 객체에 접근했습니다.");
        } catch (Exception e) {
            System.out.println("예외가 발생했습니다: " + e.getMessage());
        }
    }
}
```

## 설명
`try` 문 사용 시 주의해야 할 점은 다음과 같습니다:

- **catch 블록의 순서**: 더 구체적인 예외를 우선적으로 처리해야 합니다. 일반적인 예외인 `Exception`을 먼저 작성하면 더 구체적인 예외가 처리되지 않을 수 있습니다.
- **finally 블록의 활용**: 데이터베이스 연결이나 파일 입출력과 같은 리소스를 사용하는 경우, `finally` 블록을 사용하여 항상 자원을 해제해야 합니다.
- **Unchecked Exceptions**: `RuntimeException`과 그 하위 클래스는 명시적으로 처리할 필요가 없지만, 프로그램의 안정성을 위해 적절히 처리하는 것이 좋습니다.

## 요약
Java의 `try` 문은 예외를 안전하게 처리하여 프로그램의 안정성을 높이는 방법입니다.