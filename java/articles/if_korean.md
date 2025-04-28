<!--
Meta Description: # Java의 "if" 문: 조건부 실행의 기초 ## 개요 Java에서 "if" 문은 조건에 따라 코드 블록을 실행할 수 있게 해주는 제어문입니다. 이 문을 사용하면 프로그램의 흐름을 제어하고, 특정 조건이 충족될 때만 특정 작업을 수행하도록 할 수 있습니다. ## 문...
Meta Keywords: else, 조건이, 실행할, java, system
-->

# Java의 "if" 문: 조건부 실행의 기초

## 개요
Java에서 "if" 문은 조건에 따라 코드 블록을 실행할 수 있게 해주는 제어문입니다. 이 문을 사용하면 프로그램의 흐름을 제어하고, 특정 조건이 충족될 때만 특정 작업을 수행하도록 할 수 있습니다.

## 문서화
"if" 문은 Java의 기본적인 조건문으로, 주어진 조건이 참(true)일 때 특정 코드를 실행합니다. 이 문법은 프로그램의 의사결정을 가능하게 하며, 다양한 조건에 따라 다른 경로를 선택할 수 있게 해줍니다.

### 용법
- 기본 형식: 
  ```java
  if (조건) {
      // 조건이 true일 때 실행할 코드
  }
  ```
- "if-else" 형식: 
  ```java
  if (조건) {
      // 조건이 true일 때 실행할 코드
  } else {
      // 조건이 false일 때 실행할 코드
  }
  ```
- "if-else if-else" 형식: 
  ```java
  if (조건1) {
      // 조건1이 true일 때 실행할 코드
  } else if (조건2) {
      // 조건2가 true일 때 실행할 코드
  } else {
      // 위의 모든 조건이 false일 때 실행할 코드
  }
  ```

## 예제
### 기본 사용 예
```java
int number = 10;

if (number > 5) {
    System.out.println("number는 5보다 큽니다.");
}
```

### if-else 사용 예
```java
int number = 3;

if (number % 2 == 0) {
    System.out.println("number는 짝수입니다.");
} else {
    System.out.println("number는 홀수입니다.");
}
```

### if-else if-else 사용 예
```java
int score = 85;

if (score >= 90) {
    System.out.println("A 학점입니다.");
} else if (score >= 80) {
    System.out.println("B 학점입니다.");
} else {
    System.out.println("C 학점입니다.");
}
```

## 설명
"if" 문을 사용할 때 주의해야 할 점은 조건이 참으로 평가되면 해당 블록의 코드가 실행되고, 조건이 거짓일 경우에는 아무것도 실행되지 않는다는 것입니다. 또한, 괄호 안에 사용되는 조건은 반드시 Boolean 타입으로 평가되어야 하며, 여러 조건을 결합할 때는 논리 연산자(AND, OR 등)를 사용할 수 있습니다.

**일반적인 함정:**
- 조건문 안에 복잡한 논리를 넣다 보면 가독성이 떨어질 수 있습니다. 간단한 조건문으로 나누어 작성하는 것이 좋습니다.
- 코드 블록이 없거나 잘못된 중괄호 사용으로 인해 의도치 않은 흐름이 발생할 수 있습니다.

## 한 줄 요약
Java의 "if" 문은 조건에 따라 코드의 실행 흐름을 제어하는 중요한 제어문입니다.