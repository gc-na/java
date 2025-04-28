<!--
Meta Description: # JAVA 클래스: 객체 지향 프로그래밍의 핵심 ## 개요 JAVA에서 클래스는 객체 지향 프로그래밍의 기본 단위로, 데이터와 메소드를 캡슐화하여 객체를 생성하는 템플릿 역할을 합니다. 클래스는 JAVA 프로그램에서 코드의 재사용성과 구조적 설계를 가능하게 합니다. ...
Meta Keywords: public, java, field, 클래스, 클래스는
-->

# JAVA 클래스: 객체 지향 프로그래밍의 핵심

## 개요
JAVA에서 클래스는 객체 지향 프로그래밍의 기본 단위로, 데이터와 메소드를 캡슐화하여 객체를 생성하는 템플릿 역할을 합니다. 클래스는 JAVA 프로그램에서 코드의 재사용성과 구조적 설계를 가능하게 합니다.

## 문서화
JAVA 클래스는 객체의 속성과 동작을 정의하는 구조입니다. 클래스는 다음과 같은 구성 요소로 이루어져 있습니다:
- **필드(변수)**: 클래스의 속성을 정의합니다.
- **메소드**: 클래스의 동작을 정의합니다.
- **생성자**: 클래스의 객체를 초기화하는 특수한 메소드입니다.

### 사용 목적
클래스를 사용하면 복잡한 프로그램을 보다 간단히 관리할 수 있으며, 데이터와 관련된 행동을 하나의 단위로 묶어 코드의 재사용성과 유지보수를 용이하게 합니다.

### 사용법
클래스를 정의할 때는 `class` 키워드를 사용하며, 클래스 이름은 대문자로 시작하는 것이 일반적입니다. 기본적인 클래스 정의는 다음과 같습니다:

```java
public class ClassName {
    // 필드
    private int field;

    // 생성자
    public ClassName(int field) {
        this.field = field;
    }

    // 메소드
    public void method() {
        System.out.println("Field value: " + field);
    }
}
```

## 예제
다음은 JAVA 클래스를 사용하는 간단한 예제입니다:

```java
public class Car {
    private String model;
    private int year;

    // 생성자
    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    // 메소드
    public void displayInfo() {
        System.out.println("모델: " + model + ", 연도: " + year);
    }
    
    public static void main(String[] args) {
        Car myCar = new Car("소나타", 2020);
        myCar.displayInfo(); // 출력: 모델: 소나타, 연도: 2020
    }
}
```

## 설명
클래스를 사용할 때 주의할 점:
- **접근 제어자**: 클래스의 필드와 메소드에 적절한 접근 제어자(예: `public`, `private`, `protected`)를 설정해야 합니다. 접근 제어자를 잘못 설정하면 데이터 은닉이 제대로 이루어지지 않을 수 있습니다.
- **상속**: 클래스를 상속받을 때는 `extends` 키워드를 사용하며, 하나의 클래스만 상속할 수 있는 단일 상속을 지원합니다. 인터페이스를 사용하면 다중 상속의 기능을 구현할 수 있습니다.
- **정적 멤버**: 클래스 변수와 메소드는 `static` 키워드를 사용하여 클래스 레벨에서 공유할 수 있습니다. 하지만 정적 멤버는 인스턴스 변수와는 다르게 객체와 관계없이 존재하므로 주의가 필요합니다.

## 한 줄 요약
JAVA 클래스는 객체 지향 프로그래밍의 기반이 되는 데이터와 동작을 정의하는 구조체입니다.