<!--
Meta Description: # Understanding "const" in Java: A Comprehensive Guide ## Synopsis In Java, the term "const" is a reserved keyword that is not used in the language. T...
Meta Keywords: final, java, class, keyword, const
-->

# Understanding "const" in Java: A Comprehensive Guide

## Synopsis
In Java, the term "const" is a reserved keyword that is not used in the language. This article explores the implications of "const," its intended purpose, and how Java employs alternative mechanisms for defining constants.

## Documentation
### Purpose
The `const` keyword is part of Java's reserved keywords, but it is not implemented in the language. Originally, it was intended to signify a constant variable that cannot be modified after its initial assignment. However, Java developers typically use the `final` keyword for this purpose.

### Usage
Although `const` cannot be used in Java, the `final` keyword serves a similar purpose. When a variable is declared using `final`, it means that once the variable has been assigned a value, it cannot be reassigned. This is crucial for defining constants in Java programs.

```java
final int MAX_USERS = 100;
```

In the example above, `MAX_USERS` is a constant integer with a value of 100. Any attempt to change `MAX_USERS` after its declaration will result in a compilation error.

### Details
- **Reserved Keyword**: The `const` keyword is reserved in Java but is not functional, meaning it cannot be used in the code.
- **Final Keyword**: The `final` keyword is the correct choice for defining constants in Java. It can be applied to variables, methods, and classes:
  - **Variables**: A variable declared as `final` cannot be reassigned.
  - **Methods**: A method declared as `final` cannot be overridden in subclasses.
  - **Classes**: A class declared as `final` cannot be subclassed.

## Examples
### Example 1: Using `final` with a Variable
```java
public class Constants {
    public static final int DAYS_IN_WEEK = 7;

    public static void main(String[] args) {
        System.out.println("Days in a week: " + DAYS_IN_WEEK);
    }
}
```
In this example, `DAYS_IN_WEEK` is a constant representing the number of days in a week.

### Example 2: Using `final` with a Method
```java
class Parent {
    public final void display() {
        System.out.println("This is a final method.");
    }
}

class Child extends Parent {
    // Uncommenting the below method will cause a compilation error
    // public void display() {
    //     System.out.println("Trying to override final method.");
    // }
}
```
In this case, the `display` method in the `Parent` class cannot be overridden in the `Child` class.

### Example 3: Using `final` with a Class
```java
final class ImmutableClass {
    // Class content goes here
}

// Uncommenting the below class will cause a compilation error
// class ExtendedClass extends ImmutableClass {}
```
Here, `ImmutableClass` cannot be extended because it is declared as `final`.

## Explanation
### Common Pitfalls
1. **Confusion with Other Languages**: Developers coming from languages like C or C++ might expect `const` to function similarly in Java. It’s crucial to remember that `const` is not used in Java, and `final` should be used instead.
   
2. **Incorrect Use of `final`**: While `final` prevents reassignment, it does not make reference types immutable. For example, if a `final` variable is a reference to an object, the object's internal state can still be modified.

### Gotchas
- **Static Final**: In Java, static final variables are typically written in uppercase letters, which is a widely accepted naming convention for constants.
- **Final Arguments**: Method parameters can also be declared as `final`, which prevents the parameter from being reassigned inside the method body.

## One Line Summary
In Java, the `const` keyword is reserved but unused; instead, the `final` keyword is utilized to create constants and define non-modifiable variables, methods, and classes.