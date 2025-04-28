<!--
Meta Description: # Java에서의 "protected" 접근 제어자 ## 개요 Java에서 "protected"는 클래스의 멤버(변수 및 메서드)에 대한 접근 제한을 정의하는 접근 제어자입니다. 이 제어자는 클래스의 상속 관계에서 접근을 허용하는 특성을 가지고 있어, 자식 클래스와 같...
Meta Keywords: protected, 클래스의, 제어자는, 접근할, class
-->

# Java에서의 "protected" 접근 제어자

## 개요
Java에서 "protected"는 클래스의 멤버(변수 및 메서드)에 대한 접근 제한을 정의하는 접근 제어자입니다. 이 제어자는 클래스의 상속 관계에서 접근을 허용하는 특성을 가지고 있어, 자식 클래스와 같은 패키지 내의 다른 클래스에서 해당 멤버를 사용할 수 있게 해줍니다.

## 문서화
"protected" 접근 제어자는 Java에서 클래스의 멤버에 대한 접근을 제한하는 방법 중 하나입니다. 이 제어자는 다음과 같은 용도로 사용됩니다:

- **상속 관계에서의 접근 허용**: 자식 클래스에서 부모 클래스의 "protected" 멤버에 접근할 수 있습니다.
- **동일 패키지 내의 접근**: "protected" 멤버는 동일한 패키지에 속하는 클래스에서도 접근할 수 있습니다.

### 사용법
"protected" 접근 제어자는 클래스 내에서 변수 또는 메서드 선언 시 사용됩니다. 다음은 그 기본 구문입니다:

```java
protected 데이터타입 변수명;
protected 반환타입 메서드명(매개변수타입 매개변수명) {
    // 메서드 내용
}
```

## 예제
다음은 "protected" 접근 제어자를 사용하는 간단한 예제입니다:

```java
class Parent {
    protected void display() {
        System.out.println("Parent class method.");
    }
}

class Child extends Parent {
    void show() {
        display(); // Parent 클래스의 protected 메서드 호출
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.show(); // "Parent class method." 출력
    }
}
```

## 설명
"protected" 접근 제어자를 사용할 때 주의해야 할 점은 다음과 같습니다:

1. **다른 패키지에서의 접근 제한**: "protected" 멤버는 자식 클래스에서 접근할 수 있지만, 부모 클래스와 다른 패키지에 있는 경우에는 직접 접근할 수 없습니다. 자식 클래스가 부모 클래스와 동일한 패키지에 있을 경우에만 접근이 가능합니다.

2. **접근 제어자 우선순위**: "protected"는 "private"보다 더 많은 접근을 허용하지만, "public"보다는 더 제한적입니다. 따라서, 객체지향 프로그래밍의 원칙에 따라 적절한 접근 제어자를 선택하는 것이 중요합니다.

3. **인터페이스의 경우**: 인터페이스에서 정의된 메서드는 기본적으로 public이므로, "protected" 멤버는 인터페이스와 함께 사용할 수 없습니다.

## 한줄 요약
Java에서 "protected" 접근 제어자는 상속 관계에서 자식 클래스와 동일 패키지 내 클래스가 부모 클래스의 멤버에 접근할 수 있도록 허용하는 방식입니다.