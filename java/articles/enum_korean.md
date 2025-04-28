<!--
Meta Description: # JAVA의 Enum: 효율적인 상수 집합 관리 ## 개요 JAVA의 enum(열거형)은 상수 집합을 정의하고 관리하는 데 사용되는 특별한 데이터 타입입니다. enum을 사용하면 관련된 상수들을 그룹화하여 코드의 가독성을 높이고, 안전성을 강화할 수 있습니다. ## ...
Meta Keywords: enum, day, enum을, 있습니다, monday
-->

# JAVA의 Enum: 효율적인 상수 집합 관리

## 개요
JAVA의 enum(열거형)은 상수 집합을 정의하고 관리하는 데 사용되는 특별한 데이터 타입입니다. enum을 사용하면 관련된 상수들을 그룹화하여 코드의 가독성을 높이고, 안전성을 강화할 수 있습니다.

## 문서화
enum은 JAVA 5에서 도입된 기능으로, 상수 집합을 정의하는 데 유용합니다. 열거형은 클래스처럼 동작하며, 각 상수는 enum 타입의 인스턴스입니다. enum을 정의하는 기본 문법은 다음과 같습니다:

```java
enum EnumName {
    CONSTANT1,
    CONSTANT2,
    CONSTANT3;
}
```

### 목적
enum을 사용하면 코드 내에서 하드코딩된 상수를 피하고, 각 상수에 대해 타입 안전성을 확보할 수 있습니다. 또한, 코드의 유지보수성과 가독성을 높입니다.

### 사용법
enum을 사용하기 위해서는 다음 단계를 따릅니다:

1. enum 정의: 이름과 상수를 정의합니다.
2. enum 사용: switch 문이나 if 문 등에서 enum 값을 사용합니다.

## 예제
다음은 JAVA에서 enum을 사용하는 기본적인 예제입니다.

```java
// Enum 정의
enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}

// Enum 사용
public class EnumExample {
    Day day;

    public EnumExample(Day day) {
        this.day = day;
    }

    public void tellItLikeItIs() {
        switch (day) {
            case MONDAY:
                System.out.println("It's Monday!");
                break;
            case FRIDAY:
                System.out.println("It's Friday!");
                break;
            case SATURDAY: case SUNDAY:
                System.out.println("It's a weekend!");
                break;
            default:
                System.out.println("Looking forward to the Weekend!");
                break;
        }
    }

    public static void main(String[] args) {
        EnumExample firstDay = new EnumExample(Day.MONDAY);
        firstDay.tellItLikeItIs();
    }
}
```

## 설명
enum을 사용할 때 주의해야 할 점:

1. **상수의 순서**: enum 상수는 정의된 순서에 따라 정렬됩니다. 이 순서가 중요할 수 있으므로 주의해야 합니다.
2. **상수 추가**: 이미 사용 중인 enum에 새로운 상수를 추가하는 것은 기존 코드에 영향을 미칠 수 있습니다.
3. **비교**: enum 상수는 `==` 연산자로 비교할 수 있으며, `equals()` 메서드보다 성능이 좋습니다. 

특히, enum은 상속이 불가능하므로 다른 클래스를 상속받을 수 없습니다. 하지만 인터페이스를 구현할 수 있습니다.

## 한 줄 요약
JAVA에서 enum은 관련 상수 집합을 안전하게 관리하고 코드의 가독성을 높이는 강력한 도구입니다.