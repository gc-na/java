<!--
Meta Description: # Understanding Sealed Classes and Interfaces in Java: A Comprehensive Guide ## Synopsis Sealed classes and interfaces in Java allow developers to con...
Meta Keywords: sealed, class, public, classes, final
-->

# Understanding Sealed Classes and Interfaces in Java: A Comprehensive Guide

## Synopsis
Sealed classes and interfaces in Java allow developers to control which classes or interfaces can extend or implement them, enhancing the robustness and maintainability of code. Introduced in Java 15 as a preview feature and standardized in Java 17, sealed types provide a way to define a restricted hierarchy.

## Documentation

### Purpose
Sealed classes and interfaces are designed to provide a more controlled inheritance model, allowing developers to specify a restricted set of subclasses. This feature helps in modeling domains with specific constraints and enforces a clear structure in the codebase.

### Usage
To declare a sealed class or interface, the `sealed` modifier is used in conjunction with the `permits` clause, which lists the permitted subclasses or implementations. A sealed class can only be extended by classes that are declared as `final`, `sealed`, or `non-sealed`.

### Declaration Syntax
```java
public sealed class ParentClass permits SubClassA, SubClassB {
    // Class implementation
}

public final class SubClassA extends ParentClass {
    // Class implementation
}

public non-sealed class SubClassB extends ParentClass {
    // Class implementation
}
```

### Key Points
- **Sealed Class**: A class that restricts which other classes may extend it.
- **Permits Clause**: Lists the classes that are allowed to extend the sealed class/interface.
- **Modifiers**: 
  - `final`: The class cannot be subclassed.
  - `sealed`: The class itself can be subclassed, but only by classes that are also sealed or final.
  - `non-sealed`: Allows further subclassing of the class implementing this modifier.

## Examples

### Example 1: Basic Sealed Class
```java
public sealed class Shape permits Circle, Square {
    // Common properties and methods
}

public final class Circle extends Shape {
    // Circle-specific implementation
}

public final class Square extends Shape {
    // Square-specific implementation
}
```

### Example 2: Sealed Interface
```java
public sealed interface Shape permits Circle, Square {
    double area();
}

public final class Circle implements Shape {
    private final double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double area() {
        return Math.PI * radius * radius;
    }
}

public final class Square implements Shape {
    private final double side;

    public Square(double side) {
        this.side = side;
    }

    @Override
    public double area() {
        return side * side;
    }
}
```

### Example 3: Using Non-Sealed
```java
public sealed class Vehicle permits Car, Truck {}

public final class Car extends Vehicle {}

public non-sealed class Truck extends Vehicle {
    // Truck can have further subclasses
}

public class Pickup extends Truck {
    // Pickup-specific implementation
}
```

## Explanation
### Common Pitfalls
- **Missing permits Clause**: When declaring a sealed class or interface, failing to include the `permits` clause will result in a compilation error.
- **Incorrect Permitted Subclasses**: Only classes declared within the `permits` section can extend a sealed class. Attempting to extend a sealed class with an unauthorized class will lead to an error.
- **Mixing Access Modifiers**: The visibility of the sealed class or interface and its subclasses must be considered, as public, protected, and package-private access can affect their usage.

### Additional Notes
- Sealed types are particularly useful in scenarios such as modeling finite state machines, where the set of states is known and fixed.
- They enhance code readability and maintenance by clearly indicating which classes are part of an inheritance hierarchy.

## One Line Summary
Sealed classes and interfaces in Java provide a mechanism to control inheritance, allowing developers to define a restricted set of subclasses for better code organization and maintainability.