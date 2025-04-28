<!--
Meta Description: # Java의 "default" 키워드: 기본값 및 사용법 ## 개요 Java에서 "default" 키워드는 주로 인터페이스에서 기본 메서드를 정의하는 데 사용됩니다. 이는 인터페이스를 구현하는 클래스가 반드시 해당 메서드를 오버라이드할 필요가 없음을 의미합니다. ##...
Meta Keywords: 메서드를, default, dog, public, animal
-->

# Java의 "default" 키워드: 기본값 및 사용법

## 개요
Java에서 "default" 키워드는 주로 인터페이스에서 기본 메서드를 정의하는 데 사용됩니다. 이는 인터페이스를 구현하는 클래스가 반드시 해당 메서드를 오버라이드할 필요가 없음을 의미합니다. 

## 문서화
"Default"는 Java 8부터 도입된 기능으로, 인터페이스의 유연성을 높이고 코드 재사용성을 향상시키기 위해 사용됩니다. 기본 메서드는 인터페이스에 정의되어 있으며, 이를 구현하는 클래스는 이 메서드를 선택적으로 오버라이드할 수 있습니다.

### 목적
- 코드의 유연성을 증가시킵니다.
- 기존 인터페이스에 새로운 메서드를 추가할 수 있는 방법을 제공합니다.
- 구현 클래스가 기본 구현을 사용할 수 있게 하여 개발 시간을 단축시킵니다.

### 사용법
기본 메서드를 정의하려면 인터페이스 내에서 `default` 키워드를 사용합니다. 사용 예시는 다음과 같습니다:

```java
public interface MyInterface {
    default void myDefaultMethod() {
        System.out.println("기본 메서드 실행");
    }
}
```

이를 구현하는 클래스는 기본 메서드를 호출하거나 필요에 따라 오버라이드할 수 있습니다.

## 예제
```java
// 인터페이스 정의
public interface Animal {
    default void sound() {
        System.out.println("소리를 내는 동물");
    }
}

// 인터페이스 구현
public class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("멍멍");
    }
}

// 메인 클래스
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // 출력: 멍멍

        Animal animal = new Dog();
        animal.sound(); // 출력: 멍멍
    }
}
```

위의 예제에서 `Dog` 클래스는 `Animal` 인터페이스를 구현하고, 기본 메서드 `sound()`를 오버라이드하여 자신만의 구현을 제공합니다.

## 설명
기본 메서드는 인터페이스에서 메서드의 기본 구현을 제공할 수 있으나, 다음과 같은 주의점이 있습니다:
- 기본 메서드는 다중 상속 상황에서 충돌이 발생할 수 있습니다. 여러 인터페이스에서 동일한 기본 메서드를 정의하면 명시적으로 어떤 메서드를 사용할 것인지 지정해야 합니다.
- 기본 메서드는 인터페이스의 타입을 유지하면서도 새로운 기능을 추가할 수 있는 유용한 방법입니다. 그러나 과도한 사용은 코드의 가독성을 해칠 수 있으므로 신중히 사용해야 합니다.

## 한 줄 요약
Java의 "default" 키워드는 인터페이스에서 기본 메서드를 정의하여 코드의 유연성과 재사용성을 높이는 데 사용됩니다.