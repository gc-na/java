<!--
Meta Description: # Java의 Non-Sealed: 비봉인 클래스에 대한 이해 ## 개요 Java 17에서 도입된 `non-sealed`는 서브클래스의 계층 구조를 제어할 수 있는 새로운 키워드입니다. 이 키워드는 서브클래스가 더 이상 봉인되지 않도록 하여, 보다 유연하게 서브클래스를...
Meta Keywords: sealed, non, 클래스, public, class
-->

# Java의 Non-Sealed: 비봉인 클래스에 대한 이해

## 개요
Java 17에서 도입된 `non-sealed`는 서브클래스의 계층 구조를 제어할 수 있는 새로운 키워드입니다. 이 키워드는 서브클래스가 더 이상 봉인되지 않도록 하여, 보다 유연하게 서브클래스를 확장할 수 있도록 합니다.

## 문서화

### 목적
`non-sealed` 키워드는 Java의 봉인 클래스(sealed classes)와 함께 사용되어 서브클래스 확장을 허용합니다. 봉인 클래스는 특정 클래스만 서브클래스화할 수 있도록 제한하지만, `non-sealed`를 사용하면 그러한 제한을 해제할 수 있습니다.

### 사용법
`non-sealed` 키워드는 봉인된 클래스의 서브클래스에서 사용되며, 선언하는 방법은 다음과 같습니다:

```java
public sealed class Animal permits Dog, Cat {
    // 클래스 내용
}

public non-sealed class Dog extends Animal {
    // 클래스 내용
}

public final class Cat extends Animal {
    // 클래스 내용
}
```

위의 예제에서 `Animal`은 봉인된 클래스이고, `Dog`는 `non-sealed`로 선언되어 있어 다른 클래스가 `Dog`를 서브클래스화할 수 있습니다. 반면, `Cat`은 `final`로 선언되어 더 이상 확장이 불가능합니다.

## 예제

```java
public sealed class Shape permits Circle, Square {
    // 클래스 내용
}

public non-sealed class Circle extends Shape {
    // Circle 클래스 내용
}

public final class Square extends Shape {
    // Square 클래스 내용
}

// 새로운 서브클래스 생성 가능
public class Ellipse extends Circle {
    // Ellipse 클래스 내용
}
```

위 예제에서는 `Shape`가 봉인된 클래스이고, `Circle`은 `non-sealed`로 정의되어 있어 `Ellipse`와 같은 새로운 서브클래스를 만들 수 있습니다.

## 설명
`non-sealed`를 사용할 때 주의해야 할 점은 다음과 같습니다:

1. **계층 구조의 복잡성**: `non-sealed` 클래스를 사용하면 서브클래스 계층 구조가 복잡해질 수 있으므로, 설계 시 주의가 필요합니다.
2. **가독성**: 너무 많은 서브클래스를 생성하게 되면 코드의 가독성이 떨어질 수 있으므로, 적절한 사용이 중요합니다.
3. **상속의 위험성**: `non-sealed`로 선언된 클래스는 다른 클래스에 의해 무제한으로 확장될 수 있으므로, 기능과 의도를 명확히 해야 합니다.

## 한 줄 요약
Java의 `non-sealed`는 봉인 클래스의 서브클래스를 자유롭게 확장할 수 있도록 해주는 유용한 키워드입니다.