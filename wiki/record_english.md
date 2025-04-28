<!--
Meta Description: # Understanding Java Records: A Simplified Data Structure ## Synopsis Java Records are a special feature introduced in Java 14 as a preview and made s...
Meta Keywords: java, records, record, data, methods
-->

# Understanding Java Records: A Simplified Data Structure

## Synopsis
Java Records are a special feature introduced in Java 14 as a preview and made stable in Java 16, aimed at simplifying the creation and management of data carrier classes. They provide a concise way to create immutable data structures, automatically generating boilerplate code such as constructors, getters, `equals()`, `hashCode()`, and `toString()` methods.

## Documentation
### Purpose
Java Records are designed to reduce the verbosity of traditional Java classes that are primarily used to hold data. By encapsulating immutable data and automatically generating common methods, records facilitate cleaner and more maintainable code.

### Usage
To define a record in Java, use the `record` keyword followed by the record name and its components. The syntax is as follows:

```java
record RecordName(Type1 component1, Type2 component2, ...) { }
```

### Details
- **Immutability**: Once a record is created, its fields cannot be changed. This guarantees thread safety and ensures that the data remains consistent throughout its lifecycle.
- **Automatic Methods**: Java automatically generates the following methods for records:
  - Constructor for initialization
  - `equals(Object obj)` for equality checks
  - `hashCode()` for hash code generation
  - `toString()` for string representation
- **No Inheritance**: Records cannot extend other classes but can implement interfaces.
- **Compact Constructor**: Records allow a compact constructor for additional validation or logic during initialization.

## Examples
Here are some basic usage examples of Java Records:

### Example 1: Defining a Simple Record
```java
public record Person(String name, int age) { }

public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 30);
        System.out.println(person);
    }
}
```
Output:
```
Person[name=Alice, age=30]
```

### Example 2: Using a Compact Constructor
```java
public record Point(int x, int y) {
    public Point {
        if (x < 0 || y < 0) {
            throw new IllegalArgumentException("Coordinates must be non-negative");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Point point = new Point(5, 10);
        System.out.println(point);
    }
}
```

## Explanation
### Common Pitfalls
- **Mutable State**: Since records are immutable, attempting to change a field after creation will result in a compilation error.
- **No Inheritance**: Records cannot extend other classes, which may restrict their use in certain design patterns.
- **Method Overriding**: While you can provide custom implementations for `equals`, `hashCode`, or `toString`, it is recommended to consider the implications on equality and hashing.

### Gotchas
- **No Setter Methods**: Records do not provide setter methods for their fields, reinforcing immutability.
- **Cannot Have Instance Fields**: All fields in a record must be declared in the record header and cannot be modified afterwards.

## One Line Summary
Java Records provide a concise and immutable way to create data carrier classes, automatically generating essential methods for enhanced maintainability and readability.