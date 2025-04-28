<!--
Meta Description: # Javaにおける「protected」アクセス修飾子の解説 ## 概要 Javaの「protected」アクセス修飾子は、クラスのメンバー（フィールドやメソッド）へのアクセス制限を設定するために使用されます。この修飾子は、同じパッケージ内のクラスや、異なるパッケージに属するサブクラスからアクセス...
Meta Keywords: protected, dog, public, class, void
-->

# Javaにおける「protected」アクセス修飾子の解説

## 概要
Javaの「protected」アクセス修飾子は、クラスのメンバー（フィールドやメソッド）へのアクセス制限を設定するために使用されます。この修飾子は、同じパッケージ内のクラスや、異なるパッケージに属するサブクラスからアクセス可能です。

## ドキュメンテーション
「protected」修飾子は、オブジェクト指向プログラミングの基本概念であるカプセル化をサポートします。具体的には、以下のような目的と使用方法があります。

### 目的
- **アクセス制御**: メンバーのアクセスを制限し、データの隠蔽を行う。
- **継承のサポート**: サブクラスから親クラスのメンバーにアクセスすることを容易にする。

### 使用方法
- クラスメンバーの前に「protected」キーワードを指定します。
- 同じパッケージ内の他のクラスや、異なるパッケージにあるサブクラスからアクセスが可能です。

```java
public class Parent {
    protected int number;

    protected void displayNumber() {
        System.out.println("Number: " + number);
    }
}

public class Child extends Parent {
    public void show() {
        number = 10; // 親クラスのprotectedメンバーにアクセス
        displayNumber(); // 親クラスのprotectedメソッドにアクセス
    }
}
```

## 例
以下は、「protected」修飾子の基本的な使用例です。

```java
// 親クラス
class Animal {
    protected String species;

    protected void sound() {
        System.out.println("Animal sound");
    }
}

// サブクラス
class Dog extends Animal {
    public void bark() {
        species = "Dog"; // protectedメンバーへのアクセス
        sound(); // protectedメソッドへのアクセス
        System.out.println("I am a " + species + " and I bark.");
    }
}

// メインクラスでの使用
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.bark(); // 出力: I am a Dog and I bark.
    }
}
```

## 説明
「protected」修飾子を使用する際の一般的な落とし穴や注意点は以下の通りです。

- **同じパッケージ内のクラスからのアクセス**: 「protected」メンバーは、サブクラスだけでなく、同じパッケージ内の全てのクラスからもアクセス可能です。この点を理解していないと、意図しないアクセスが許可されることがあります。
- **異なるパッケージの非サブクラスからのアクセス不可**: 「protected」メンバーは、異なるパッケージにあるクラスからはアクセスできません。これは、カプセル化の目的に沿っていますが、プログラムの構造によっては不便に感じる場合があります。

## 一文要約
Javaにおける「protected」修飾子は、同じパッケージ内のクラスや異なるパッケージのサブクラスからアクセス可能なメンバーを定義するために使用されます。