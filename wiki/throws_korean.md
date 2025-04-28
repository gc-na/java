<!--
Meta Description: # Java의 throws 키워드: 예외 처리의 기초 ## 개요 Java에서의 `throws` 키워드는 메서드가 특정 예외를 발생시킬 수 있음을 명시하는 데 사용됩니다. 이를 통해 컴파일러에게 해당 예외가 발생할 가능성을 알리고, 호출자가 이를 처리하도록 강제합니다. ...
Meta Keywords: throws, 예외를, 발생시킬, ioexception, 키워드는
-->

# Java의 throws 키워드: 예외 처리의 기초

## 개요
Java에서의 `throws` 키워드는 메서드가 특정 예외를 발생시킬 수 있음을 명시하는 데 사용됩니다. 이를 통해 컴파일러에게 해당 예외가 발생할 가능성을 알리고, 호출자가 이를 처리하도록 강제합니다.

## 문서화
Java의 `throws` 키워드는 메서드 선언의 일부로 사용되며, 메서드가 발생시킬 수 있는 체크 예외를 명시합니다. 이는 예외 처리의 중요한 부분으로, 프로그램의 안정성을 높이고 예외 발생 시 적절한 대응을 가능하게 합니다.

### 목적
`throws` 키워드는 호출자에게 예외를 처리할 책임을 부여하며, 메서드가 예외를 발생시킬 수 있음을 클라이언트에게 알립니다.

### 사용법
`throws` 키워드는 메서드의 반환 타입 뒤에 위치하며, 발생할 수 있는 예외 타입을 쉼표로 구분하여 나열합니다. 예를 들어:

```java
public void myMethod() throws IOException, SQLException {
    // 메서드 구현
}
```

이 경우, `myMethod`는 `IOException` 및 `SQLException`을 발생시킬 수 있음을 나타냅니다.

## 예제
다음은 `throws` 키워드를 사용하는 간단한 예제입니다.

```java
import java.io.FileReader;
import java.io.IOException;

public class FileExample {
    public void readFile() throws IOException {
        FileReader reader = new FileReader("example.txt");
        // 파일 읽기 로직
        reader.close();
    }

    public static void main(String[] args) {
        FileExample example = new FileExample();
        try {
            example.readFile();
        } catch (IOException e) {
            System.out.println("파일을 읽는 중 오류 발생: " + e.getMessage());
        }
    }
}
```

위의 예제에서 `readFile` 메서드는 `IOException`을 발생시킬 수 있으며, 이를 호출하는 측에서 예외를 처리하도록 요구합니다.

## 설명
`throws` 키워드를 사용할 때 주의해야 할 몇 가지 사항이 있습니다:

- **체크 예외와 비체크 예외**: `throws`는 체크 예외(checked exception)에서만 사용되며, 런타임 예외는 포함되지 않습니다.
- **메서드 서명**: 메서드 서명에 `throws`를 추가하면, 해당 메서드는 체크 예외를 발생시킬 수 있다는 것을 명시하게 됩니다. 따라서 이 메서드를 호출하는 모든 메서드에서도 해당 예외를 처리해야 합니다.
- **예외 처리 책임**: `throws`를 사용하는 메서드는 호출자가 예외를 처리하도록 강제하므로, 메서드의 안정성을 높입니다.

## 한 줄 요약
Java의 `throws` 키워드는 메서드가 발생시킬 수 있는 체크 예외를 선언하여 호출자가 이를 처리하도록 요구하는 기능입니다.