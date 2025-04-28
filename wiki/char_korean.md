<!--
Meta Description: # Java에서 char 데이터 타입: 문자열 처리의 기초 ## 개요 Java에서 `char`는 단일 16비트 유니코드 문자를 저장하는 기본 데이터 타입입니다. 이 타입은 문자 데이터를 처리하는 데 필수적이며, 문자열 및 문자 기반 작업에서 자주 사용됩니다. ## 문서...
Meta Keywords: char, 문자를, letter, public, 데이터
-->

# Java에서 char 데이터 타입: 문자열 처리의 기초

## 개요
Java에서 `char`는 단일 16비트 유니코드 문자를 저장하는 기본 데이터 타입입니다. 이 타입은 문자 데이터를 처리하는 데 필수적이며, 문자열 및 문자 기반 작업에서 자주 사용됩니다.

## 문서화
### 목적
`char` 데이터 타입은 단일 문자를 저장하기 위해 설계되었습니다. 이는 Java의 Unicode 문자 집합을 사용하여 다양한 언어의 문자를 지원하며, 문자열 연산 및 문자 조작을 용이하게 합니다.

### 사용법
Java에서 `char`는 다음과 같이 선언할 수 있습니다:
```java
char letter = 'A';
char number = '1';
char symbol = '@';
```
문자 리터럴은 작은따옴표(`'`)로 감싸야 하며, 유니코드 이스케이프를 사용하여 특정 문자를 나타낼 수도 있습니다:
```java
char unicodeChar = '\u2602'; // ☂ (우산 기호)
```

### 세부 사항
- `char` 타입은 0부터 65535까지의 값을 가질 수 있습니다.
- `char`는 정수형 데이터 타입인 `int`, `byte`, `short`와의 호환성이 있으며, 자동 형 변환이 가능합니다.
- 문자 연산(더하기, 빼기 등)을 통해 ASCII 코드와 같은 정수 연산을 수행할 수 있습니다.

## 예제
1. 기본적인 `char` 사용 예:
```java
public class CharExample {
    public static void main(String[] args) {
        char firstLetter = 'J';
        char secondLetter = 'a';
        System.out.println("First letter: " + firstLetter);
        System.out.println("Second letter: " + secondLetter);
    }
}
```

2. 유니코드 문자 사용 예:
```java
public class UnicodeExample {
    public static void main(String[] args) {
        char heartSymbol = '\u2665';
        System.out.println("Heart Symbol: " + heartSymbol);
    }
}
```

3. 문자와 정수의 연산:
```java
public class CharArithmetic {
    public static void main(String[] args) {
        char letter = 'A';
        int asciiValue = letter + 1; // 'A'의 ASCII 값에 1을 더함
        char nextLetter = (char) asciiValue;
        System.out.println("Next letter: " + nextLetter); // 'B' 출력
    }
}
```

## 설명
- **문자 리터럴**: `char` 값은 반드시 작은따옴표로 감싸야 하며, 쌍따옴표는 문자열을 나타냅니다. 이 점을 혼동하지 않도록 주의해야 합니다.
- **형 변환**: `char`를 정수형으로 사용하거나 정수를 `char`로 변환할 때는 주의가 필요합니다. 잘못된 형 변환은 예외를 발생시킬 수 있습니다.
- **유니코드 지원**: Java는 다양한 언어의 문자를 지원하므로, 국제화(i18n) 애플리케이션 개발에 유용합니다.

## 한 줄 요약
Java의 `char` 데이터 타입은 단일 16비트 유니코드 문자를 표현하며, 문자열과 문자 조작에 필수적인 요소입니다.