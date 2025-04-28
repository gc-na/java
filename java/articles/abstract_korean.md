<!--
Meta Description: # Java의 추상 클래스 및 인터페이스: 추상(abstract)의 이해 ## 개요 Java에서 '추상(abstract)'은 클래스나 메서드가 구체적인 구현 없이 선언만 되어 있는 상태를 나타냅니다. 추상 클래스는 다른 클래스에서 상속받아 구현할 수 있는 기본 구조를 ...
Meta Keywords: abstract, 클래스, class, 클래스는, 메서드를
-->

# Java의 추상 클래스 및 인터페이스: 추상(abstract)의 이해

## 개요
Java에서 '추상(abstract)'은 클래스나 메서드가 구체적인 구현 없이 선언만 되어 있는 상태를 나타냅니다. 추상 클래스는 다른 클래스에서 상속받아 구현할 수 있는 기본 구조를 제공합니다. 이는 코드의 재사용성과 유연성을 높이며, 객체지향 프로그래밍의 중요한 개념 중 하나입니다.

## 문서화
### 목적
'추상'은 Java에서 다형성을 제공하며, 불완전한 클래스 또는 메서드를 정의할 수 있게 합니다. 이를 통해 개발자는 구체적인 클래스를 작성할 때 기본적인 틀을 따르도록 강제할 수 있습니다.

### 사용법
1. **추상 클래스(abstract class)**: 추상 키워드를 사용하여 클래스를 정의합니다. 추상 클래스는 인스턴스를 생성할 수 없으며, 최소 하나 이상의 추상 메서드를 포함해야 합니다.
2. **추상 메서드(abstract method)**: 메서드 선언부에 추상 키워드를 추가하여 메서드를 정의합니다. 이 메서드는 서브클래스에서 반드시 구현해야 합니다.

### 세부사항
- 추상 클래스는 일반 메서드와 추상 메서드를 모두 포함할 수 있습니다.
- 추상 클래스는 다른 추상 클래스 또는 구체 클래스(비추상 클래스)에서 상속받을 수 있습니다.
- 인터페이스와의 차이점: 인터페이스는 모든 메서드가 기본적으로 추상적이며, 다중 상속을 지원합니다. 반면 추상 클래스는 단일 상속만 가능하며, 상태(속성)를 가질 수 있습니다.

## 예제
### 추상 클래스 예제
```java
abstract class Animal {
    abstract void makeSound(); // 추상 메서드

    void eat() { // 일반 메서드
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.makeSound(); // 출력: Bark
        myDog.eat(); // 출력: Eating...
    }
}
```

### 추상 메서드 예제
```java
abstract class Shape {
    abstract double area(); // 추상 메서드
}

class Circle extends Shape {
    double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    double area() {
        return Math.PI * radius * radius; // 구체적 구현
    }
}

public class Main {
    public static void main(String[] args) {
        Shape myCircle = new Circle(5);
        System.out.println("Area: " + myCircle.area()); // 출력: Area: 78.53981633974483
    }
}
```

## 설명
- **주요 함정**: 추상 클래스는 인스턴스를 생성할 수 없습니다. 따라서 직접 객체를 만들려고 하면 컴파일 오류가 발생합니다.
- **구현 강제**: 서브클래스에서 추상 메서드를 구현하지 않으면 컴파일 오류가 발생합니다. 이는 모든 서브클래스가 특정 메서드를 반드시 구현하도록 강제합니다.
- **다중 상속 제한**: Java는 추상 클래스에 대해 단일 상속만 지원하므로, 여러 추상 클래스를 상속받을 수 없습니다. 이를 해결하기 위해 인터페이스를 사용할 수 있습니다.

## 한 줄 요약
Java의 '추상(abstract)'은 클래스와 메서드의 기본 구조를 정의하여 다형성을 제공하고 코드의 재사용성을 높이는 객체지향 프로그래밍의 핵심 개념입니다.