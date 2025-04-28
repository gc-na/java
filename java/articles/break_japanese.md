<!--
Meta Description: # Javaの「break」文: 制御フローのための命令 ## 概要 Javaにおける「break」文は、ループやswitch文の実行を中断するための制御フロー命令です。この命令を使用することで、条件に応じてループを早期に終了させることが可能になります。 ## ドキュメンテーション ### 目的 「...
Meta Keywords: break, system, out, println, 現在の数
-->

# Javaの「break」文: 制御フローのための命令

## 概要
Javaにおける「break」文は、ループやswitch文の実行を中断するための制御フロー命令です。この命令を使用することで、条件に応じてループを早期に終了させることが可能になります。

## ドキュメンテーション
### 目的
「break」文は、for文、while文、do-while文、またはswitch文の流れを制御するために使用されます。特定の条件が満たされたときに、ループやswitchの処理を終了させることができ、プログラムの制御を次のステートメントに移す役割を果たします。

### 使用法
- **ループでの使用**:
  ```java
  for (int i = 0; i < 10; i++) {
      if (i == 5) {
          break; // iが5の時、ループを終了
      }
      System.out.println(i);
  }
  ```

- **switch文での使用**:
  ```java
  int day = 3;
  switch (day) {
      case 1:
          System.out.println("月曜日");
          break; // switchを抜ける
      case 2:
          System.out.println("火曜日");
          break;
      case 3:
          System.out.println("水曜日");
          break;
      default:
          System.out.println("無効な日");
  }
  ```

## 例
### 例1: ループの早期終了
```java
public class BreakExample {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            if (i == 7) {
                break; // iが7の時、ループを終了
            }
            System.out.println("現在の数: " + i);
        }
    }
}
```
*出力結果*:
```
現在の数: 0
現在の数: 1
現在の数: 2
現在の数: 3
現在の数: 4
現在の数: 5
現在の数: 6
```

### 例2: switch文の利用
```java
public class SwitchBreakExample {
    public static void main(String[] args) {
        int score = 85;
        switch (score / 10) {
            case 10:
            case 9:
                System.out.println("優");
                break;
            case 8:
                System.out.println("良");
                break;
            case 7:
                System.out.println("可");
                break;
            default:
                System.out.println("不可");
        }
    }
}
```
*出力結果*:
```
良
```

## 説明
### よくある落とし穴
- **break文のスコープ**: break文は、最も内側のループやswitch文にのみ影響を与えます。ネストされたループ内で使用する場合は、どのループを終了させるのかを理解しておくことが重要です。
  
- **ラベル付きbreak**: 複数のネストされたループがある場合、ラベルを使用して外側のループを終了させることもできます。例えば:
  ```java
  outerLoop:
  for (int i = 0; i < 5; i++) {
      for (int j = 0; j < 5; j++) {
          if (i == 2 && j == 2) {
              break outerLoop; // outerLoopを終了
          }
          System.out.println("i: " + i + ", j: " + j);
      }
  }
  ```

## 一行要約
Javaにおける「break」文は、ループやswitch文の実行を中断し、制御を次のステートメントに移すための命令です。