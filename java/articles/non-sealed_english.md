<!--
Meta Description: # Understanding the "non-sealed" Modifier in Java: A Comprehensive Guide ## Synopsis In Java, the `non-sealed` modifier is a keyword introduced in Jav...
Meta Keywords: sealed, class, non, interface, java
-->

# Understanding the "non-sealed" Modifier in Java: A Comprehensive Guide

## Synopsis
In Java, the `non-sealed` modifier is a keyword introduced in Java 17 that allows a class to indicate that it can be subclassed further, even when it is part of a sealed class hierarchy. This article explores the purpose, usage, and implications of the `non-sealed` modifier in Java programming.

## Documentation
### Purpose
The `non-sealed` modifier is used in the context of sealed classes and interfaces. A sealed class or interface restricts which classes or interfaces can extend or implement it. By marking a subclass as `non-sealed`, developers can allow it to be extended by any class, thereby providing flexibility within a controlled hierarchy.

### Usage
To use `non-sealed`, a class must be a subclass of a sealed class or interface. The basic syntax is as follows:

```java
sealed class Parent permits Child1, Child2 {
    // class implementation
}

non-sealed class Child1 extends Parent {
    // class implementation
}
```

In this example, `Child1` is a `non-sealed` subclass of the sealed class `Parent`. This means that other classes can extend `Child1`, while `Child2` remains sealed.

### Details
- **Sealed Class/Interface**: A class or interface that restricts which other classes or interfaces can extend or implement it, defined using the `sealed` keyword.
- **Permitted Subclasses**: The `permits` clause in a sealed class specifies which classes are allowed to extend it.
- **Non-Sealed Subclasses**: The `non-sealed` modifier allows further extensions, breaking out of the sealed hierarchy.

## Examples
### Example 1: Basic Non-Sealed Class
```java
sealed class Animal permits Dog, Cat {
    // Base class implementation
}

non-sealed class Dog extends Animal {
    // Dog implementation
}

class Puppy extends Dog {
    // Puppy implementation
}
```
In this example, `Dog` is a `non-sealed` subclass of `Animal`, allowing `Puppy` to extend it.

### Example 2: Non-Sealed Interface
```java
sealed interface Shape permits Circle, Square {
    double area();
}

non-sealed interface Polygon extends Shape {
    int numberOfSides();
}

class Triangle implements Polygon {
    // Triangle implementation
    @Override
    public double area() {
        return 0.5 * base * height;
    }

    @Override
    public int numberOfSides() {
        return 3;
    }
}
```
Here, `Polygon` is a `non-sealed` interface permitting further implementations like `Triangle`.

## Explanation
### Common Pitfalls
- **Using Non-Sealed Incorrectly**: Attempting to declare a `non-sealed` class or interface without it being a subclass of a sealed class will result in a compilation error.
- **Hierarchy Complexity**: Introducing `non-sealed` classes into a sealed hierarchy can lead to complexities in understanding the relationships and behavior of classes. It's important to maintain clarity in the design.

### Gotchas
- **Design Intent**: The use of `non-sealed` should be intentional. Overusing it can undermine the benefits of a sealed hierarchy, which aims to provide a controlled extension mechanism.
- **Compatibility**: Ensure that all subclasses adhere to the design principles of the sealed class. Mixing `sealed` and `non-sealed` can lead to unexpected behavior if not managed carefully.

## One Line Summary
The `non-sealed` modifier in Java allows subclasses of sealed classes to be freely extended, providing flexibility within a controlled class hierarchy.