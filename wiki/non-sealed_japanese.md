<!--
Meta Description: # Javaにおける「non-sealed」: 非シールドクラスの理解 ## 概要 Javaの「non-sealed」キーワードは、シールドクラスの機能に関連し、サブクラスの継承を制御するために使用されます。このキーワードを使用することで、特定のクラスがサブクラス化できるかどうかを明示的に指定するこ...
Meta Keywords: sealed, non, class, extends, circle
-->

# Javaにおける「non-sealed」: 非シールドクラスの理解

## 概要
Javaの「non-sealed」キーワードは、シールドクラスの機能に関連し、サブクラスの継承を制御するために使用されます。このキーワードを使用することで、特定のクラスがサブクラス化できるかどうかを明示的に指定することができます。

## ドキュメンテーション
### 目的
「non-sealed」キーワードは、シールドクラスの一部として機能し、クラスの継承の制約を緩和するために用いられます。シールドクラスは、継承可能なサブクラスを制限することができますが、`non-sealed`を使用することで、その制限を解除し、他のクラスが自由にサブクラス化できるようにします。

### 使用法
`non-sealed`は、シールドクラスのサブクラスに適用します。以下のように記述します。

```java
sealed class Parent permits Child1, Child2 {
}

non-sealed class Child1 extends Parent {
}

class Child2 extends Parent {
}
```

上記のコードでは、`Parent`クラスがシールドクラスとして定義され、そのサブクラスとして`Child1`（`non-sealed`）と`Child2`が存在します。`Child1`は自由にサブクラス化できますが、`Child2`はそれを許可されていません。

### 詳細
- **シールドクラスとの関係**: `non-sealed`はシールドクラスのサブクラスにのみ適用でき、`sealed`または`non-sealed`のどちらかを指定する必要があります。
- **コンパイラーの動作**: `non-sealed`が指定されたクラスは、他のクラスからの継承を許可します。これにより、柔軟性が増しますが、設計上の意図を明確にすることが重要です。

## 例
```java
sealed class Shape permits Circle, Rectangle {
}

non-sealed class Circle extends Shape {
    // Circleの実装
}

class Rectangle extends Shape {
    // Rectangleの実装
}

// Circleはさらにサブクラス化可能
class LargeCircle extends Circle {
    // LargeCircleの実装
}
```

上記の例では、`Shape`クラスがシールドされ、`Circle`は`non-sealed`として宣言されているため、`LargeCircle`は`Circle`からサブクラス化可能です。

## 説明
### よくある落とし穴
- **設計の一貫性**: `non-sealed`を使用する際は、クラスの設計が一貫していることを確認することが重要です。無制限にサブクラスを作成できるため、コードの可読性や保守性が低下する恐れがあります。
- **適切な場面での使用**: `non-sealed`は、状況に応じて使用すべきです。すべてのシールドクラスのサブクラスに対して`non-sealed`を使用することは推奨されません。

## 一文要約
Javaの「non-sealed」キーワードは、シールドクラスのサブクラス化を許可し、柔軟なクラス設計を可能にします。