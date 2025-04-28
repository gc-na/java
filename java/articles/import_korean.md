<!--
Meta Description: # Java에서의 import: 필수 개념과 사용법 ## 개요 Java에서 `import`는 다른 클래스나 패키지를 현재 소스 파일에 포함시키기 위해 사용되는 명령어입니다. 이를 통해 개발자는 코드의 재사용성을 높이고, 복잡성을 줄이며, 외부 라이브러리와 API를 쉽게...
Meta Keywords: import, java, 클래스를, public, 클래스
-->

# Java에서의 import: 필수 개념과 사용법

## 개요
Java에서 `import`는 다른 클래스나 패키지를 현재 소스 파일에 포함시키기 위해 사용되는 명령어입니다. 이를 통해 개발자는 코드의 재사용성을 높이고, 복잡성을 줄이며, 외부 라이브러리와 API를 쉽게 활용할 수 있습니다.

## 문서화
`import` 문은 Java 프로그램에서 필요로 하는 클래스를 찾기 위해 사용됩니다. Java의 모든 클래스는 특정 패키지에 속하며, `import` 문을 사용함으로써 해당 패키지의 클래스를 사용할 수 있게 됩니다. 

### 목적
- **코드 가독성 향상**: 긴 클래스 이름을 줄여 코드의 가독성을 높입니다.
- **재사용성**: 이미 작성된 클래스를 재사용할 수 있게 해줍니다.
- **패키지 관리**: 패키지 내의 클래스를 효율적으로 관리하고 사용할 수 있게 합니다.

### 사용법
Java에서 `import` 문은 클래스 선언 전에 위치하며, 다음과 같은 형식을 가집니다:
```java
import packageName.ClassName;
```
또는 패키지 내의 모든 클래스를 가져오고 싶을 경우:
```java
import packageName.*;
```

## 예제
1. 특정 클래스 가져오기:
```java
import java.util.Scanner;

public class Example {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter a number:");
        int number = scanner.nextInt();
        System.out.println("You entered: " + number);
    }
}
```

2. 전체 패키지 가져오기:
```java
import java.util.*;

public class Example {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Hello");
        list.add("World");
        System.out.println(list);
    }
}
```

## 설명
- **가져오기 순서**: `import` 문은 항상 패키지 이름과 클래스 이름의 정확한 대소문자를 구분해야 합니다. Java는 대소문자를 구분하는 언어이므로, 잘못된 대소문자로 인해 컴파일 오류가 발생할 수 있습니다.
- **충돌 문제**: 동일한 이름의 클래스를 여러 패키지에서 가져오는 경우, 클래스 이름 충돌이 발생할 수 있습니다. 이럴 때는 전체 경로를 사용하여 명확하게 구분해야 합니다.
- **정적 가져오기**: Java에서는 `import static` 문을 사용하여 클래스의 정적 멤버를 직접 사용할 수 있습니다. 예를 들어:
```java
import static java.lang.Math.PI;

public class Example {
    public static void main(String[] args) {
        System.out.println(PI);
    }
}
```

## 한 줄 요약
Java에서 `import` 명령어는 외부 클래스나 패키지를 포함하여 코드 재사용성과 가독성을 높이는 중요한 기능입니다.