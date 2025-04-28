<!--
Meta Description: # Java의 break 명령어: 제어문에서의 사용과 이해 ## 개요 Java에서 `break` 명령어는 반복문이나 switch 문을 조기 종료하는 데 사용됩니다. 이 명령어는 프로그램의 흐름을 제어하고, 특정 조건이 충족될 때 루프를 빠져나오거나 switch 문을 종...
Meta Keywords: break, switch, system, out, println
-->

# Java의 break 명령어: 제어문에서의 사용과 이해

## 개요
Java에서 `break` 명령어는 반복문이나 switch 문을 조기 종료하는 데 사용됩니다. 이 명령어는 프로그램의 흐름을 제어하고, 특정 조건이 충족될 때 루프를 빠져나오거나 switch 문을 종료할 수 있게 해줍니다.

## 문서화
### 목적
`break` 명령어는 코드의 실행 흐름을 제어하는 데 중요한 역할을 합니다. 반복문이나 switch 문에서 더 이상 실행할 필요가 없을 때 이를 종료할 수 있습니다.

### 사용법
`break`는 다음과 같이 사용됩니다:
1. **반복문 종료**: `for`, `while`, `do-while` 등의 반복문 안에서 사용하여 루프를 종료합니다.
2. **switch 문 종료**: 특정 case가 실행된 후 더 이상의 case를 실행하지 않도록 합니다.

### 세부 사항
- `break` 명령어는 항상 현재의 블록을 종료하고 제어를 해당 블록을 호출한 위치로 반환합니다.
- `break`는 레이블과 함께 사용할 수 있으며, 이 경우 특정 레이블이 지정된 반복문을 종료할 수 있습니다.

## 예제
아래는 `break` 명령어의 기본 사용 예시입니다.

### 반복문에서의 사용
```java
public class BreakExample {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            if (i == 5) {
                break; // i가 5일 때 루프 종료
            }
            System.out.println(i);
        }
    }
}
```
*출력 결과:*
```
0
1
2
3
4
```

### switch 문에서의 사용
```java
public class SwitchExample {
    public static void main(String[] args) {
        int day = 4;
        switch (day) {
            case 1:
                System.out.println("월요일");
                break;
            case 2:
                System.out.println("화요일");
                break;
            case 3:
                System.out.println("수요일");
                break;
            case 4:
                System.out.println("목요일");
                break; // 이 지점에서 switch 문 종료
            default:
                System.out.println("주말");
        }
    }
}
```
*출력 결과:*
```
목요일
```

## 설명
- **일반적인 실수**: `break` 명령어를 사용하지 않으면, switch 문 내에서 다음 case로 넘어가게 되며 이는 의도치 않은 동작을 초래할 수 있습니다.
- **레이블 사용 주의**: 레이블이 붙은 `break`를 사용할 때는 해당 레이블이 현재의 블록에서 올바르게 지정되어 있는지 확인해야 합니다. 잘못된 레이블은 컴파일 에러를 발생시킬 수 있습니다.

## 한 줄 요약
`break` 명령어는 Java에서 반복문이나 switch 문을 조기에 종료하는 데 사용되는 제어 흐름 명령어입니다.