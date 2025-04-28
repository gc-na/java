<!--
Meta Description: # Javaにおける「return」文の完全ガイド ## 概要 Javaにおける「return」文は、メソッドから値を返すために使用される重要なキーワードです。これにより、メソッドの実行結果を呼び出し元に戻すことができます。 ## ドキュメント 「return」文は、メソッドの実行を終了し、オプショ...
Meta Keywords: return, example, public, int, sum
-->

# Javaにおける「return」文の完全ガイド

## 概要
Javaにおける「return」文は、メソッドから値を返すために使用される重要なキーワードです。これにより、メソッドの実行結果を呼び出し元に戻すことができます。

## ドキュメント
「return」文は、メソッドの実行を終了し、オプションで値を返すために使用されます。使用方法は次の通りです。

### 目的
- メソッドの実行結果を返す
- メソッドの処理を終了する

### 使用法
- 戻り値が必要なメソッドでは、戻り値の型を指定し、メソッド内で「return」文を使用して値を返します。
- 戻り値がないメソッド（voidメソッド）では、「return」文を指定することはできますが、値を返すことはできません。

### 詳細
- **戻り値の型**: メソッドが返す値の型を定義する必要があります。例えば、int型、String型、オブジェクト型など。
- **return文の構文**: `return [値];` または `return;`（voidメソッドの場合）

## 例
### 基本的な使用例
```java
public class Example {
    // 整数を返すメソッド
    public int add(int a, int b) {
        return a + b; // aとbの合計を返す
    }

    // voidメソッド
    public void displayMessage() {
        System.out.println("Hello, World!");
        return; // return文は省略可能
    }
    
    public static void main(String[] args) {
        Example example = new Example();
        int sum = example.add(5, 10);
        System.out.println("Sum: " + sum); // 出力: Sum: 15
        example.displayMessage(); // 出力: Hello, World!
    }
}
```

## 説明
### 一般的な落とし穴
- **戻り値の型と一致しない値**: メソッドの戻り値の型と一致しない値を「return」文で返すと、コンパイルエラーが発生します。
- **voidメソッドのreturn文**: voidメソッドでは「return;」を使うことができますが、値を返してはいけません。これは混乱を招くことがあります。
- **メソッドの最後におけるreturn文**: メソッドの最後に「return」文を置く必要はありませんが、条件に基づいて早期にメソッドを終了させるために使用することができます。

## 一文要約
Javaにおける「return」文は、メソッドの結果を返すための重要なキーワードであり、メソッドの実行を終了させる際に使用されます。