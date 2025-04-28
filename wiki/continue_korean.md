<!--
Meta Description: # Java의 continue 문: 제어 구조의 효율적인 활용 ## 개요 Java의 `continue` 문은 반복문 내에서 사용되어 현재 반복의 나머지 부분을 건너뛰고 다음 반복으로 넘어가게 하는 제어 구조입니다. 이 문은 효율적인 반복 흐름 제어를 가능하게 하여 코드...
Meta Keywords: continue, while, 반복으로, java, 넘어감
-->

# Java의 continue 문: 제어 구조의 효율적인 활용

## 개요
Java의 `continue` 문은 반복문 내에서 사용되어 현재 반복의 나머지 부분을 건너뛰고 다음 반복으로 넘어가게 하는 제어 구조입니다. 이 문은 효율적인 반복 흐름 제어를 가능하게 하여 코드의 가독성과 유지 보수성을 향상시킵니다.

## 문서화
`continue` 문은 주로 `for`, `while`, `do-while` 반복문과 함께 사용됩니다. 이 명령어는 특정 조건이 충족될 때 현재 반복을 중단하고 다음 반복으로 넘어가도록 지시합니다. 

### 목적
`continue` 문은 특정 조건을 만족할 때 불필요한 코드 실행을 피하고, 반복문을 더 간결하게 만들기 위해 사용됩니다.

### 사용법
`continue` 문은 다음과 같은 형식으로 사용됩니다:

```java
for (초기화; 조건; 증감) {
    if (조건문) {
        continue; // 조건이 참일 경우 다음 반복으로 넘어감
    }
    // 반복할 코드
}
```

또는 `while` 문에서도 다음과 같이 사용할 수 있습니다:

```java
while (조건) {
    if (조건문) {
        continue; // 조건이 참일 경우 다음 반복으로 넘어감
    }
    // 반복할 코드
}
```

## 예제
### 1. 기본 사용 예
다음은 `for` 문을 사용하여 1부터 10까지의 숫자 중 홀수만 출력하는 예제입니다:

```java
public class ContinueExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i % 2 == 0) {
                continue; // 짝수일 경우 다음 반복으로 넘어감
            }
            System.out.println(i); // 홀수만 출력
        }
    }
}
```

### 2. while 문에서의 사용 예
다음은 `while` 문을 사용하여 1부터 10까지의 숫자 중 짝수만 출력하는 예제입니다:

```java
public class WhileContinueExample {
    public static void main(String[] args) {
        int i = 1;
        while (i <= 10) {
            i++;
            if (i % 2 != 0) {
                continue; // 홀수일 경우 다음 반복으로 넘어감
            }
            System.out.println(i); // 짝수만 출력
        }
    }
}
```

## 설명
`continue` 문을 사용할 때 주의해야 할 점은 무한 루프에 빠질 수 있는 가능성입니다. 조건문이 항상 참으로 평가되면 반복문이 종료되지 않으므로, 적절한 조건을 설정하는 것이 중요합니다. 또한, `continue` 문은 현재 반복의 나머지 코드를 건너뛰기 때문에, 건너뛰는 코드가 중요한 경우에는 사용을 피해야 합니다.

## 한 줄 요약
Java의 `continue` 문은 조건에 따라 반복문의 현재 사이클을 건너뛰고 다음 사이클로 이동하는 제어 구조입니다.