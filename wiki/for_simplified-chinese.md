<!--
Meta Description: # Java中的for循环：用法、示例与注意事项 ## 摘要 Java中的`for`循环是一种控制结构，用于在满足特定条件的情况下重复执行代码块。它提供了简洁的语法，适用于已知执行次数的迭代。 ## 文档 `for`循环的基本语法如下： ```java for (初始化; 条件; 更新) { // ...
Meta Keywords: java, public, string, int, system
-->

# Java中的for循环：用法、示例与注意事项

## 摘要
Java中的`for`循环是一种控制结构，用于在满足特定条件的情况下重复执行代码块。它提供了简洁的语法，适用于已知执行次数的迭代。

## 文档
`for`循环的基本语法如下：

```java
for (初始化; 条件; 更新) {
    // 循环体
}
```

- **初始化**：在循环开始时执行，通常用于定义和初始化循环变量。
- **条件**：在每次循环迭代之前评估。如果条件为`true`，则执行循环体；如果为`false`，则终止循环。
- **更新**：在每次循环体执行完毕后执行，通常用于更新循环变量。

### 目的
`for`循环主要用于在已知循环次数时进行迭代操作，例如遍历数组或执行特定次数的任务。

### 用法
`for`循环常见于各种场景，如：

- 遍历数组或集合
- 实现计数器
- 生成序列

## 示例
### 示例1：遍历数组
```java
public class ForLoopExample {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        for (int i = 0; i < numbers.length; i++) {
            System.out.println(numbers[i]);
        }
    }
}
```

### 示例2：打印1到5的数字
```java
public class ForLoopExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
        }
    }
}
```

### 示例3：使用增强for循环遍历集合
```java
import java.util.ArrayList;

public class ForEachExample {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("苹果");
        fruits.add("香蕉");
        fruits.add("橘子");

        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

## 解释
### 常见陷阱与注意事项
1. **无限循环**：如果循环条件始终为`true`，将导致无限循环，造成程序卡死。
   ```java
   for (int i = 0; i < 10; i--) { // 这将导致无限循环
       System.out.println(i);
   }
   ```

2. **循环变量的作用域**：在`for`循环中定义的变量在循环外不可用。
   ```java
   for (int i = 0; i < 5; i++) {
       // do something
   }
   // System.out.println(i); // 编译错误，i超出作用域
   ```

3. **使用增强for循环**：增强`for`循环（也称为“for-each”循环）是遍历集合和数组的简洁方法，但无法获得索引。

## 一句话总结
Java中的`for`循环是一种强大且灵活的控制结构，用于在满足特定条件的情况下重复执行代码块。