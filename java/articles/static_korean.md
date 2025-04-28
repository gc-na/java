<!--
Meta Description: # Java의 static 키워드: 개념 및 활용 ## 개요 Java에서 `static` 키워드는 클래스 수준에서 변수를 선언하거나 메서드를 정의할 수 있게 해주는 중요한 기능입니다. 이 키워드를 사용하면 객체가 아닌 클래스에 속하는 요소를 만들 수 있습니다. ## 문...
Meta Keywords: static, staticvariable, 클래스, 변수를, 있습니다
-->

# Java의 static 키워드: 개념 및 활용

## 개요
Java에서 `static` 키워드는 클래스 수준에서 변수를 선언하거나 메서드를 정의할 수 있게 해주는 중요한 기능입니다. 이 키워드를 사용하면 객체가 아닌 클래스에 속하는 요소를 만들 수 있습니다.

## 문서화
`static` 키워드는 클래스의 특정 필드나 메서드가 클래스의 인스턴스에 속하지 않고, 클래스 자체에 속하도록 설정합니다. 이는 메모리 사용을 최적화하고, 객체를 생성하지 않고도 접근할 수 있는 유용한 기능을 제공합니다.

### 목적
- 클래스 수준에서 공유되는 변수 및 메서드를 정의합니다.
- 인스턴스 생성 없이 접근할 수 있습니다.
- 메모리 사용을 줄이고 코드의 구조를 간결하게 유지합니다.

### 사용법
- `static` 변수를 선언할 때는 `static` 키워드를 사용하여 클래스 내에서 직접 정의합니다.
- `static` 메서드는 클래스 이름으로 직접 호출할 수 있으며, 인스턴스 변수나 메서드에 접근할 수 없습니다.

## 예제
```java
public class Example {
    static int staticVariable = 0; // static 변수

    static void staticMethod() { // static 메서드
        System.out.println("Static 메서드 호출됨");
    }

    public static void main(String[] args) {
        Example.staticVariable++; // static 변수에 접근
        Example.staticMethod(); // static 메서드 호출
        System.out.println("staticVariable: " + Example.staticVariable);
    }
}
```

## 설명
- **공통적인 함정**: `static` 변수를 사용할 때, 여러 인스턴스에서 이 변수에 접근하면 값이 공유되므로 의도치 않은 결과를 초래할 수 있습니다. 따라서 상태를 유지해야 하는 변수를 `static`으로 정의하는 것은 신중해야 합니다.
- **정적 메서드**: 정적 메서드는 인스턴스에 의존하지 않기 때문에 인스턴스 필드에 접근할 수 없습니다. 만약 정적 메서드에서 인스턴스 필드에 접근하려고 하면 컴파일 오류가 발생합니다.
- **정적 초기화 블록**: `static` 변수를 초기화하기 위해 정적 초기화 블록을 사용할 수 있습니다.
  
```java
public class StaticExample {
    static int staticVariable;

    static {
        staticVariable = 5; // 정적 초기화 블록
    }

    public static void main(String[] args) {
        System.out.println("staticVariable: " + staticVariable);
    }
}
```

## 한 줄 요약
Java에서 `static` 키워드는 클래스 수준에서 공유되는 변수와 메서드를 정의할 수 있게 해주는 키워드입니다.