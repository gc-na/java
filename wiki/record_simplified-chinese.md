<!--
Meta Description: # Java 中的 Record：简化数据类的定义 ## 摘要 Java 中的 `record` 是一种新型的数据类，用于简化不可变数据对象的定义。它在 Java 14 中引入，并在 Java 16 中成为标准特性。`record` 提供了一种简洁且清晰的方式来创建只包含数据的类。 ## 文档 ##...
Meta Keywords: record, java, person, public, name
-->

# Java 中的 Record：简化数据类的定义

## 摘要
Java 中的 `record` 是一种新型的数据类，用于简化不可变数据对象的定义。它在 Java 14 中引入，并在 Java 16 中成为标准特性。`record` 提供了一种简洁且清晰的方式来创建只包含数据的类。

## 文档
### 目的
`record` 的主要目的是减少样板代码，特别是在定义只包含字段的类时。通过使用 `record`，开发者可以自动生成 `equals()`、`hashCode()`、`toString()` 方法以及构造函数，从而提高代码的可读性和可维护性。

### 用法
在 Java 中定义 `record` 的基本语法如下：
```java
public record RecordName(Type1 field1, Type2 field2) { }
```
- `RecordName` 是记录类的名称。
- `field1` 和 `field2` 是记录的字段名及其类型。

`record` 可以用在任何需要数据传递的场景，如 API 传输对象、配置类等。

### 详细说明
- **不可变性**：一旦创建，记录的字段值不能被修改。
- **构造函数**：自动生成的构造函数接受所有字段并初始化。
- **访问器**：为每个字段生成访问器方法，命名为 `fieldName()`。
- **功能**：`record` 类自动实现 `equals()` 和 `hashCode()` 方法，确保对象在比较时基于字段值。
- **序列化**：`record` 也支持序列化，适合用于网络传输和持久化存储。

## 示例
以下是一个简单的 `record` 定义和使用示例：

```java
public record Person(String name, int age) { }

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 30);
        System.out.println(person.name()); // 输出: Alice
        System.out.println(person.age());  // 输出: 30
        System.out.println(person);         // 输出: Person[name=Alice, age=30]
    }
}
```

## 说明
- **常见陷阱**：`record` 只支持不可变字段，因此不适合需要可变状态的对象。
- **嵌套记录**：可以在 `record` 中使用其他记录作为字段，但要确保数据结构的清晰性。
- **继承限制**：`record` 不能扩展其他类，只能实现接口。

## 一句话总结
Java 的 `record` 提供了一种高效且简洁的方式来定义不可变数据类。