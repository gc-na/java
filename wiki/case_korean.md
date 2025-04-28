<!--
Meta Description: # Java의 switch-case 문: 조건 분기 처리의 핵심 ## 개요 Java의 `switch-case` 문은 주어진 표현식의 값에 따라 여러 조건 중 하나를 선택하여 실행하는 제어 구조입니다. `if-else` 문보다 간결하게 표현할 수 있으며, 특정 상황에서 ...
Meta Keywords: case, switch, break, dayname, 주어진
-->

# Java의 switch-case 문: 조건 분기 처리의 핵심

## 개요
Java의 `switch-case` 문은 주어진 표현식의 값에 따라 여러 조건 중 하나를 선택하여 실행하는 제어 구조입니다. `if-else` 문보다 간결하게 표현할 수 있으며, 특정 상황에서 코드의 가독성을 높이는 데 유용합니다.

## 문서화

### 목적
`switch-case` 문은 여러 조건을 검사하고, 해당 조건에 맞는 코드를 실행하기 위해 사용됩니다. 주로 정수형, 문자열, 열거형(enum) 등의 값을 기반으로 조건 분기를 처리합니다.

### 사용법
`switch-case` 문은 다음과 같은 형식으로 사용됩니다:

```java
switch (expression) {
    case value1:
        // value1에 해당하는 코드 블록
        break;
    case value2:
        // value2에 해당하는 코드 블록
        break;
    // 필요에 따라 추가 case 문
    default:
        // 모든 case에 해당하지 않을 때 실행되는 코드 블록
}
```

- **expression**: `switch`에서 평가할 값입니다.
- **case**: 각 조건을 나타내며, 주어진 값과 일치할 경우 해당 코드 블록이 실행됩니다.
- **break**: 코드 블록 실행 후 `switch` 문을 종료합니다. `break`가 없으면 다음 `case` 블록까지 실행됩니다.
- **default**: 주어진 값과 일치하는 `case`가 없을 때 실행되는 코드 블록입니다.

## 예제

```java
int day = 3;
String dayName;

switch (day) {
    case 1:
        dayName = "월요일";
        break;
    case 2:
        dayName = "화요일";
        break;
    case 3:
        dayName = "수요일";
        break;
    default:
        dayName = "주말";
        break;
}

System.out.println(dayName); // 출력: 수요일
```

## 설명
- `switch-case` 문을 사용할 때 주의해야 할 점은 `break` 문을 반드시 사용하는 것입니다. `break` 문이 없으면 프로그램이 다음 `case`로 계속 진행하여 원치 않는 동작을 초래할 수 있습니다.
- `switch` 문은 Java 7부터 문자열을 지원하게 되었으며, 이는 문자열 기반의 조건 분기에 매우 유용합니다.
- `case` 문에는 서로 다른 데이터 타입을 사용할 수 없으며, 각 `case`의 값은 반드시 고유해야 합니다.

## 한 줄 요약
Java의 `switch-case` 문은 주어진 표현식의 값에 따라 여러 조건 중 하나를 선택하여 실행하는 유용한 제어 구조입니다.