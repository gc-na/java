<!--
Meta Description: # Javaの「record」: クラスの新しい形 ## 概要 Javaの「record」は、Java 14でプレビュー機能として導入され、Java 16で正式に追加された新しいデータ型です。主に不変のデータキャリアとして使用され、簡潔にデータクラスを定義するための構文を提供します。 ## ドキュメ...
Meta Keywords: record, java, book, public, string
-->

# Javaの「record」: クラスの新しい形

## 概要
Javaの「record」は、Java 14でプレビュー機能として導入され、Java 16で正式に追加された新しいデータ型です。主に不変のデータキャリアとして使用され、簡潔にデータクラスを定義するための構文を提供します。

## ドキュメンテーション
### 目的
「record」は、データを保持するためのクラスを簡単に定義するために設計されています。この機能により、ボイラープレートコードを削減し、データクラスの定義をより直感的にします。

### 使用法
`record`キーワードを使用してクラスを定義します。このクラスは、指定したフィールドを自動的に持つ不変のオブジェクトを生成します。たとえば、次のように定義できます。

```java
public record Person(String name, int age) {}
```

この`Person`レコードは、`name`と`age`の2つのフィールドを持ち、それぞれのフィールドに対するゲッターが自動的に生成されます。

### 詳細
- **不変性**: `record`で定義されたクラスは不変であり、フィールドの値は変更できません。
- **自動生成**: `record`は、`equals()`, `hashCode()`, および `toString()` メソッドを自動的に生成します。
- **コンストラクタ**: 自動的に生成されるコンストラクタは、フィールドの順序に基づいた引数を持ちます。

## 例
以下は、`record`を使用した基本的な例です。

```java
public record Book(String title, String author) {}

public class Main {
    public static void main(String[] args) {
        Book book = new Book("Java Programming", "John Doe");
        System.out.println(book.title()); // "Java Programming"
        System.out.println(book.author()); // "John Doe"
    }
}
```

## 説明
### 一般的な落とし穴
- **不変性の理解**: レコードは不変であり、一度オブジェクトが生成されると、そのフィールドの値を変更できません。この性質を理解していないと、意図しないバグを引き起こす可能性があります。
- **継承の制約**: `record`は他のクラスから継承することができません。すべてのレコードは自動的に`java.lang.Record`クラスを拡張します。

### 注意点
- レコードは、シリアライズ可能なデータクラスとして使用されることが一般的です。
- ゲッターはフィールド名と同じ名前を持ちますが、フィールドは不変です。

## 一文要約
Javaの「record」は、不変のデータキャリアを簡潔に定義するための新しい構文です。