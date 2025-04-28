<!--
Meta Description: # Understanding the "final" Keyword in Java: A Comprehensive Guide ## Synopsis The `final` keyword in Java is a modifier that can be applied to variab...
Meta Keywords: final, class, java, variables, methods
-->

# Understanding the "final" Keyword in Java: A Comprehensive Guide

## Synopsis
The `final` keyword in Java is a modifier that can be applied to variables, methods, and classes, indicating that the entity cannot be modified or overridden. It plays a critical role in ensuring immutability and maintaining the integrity of your code.

## Documentation

### Purpose
The `final` keyword serves various purposes depending on its context:
- **Final Variables**: Once assigned, their values cannot be changed.
- **Final Methods**: These cannot be overridden by subclasses.
- **Final Classes**: These cannot be subclassed.

### Usage
- **Final Variables**: To declare a variable as `final`, use the syntax:
  ```java
  final int x = 10;
  ```
  After this declaration, any attempt to reassign `x` will result in a compilation error.

- **Final Methods**: To prevent a method from being overridden in a subclass, declare it as `final`:
  ```java
  class Parent {
      final void display() {
          System.out.println("This is a final method.");
      }
  }
  ```

- **Final Classes**: To restrict the inheritance of a class, declare it as `final`:
  ```java
  final class FinalClass {
      // Class implementation
  }
  ```

### Details
- **Final Variables**: They must be initialized when declared or in the constructor if they are instance variables.
- **Final Methods**: Useful for maintaining the original behavior of a method in subclassing scenarios.
- **Final Classes**: Often used for utility classes that should not be extended, like `java.lang.Math`.

## Examples

### Final Variables
```java
public class FinalVariableExample {
    public static void main(String[] args) {
        final int MAX_VALUE = 100;
        // MAX_VALUE = 200;  // This will cause a compilation error
        System.out.println("Max Value: " + MAX_VALUE);
    }
}
```

### Final Methods
```java
class Base {
    final void show() {
        System.out.println("Final method in Base class.");
    }
}

class Derived extends Base {
    // void show() {   // This will cause a compilation error
    //     System.out.println("Trying to override.");
    // }
}
```

### Final Classes
```java
final class Utility {
    static void printMessage() {
        System.out.println("This is a utility class.");
    }
}

// class ExtendedUtility extends Utility {  // This will cause a compilation error
// }
```

## Explanation
Common pitfalls when using the `final` keyword include:
- **Reassigning Final Variables**: Attempting to change the value of a final variable after initialization leads to a compilation error. Thus, careful planning of your variables is essential.
- **Overriding Final Methods**: Developers might mistakenly think they can override a final method, which will cause a compilation error.
- **Inheriting Final Classes**: Declaring a class as final prevents any inheritance. If you plan on extending functionality in the future, consider this before making a class final.

### Additional Notes
- The `final` keyword can enhance performance in some scenarios, as the compiler can make optimizations knowing that certain methods or variables will not change.
- When using `final` with reference types (like objects), the reference itself cannot change, but the object's internal state can still be modified unless the object itself is designed to be immutable.

## One Line Summary
The `final` keyword in Java ensures that variables, methods, and classes maintain their original state and cannot be altered or overridden, promoting code stability and integrity.