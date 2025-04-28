<!--
Meta Description: # 자바 모듈(Module): 구조적 프로그래밍의 새로운 패러다임 ## 개요 자바 모듈은 Java 9에서 도입된 기능으로, 애플리케이션을 구성하는 코드와 종속성을 관리하고, 서로 다른 모듈 간의 접근 제어를 제공하여 코드의 모듈성을 높이는 역할을 합니다. ## 문서화 ...
Meta Keywords: module, java, com, info, hello
-->

# 자바 모듈(Module): 구조적 프로그래밍의 새로운 패러다임

## 개요
자바 모듈은 Java 9에서 도입된 기능으로, 애플리케이션을 구성하는 코드와 종속성을 관리하고, 서로 다른 모듈 간의 접근 제어를 제공하여 코드의 모듈성을 높이는 역할을 합니다. 

## 문서화
자바 모듈은 `module-info.java` 파일을 통해 정의됩니다. 이 파일은 모듈의 이름, 외부 모듈에 대한 의존성, 다른 모듈이 제공하는 패키지에 대한 접근 허용 여부 등을 명시합니다. 

### 목적
- **모듈화**: 애플리케이션을 논리적으로 나누어 관리하기 쉽게 만듭니다.
- **캡슐화**: 모듈 간의 의존성을 명확히 하여 코드의 안전성을 증가시킵니다.
- **성능 향상**: 필요한 모듈만 로드하여 성능을 최적화합니다.

### 사용법
1. **모듈 생성**: `module-info.java` 파일을 생성하고 모듈의 이름과 요구 사항을 정의합니다.
   ```java
   module my.module {
       requires another.module;
       exports com.my.package;
   }
   ```

2. **모듈 컴파일**: `javac` 명령어를 사용하여 모듈을 컴파일합니다.
   ```bash
   javac -d mods/my.module src/my/module/module-info.java src/my/module/*.java
   ```

3. **모듈 실행**: `java` 명령어로 모듈을 실행합니다.
   ```bash
   java --module-path mods -m my.module/com.my.package.Main
   ```

## 예제
### 기본적인 모듈 사용 예제
1. **모듈 정의**: `module-info.java`
   ```java
   module my.module {
       exports com.example;
   }
   ```
   
2. **패키지 클래스**: `com/example/Hello.java`
   ```java
   package com.example;

   public class Hello {
       public static void greet() {
           System.out.println("Hello, World!");
       }
   }
   ```

3. **메인 클래스**: `Main.java`
   ```java
   import com.example.Hello;

   public class Main {
       public static void main(String[] args) {
           Hello.greet();
       }
   }
   ```

## 설명
- **모듈 의존성**: 모듈이 다른 모듈을 사용하려면 `requires`를 통해 의존성을 명시해야 합니다.
- **패키지 공유**: `exports` 키워드를 사용하여 다른 모듈에서 접근할 수 있는 패키지를 지정합니다.
- **컴파일 문제**: 모듈 관련 문제가 발생할 경우, 컴파일 경로가 올바른지, 모듈 이름이 정확한지 확인해야 합니다.

## 한 줄 요약
자바 모듈은 코드의 모듈성과 안전성을 높이기 위해 Java 9에서 도입된 기능으로, `module-info.java` 파일을 통해 모듈을 정의하고 관리합니다.