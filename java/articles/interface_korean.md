<!--
Meta Description: # 자바 인터페이스: 개념과 활용 ## 개요 자바 인터페이스는 클래스가 구현해야 하는 메서드의 청사진을 제공하는 특별한 타입입니다. 인터페이스를 사용하면 클래스 간의 관계를 정의하고 코드의 유연성을 높일 수 있습니다. ## 문서화 ### 목적 자바 인터페이스는 여러 클...
Meta Keywords: public, void, 인터페이스는, 인터페이스, 인터페이스를
-->

# 자바 인터페이스: 개념과 활용

## 개요
자바 인터페이스는 클래스가 구현해야 하는 메서드의 청사진을 제공하는 특별한 타입입니다. 인터페이스를 사용하면 클래스 간의 관계를 정의하고 코드의 유연성을 높일 수 있습니다.

## 문서화
### 목적
자바 인터페이스는 여러 클래스가 동일한 메서드 시그니처를 사용하도록 강제함으로써 다형성을 지원합니다. 인터페이스를 구현하는 클래스는 인터페이스에서 정의된 모든 메서드를 구현해야 하며, 이를 통해 코드의 일관성과 재사용성을 높일 수 있습니다.

### 사용법
인터페이스는 `interface` 키워드를 사용하여 정의됩니다. 인터페이스 내에서 메서드는 기본적으로 `public`과 `abstract`로 선언되며, 변수는 `public`, `static`, `final` 속성을 가집니다. 클래스는 `implements` 키워드를 사용하여 인터페이스를 구현합니다.

#### 인터페이스 정의 예시:
```java
public interface Animal {
    void makeSound();
    void eat();
}
```

#### 인터페이스 구현 예시:
```java
public class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("멍멍");
    }

    @Override
    public void eat() {
        System.out.println("개가 먹습니다.");
    }
}
```

## 예제
### 기본 사용 예
다음은 간단한 인터페이스와 이를 구현한 클래스의 예시입니다.

```java
public interface Vehicle {
    void start();
    void stop();
}

public class Car implements Vehicle {
    @Override
    public void start() {
        System.out.println("차가 출발합니다.");
    }

    @Override
    public void stop() {
        System.out.println("차가 멈춥니다.");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        myCar.start();
        myCar.stop();
    }
}
```

위의 코드에서 `Vehicle` 인터페이스는 `start()` 및 `stop()` 메서드를 정의하고, `Car` 클래스는 이를 구현하여 차량의 행동을 정의합니다.

## 설명
인터페이스를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- **다중 상속**: 자바는 클래스의 다중 상속을 지원하지 않지만, 인터페이스는 다중 구현이 가능합니다. 여러 인터페이스를 동시에 구현할 수 있습니다.
- **디폴트 메서드**: 자바 8부터 인터페이스는 디폴트 메서드를 가질 수 있습니다. 이는 인터페이스에 메서드 구현을 추가할 수 있는 기능입니다.
- **상수**: 인터페이스에서 정의된 변수는 자동으로 `public static final`로 간주되므로, 초기화가 필요합니다.

### 일반적인 실수
- 인터페이스에 메서드 구현을 추가할 수 없다는 것을 잊지 마십시오. 모든 메서드는 기본적으로 추상적입니다.
- 인터페이스는 인스턴스를 생성할 수 없다는 점에 유의하십시오. 인터페이스 타입의 변수를 선언할 수는 있지만, 그 자체로 객체를 생성할 수는 없습니다.

## 한 줄 요약
자바 인터페이스는 클래스 간의 계약을 정의하여 다형성과 코드 재사용성을 높이는 데 사용되는 강력한 도구입니다.