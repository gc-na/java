<!--
Meta Description: # Java에서 'implements' 키워드 이해하기 ## 개요 Java에서 'implements' 키워드는 클래스가 인터페이스를 구현할 때 사용되는 중요한 문법 요소입니다. 이는 객체 지향 프로그래밍의 다형성과 상속을 지원하며, 코드의 재사용성과 유연성을 높입니다....
Meta Keywords: implements, frog, void, 인터페이스를, public
-->

# Java에서 'implements' 키워드 이해하기

## 개요
Java에서 'implements' 키워드는 클래스가 인터페이스를 구현할 때 사용되는 중요한 문법 요소입니다. 이는 객체 지향 프로그래밍의 다형성과 상속을 지원하며, 코드의 재사용성과 유연성을 높입니다.

## 문서화
### 목적
'implements' 키워드는 클래스가 특정 인터페이스의 메서드를 구현하도록 강제합니다. 인터페이스는 메서드의 시그니처만 정의하고, 실제 구현은 이를 사용하는 클래스에서 제공됩니다. 이를 통해 서로 다른 클래스 간에 일관된 메서드 집합을 생성할 수 있습니다.

### 사용법
Java에서 클래스가 인터페이스를 구현하려면, 클래스 정의에서 'implements' 키워드를 사용합니다. 다음과 같은 구문을 따릅니다:

```java
class ClassName implements InterfaceName {
    // 인터페이스의 모든 메서드를 구현해야 합니다.
}
```

### 세부 사항
- 하나의 클래스는 여러 인터페이스를 구현할 수 있으며, 이 경우 각 인터페이스 이름을 쉼표로 구분하여 나열합니다.
- 인터페이스의 메서드는 기본적으로 public이므로, 구현 클래스에서도 이 메서드는 public으로 정의해야 합니다.
- 인터페이스는 다중 상속을 지원하여, 코드의 유연성을 높이고, 여러 기능을 가진 클래스를 설계할 수 있게 합니다.

## 예제
### 기본 사용 예
다음은 'implements' 키워드를 사용하는 간단한 예제입니다.

```java
// 인터페이스 정의
interface Animal {
    void sound();
}

// 클래스가 인터페이스를 구현
class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Woof");
    }
}

// 메인 클래스
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // 출력: Woof
    }
}
```

### 다중 구현 예
```java
interface Swimmable {
    void swim();
}

interface Runnable {
    void run();
}

class Frog implements Swimmable, Runnable {
    @Override
    public void swim() {
        System.out.println("Frog swims");
    }

    @Override
    public void run() {
        System.out.println("Frog runs");
    }
}

public class Main {
    public static void main(String[] args) {
        Frog frog = new Frog();
        frog.swim(); // 출력: Frog swims
        frog.run();  // 출력: Frog runs
    }
}
```

## 설명
'implements' 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:
- 인터페이스의 모든 메서드를 구현하지 않으면 컴파일 에러가 발생합니다. 이는 인터페이스의 계약을 준수하지 않기 때문입니다.
- 'implements' 키워드는 클래스가 인터페이스를 구현하는 것을 명시적으로 표현하므로, 코드의 가독성과 유지보수성을 높입니다.
- 인터페이스는 다중 상속을 허용하지만, 클래스는 단일 상속만 지원하므로, 인터페이스를 통해 다형성을 활용할 수 있습니다.

## 한 줄 요약
Java에서 'implements' 키워드는 클래스가 하나 이상의 인터페이스를 구현하여 메서드의 시그니처를 정의하고, 다형성을 지원하는 핵심 문법이다.