<!--
Meta Description: # Java의 "new" 키워드: 객체 생성의 기초 ## 개요 Java 프로그래밍 언어에서 "new" 키워드는 새로운 객체(instance)를 생성하는 데 사용되는 중요한 키워드입니다. 이 키워드를 사용하여 클래스의 인스턴스를 만들고, 메모리를 할당하며, 생성자를 호출...
Meta Keywords: new, 객체를, 키워드는, 클래스의, dog
-->

# Java의 "new" 키워드: 객체 생성의 기초

## 개요
Java 프로그래밍 언어에서 "new" 키워드는 새로운 객체(instance)를 생성하는 데 사용되는 중요한 키워드입니다. 이 키워드를 사용하여 클래스의 인스턴스를 만들고, 메모리를 할당하며, 생성자를 호출합니다.

## 문서화
### 목적
"new" 키워드는 Java에서 객체를 생성하는 데 필수적입니다. 객체 지향 프로그래밍(OOP)에서 클래스는 객체의 청사진 역할을 하며, "new"를 사용하여 해당 클래스의 인스턴스를 생성합니다.

### 사용법
"new" 키워드는 다음과 같은 형식으로 사용됩니다:

```java
ClassName objectName = new ClassName();
```

- `ClassName`: 생성할 객체의 클래스 이름
- `objectName`: 생성되는 객체의 참조 변수 이름

이 코드는 지정된 클래스의 객체를 생성하고, 메모리를 할당하며, 해당 클래스의 생성자를 호출합니다.

### 세부 사항
- **메모리 할당**: "new" 키워드는 JVM(Java Virtual Machine)에서 객체를 위한 메모리를 동적으로 할당합니다.
- **생성자 호출**: 객체 생성 시 클래스의 생성자가 호출되어 초기화 작업을 수행합니다.
- **null 참조**: 객체를 생성하지 않으면 해당 참조 변수는 null이 됩니다. 이 상태에서 메서드를 호출하면 NullPointerException이 발생할 수 있습니다.

## 예제
### 기본 사용 예제

```java
// 클래스 정의
class Dog {
    String name;

    Dog(String name) {
        this.name = name;
    }

    void bark() {
        System.out.println(name + " says Woof!");
    }
}

// 객체 생성
public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Buddy");
        myDog.bark(); // 출력: Buddy says Woof!
    }
}
```

이 예제에서 `Dog`라는 클래스를 정의하고, "new" 키워드를 사용하여 `myDog` 객체를 생성합니다. 그런 다음, `bark` 메서드를 호출하여 객체의 기능을 실행합니다.

## 설명
### 일반적인 함정 및 주의 사항
1. **NullPointerException**: 객체를 생성하지 않고 메서드를 호출하는 경우 발생할 수 있습니다. 항상 객체가 null이 아닌지 확인해야 합니다.
2. **메모리 누수**: 객체를 사용한 후 참조를 null로 설정하지 않으면, 가비지 컬렉터가 메모리를 회수하지 못할 수 있습니다.
3. **Immutable 객체**: String과 같은 불변 객체를 생성할 때는 "new" 보다 리터럴을 사용하여 더 효율적으로 객체를 생성할 수 있습니다.

## 한 줄 요약
Java에서 "new" 키워드는 새로운 객체를 생성하고 초기화하는 데 사용되는 핵심 키워드입니다.