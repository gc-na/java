<!--
Meta Description: # JAVA의 private 접근 제어자: 이해와 활용 ## 개요 JAVA에서의 `private` 접근 제어자는 클래스의 멤버(변수 및 메서드)에 대한 접근을 제한하는 중요한 기능입니다. 이를 통해 데이터 은닉을 구현하고, 클래스 외부에서의 불법적인 접근을 방지할 수 ...
Meta Keywords: private, 접근할, public, 멤버에, 클래스의
-->

# JAVA의 private 접근 제어자: 이해와 활용

## 개요
JAVA에서의 `private` 접근 제어자는 클래스의 멤버(변수 및 메서드)에 대한 접근을 제한하는 중요한 기능입니다. 이를 통해 데이터 은닉을 구현하고, 클래스 외부에서의 불법적인 접근을 방지할 수 있습니다.

## 문서화
`private` 키워드는 JAVA에서 클래스 내에서 정의된 변수와 메서드의 접근 수준을 설정합니다. `private`로 선언된 멤버는 해당 클래스 내부에서만 접근 가능하며, 외부 클래스나 서브클래스에서는 접근할 수 없습니다. 이를 통해 클래스의 내부 구현 세부정보를 숨기고, 객체 지향 프로그래밍의 캡슐화 원칙을 따를 수 있습니다.

### 목적
- 데이터 은닉: 객체의 상태를 보호하고, 잘못된 데이터 변경을 방지합니다.
- 코드 유지보수: 클래스의 내부 구조가 변경되더라도 외부에 미치는 영향을 최소화합니다.

### 사용법
`private` 키워드는 클래스 멤버를 선언할 때 사용하며, 변수나 메서드 앞에 위치합니다.

```java
public class Example {
    private int number; // private 변수

    private void displayNumber() { // private 메서드
        System.out.println("Number: " + number);
    }
}
```

## 예제
다음은 `private` 접근 제어자를 사용한 간단한 예제입니다.

```java
public class BankAccount {
    private double balance; // 잔고

    public BankAccount(double initialBalance) {
        this.balance = initialBalance;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    public double getBalance() {
        return balance; // private 멤버에 접근하는 공개 메서드
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount account = new BankAccount(1000);
        account.deposit(500);
        System.out.println("잔고: " + account.getBalance());
    }
}
```

위의 예제에서 `balance` 멤버는 `private`로 선언되어 외부에서 직접 접근할 수 없으며, `getBalance()` 메서드를 통해서만 접근할 수 있습니다.

## 설명
- **캡슐화**: `private`는 클래스의 내부 상태를 보호하기 위해 사용됩니다. 외부에서 직접적으로 멤버에 접근할 수 없게 하여, 데이터의 무결성을 유지합니다.
- **상속과의 관계**: 서브클래스는 슈퍼클래스의 `private` 멤버에 접근할 수 없습니다. 이를 통해 각 클래스의 독립성을 유지할 수 있습니다.
- **getter 및 setter 사용**: `private` 멤버에 접근하기 위해서는 보통 `getter`와 `setter` 메서드를 사용하여 데이터를 간접적으로 조작합니다.

### 흔한 실수 및 주의사항
- `private`으로 선언된 멤버에 접근하려고 시도할 경우, 컴파일 오류가 발생합니다.
- `private` 멤버는 같은 클래스 내에서는 자유롭게 접근할 수 있지만, 외부 클래스 또는 서브클래스에서는 접근할 수 없습니다.
- 객체의 상태를 변경할 때는 반드시 `setter` 메서드를 통해 변경해야 하며, 직접적으로 멤버에 접근하여 변경하는 것은 피해야 합니다.

## 한 줄 요약
`private` 접근 제어자는 JAVA에서 클래스의 멤버에 대한 접근을 제한하여 데이터 은닉과 캡슐화를 구현하는 데 사용됩니다.