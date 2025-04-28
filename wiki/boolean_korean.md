<!--
Meta Description: # Java의 boolean: 데이터 타입과 사용법 ## 개요 Java에서 `boolean`은 참(true) 또는 거짓(false)의 두 가지 값 중 하나를 가질 수 있는 데이터 타입입니다. 이 기본 타입은 조건문, 반복문 등에서 조건을 평가할 때 필수적으로 사용됩니다...
Meta Keywords: boolean, false, true, java, 데이터
-->

# Java의 boolean: 데이터 타입과 사용법

## 개요
Java에서 `boolean`은 참(true) 또는 거짓(false)의 두 가지 값 중 하나를 가질 수 있는 데이터 타입입니다. 이 기본 타입은 조건문, 반복문 등에서 조건을 평가할 때 필수적으로 사용됩니다.

## 문서화
`boolean`은 Java의 기본 데이터 타입 중 하나로, 조건을 나타내기 위해 사용됩니다. `boolean` 타입의 변수는 두 가지 값, 즉 `true`와 `false`만 가질 수 있으며, 주로 조건문과 루프에서 사용되어 프로그램의 흐름을 제어합니다. 

### 사용법
- **변수 선언**: `boolean` 타입 변수는 `boolean` 키워드를 사용하여 선언합니다.
  ```java
  boolean isActive = true;
  ```
- **조건문**: `if` 문과 `switch` 문에서 조건을 평가하는 데 사용됩니다.
  ```java
  if (isActive) {
      System.out.println("활성화 상태입니다.");
  }
  ```
- **반복문**: `while` 루프와 같은 반복문에서도 사용되어 조건이 참일 때 반복을 수행합니다.
  ```java
  while (isActive) {
      // 반복 작업
  }
  ```

## 예제
### 예제 1: 기본적인 boolean 사용
```java
public class BooleanExample {
    public static void main(String[] args) {
        boolean isRaining = false;
        
        if (isRaining) {
            System.out.println("우산을 가져가세요.");
        } else {
            System.out.println("오늘은 우산이 필요하지 않습니다.");
        }
    }
}
```

### 예제 2: 반복문에서의 boolean 사용
```java
public class BooleanLoopExample {
    public static void main(String[] args) {
        boolean isRunning = true;
        int count = 0;
        
        while (isRunning) {
            count++;
            if (count > 5) {
                isRunning = false; // 루프 종료 조건
            }
        }
        
        System.out.println("루프가 " + count + "회 실행되었습니다.");
    }
}
```

## 설명
`boolean` 타입은 조건을 평가하는 데 매우 유용하지만, 몇 가지 주의해야 할 점이 있습니다:
- **기본값**: boolean 변수의 기본값은 `false`입니다.
- **비교 연산자**: `==`, `!=`, `<`, `>`, `<=`, `>=`와 같은 비교 연산자는 boolean 결과를 생성하지만, `boolean` 타입을 직접 사용할 때는 `if` 문이나 `while` 문 내에서 조건으로 사용해야 합니다.
- **객체와의 혼동**: `Boolean` 클래스는 `boolean`의 래퍼 클래스이며, null 값을 가질 수 있지만, 기본 `boolean` 타입은 null을 허용하지 않습니다.

## 한 줄 요약
Java의 `boolean` 데이터 타입은 참(true) 또는 거짓(false) 값을 가지며, 조건문과 반복문에서 프로그램의 흐름을 제어하는 데 필수적입니다.