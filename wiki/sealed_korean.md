<!--
Meta Description: # Java의 Sealed 클래스: 기능과 활용 ## 개요 Java의 Sealed 클래스는 클래스 계층 구조에서 상속을 제어하는 기능입니다. 이를 통해 개발자는 어떤 클래스가 특정 클래스를 확장할 수 있는지를 명시적으로 정의할 수 있습니다. ## 문서화 Sealed 클...
Meta Keywords: sealed, 클래스를, 클래스의, 합니다, public
-->

# Java의 Sealed 클래스: 기능과 활용

## 개요
Java의 Sealed 클래스는 클래스 계층 구조에서 상속을 제어하는 기능입니다. 이를 통해 개발자는 어떤 클래스가 특정 클래스를 확장할 수 있는지를 명시적으로 정의할 수 있습니다.

## 문서화
Sealed 클래스는 Java 15에서 처음 도입되었으며, Java 17에서 정식으로 기능이 추가되었습니다. 이 기능은 클래스의 상속을 제한하여 코드의 안전성을 높이고, 유지보수를 용이하게 합니다. Sealed 클래스를 사용하면, 개발자는 허용된 하위 클래스만 정의할 수 있으며, 이는 코드의 예측 가능성을 증가시킵니다.

### 목적
- 상속을 명확히 제한하여 코드의 안정성을 강화합니다.
- 하위 클래스의 정의를 명시적으로 관리하여 유지보수를 쉽게 합니다.

### 사용법
Sealed 클래스를 정의하기 위해서는 클래스 선언 시 `sealed` 키워드를 사용하며, 하위 클래스는 `permits` 키워드를 통해 명시해야 합니다.

```java
public sealed class Shape permits Circle, Square {
    // 클래스 구현
}

public final class Circle extends Shape {
    // Circle 클래스의 구현
}

public final class Square extends Shape {
    // Square 클래스의 구현
}
```

## 예제
다음은 Sealed 클래스를 사용하는 간단한 예제입니다.

```java
public sealed class Vehicle permits Car, Truck {
    // Vehicle 클래스의 구현
}

public final class Car extends Vehicle {
    // Car 클래스의 구현
}

public final class Truck extends Vehicle {
    // Truck 클래스의 구현
}
```

위의 예제에서 `Vehicle`은 `Car`와 `Truck`만을 허용하는 Sealed 클래스입니다.

## 설명
Sealed 클래스를 사용할 때 주의해야 할 점은 다음과 같습니다:
- Sealed 클래스를 상속할 수 있는 하위 클래스는 반드시 `final`, `sealed`, 또는 `non-sealed`로 선언해야 합니다.
- Sealed 클래스를 잘못 사용하면 상속 구조가 복잡해질 수 있으므로, 설계 시 신중해야 합니다.
- Sealed 클래스를 사용하지 않는 경우와 비교하여 코드의 가독성이 떨어질 수 있으므로, 필요에 따라 사용해야 합니다.

## 한 줄 요약
Java의 Sealed 클래스는 상속을 명확히 제한하여 코드의 안정성과 유지보수성을 향상시키는 기능입니다.