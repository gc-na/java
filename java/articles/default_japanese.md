<!--
Meta Description: # Javaにおける「default」キーワードの完全ガイド ## 概要 Javaプログラミング言語における「default」は、インターフェース内でのメソッドの定義に関する重要なキーワードです。これは、インターフェースにおいてデフォルトの実装を提供するために使用され、実装クラスがこのメソッドをオー...
Meta Keywords: default, public, void, java, system
-->

# Javaにおける「default」キーワードの完全ガイド

## 概要
Javaプログラミング言語における「default」は、インターフェース内でのメソッドの定義に関する重要なキーワードです。これは、インターフェースにおいてデフォルトの実装を提供するために使用され、実装クラスがこのメソッドをオーバーライドすることができます。

## ドキュメンテーション
### 目的
「default」キーワードは、Java 8以降のインターフェースの機能で、インターフェースに具体的なメソッド実装を持たせることを可能にします。これにより、既存のインターフェースを変更することなく、新しい機能を追加することができます。

### 使用法
`default`メソッドは、インターフェースのメソッドの宣言の前に `default`キーワードを付加して定義します。以下のように記述します。

```java
public interface MyInterface {
    default void myDefaultMethod() {
        System.out.println("デフォルトメソッドの実装");
    }
}
```

このメソッドは、`MyInterface`を実装するクラスが特にオーバーライドしない限り、デフォルトの実装として使用されます。

### 詳細
- `default`メソッドは、インターフェースにおける多重継承の問題を解決するために導入されました。
- クラスが複数のインターフェースを実装する場合、同じメソッド名を持つデフォルトメソッドが複数存在する場合、コンパイルエラーが発生します。この場合、明示的にどのデフォルトメソッドを使用するかを指定する必要があります。

## 例
以下に「default」メソッドの基本的な使用例を示します。

### 例1: シンプルなデフォルトメソッド
```java
public interface Animal {
    default void sound() {
        System.out.println("動物の音");
    }
}

public class Dog implements Animal {
    // デフォルトメソッドをオーバーライド
    @Override
    public void sound() {
        System.out.println("ワンワン");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound(); // 出力: ワンワン
    }
}
```

### 例2: デフォルトメソッドの利用
```java
public interface Vehicle {
    default void start() {
        System.out.println("車がスタートします");
    }
}

public class Bike implements Vehicle {
    // デフォルトメソッドをオーバーライドしない
}

public class Main {
    public static void main(String[] args) {
        Vehicle bike = new Bike();
        bike.start(); // 出力: 車がスタートします
    }
}
```

## 説明
- **一般的な落とし穴**: 複数のインターフェースで同じ名前のデフォルトメソッドを持つ場合、どのメソッドを使用するかを明示的に指定する必要があります。これにより、コードが複雑になることがあります。
- **注意点**: デフォルトメソッドは、インターフェースのバージョン管理を容易にしますが、過度に使用すると、インターフェースの意図が不明確になる可能性があります。

## 一文要約
Javaにおける「default」キーワードは、インターフェースにおいてデフォルトのメソッド実装を提供し、クラスがこの実装をオーバーライドできる機能を持つ。