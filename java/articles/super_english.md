<!--
Meta Description: # Understanding the "super" Keyword in Java: A Comprehensive Guide ## Synopsis The `super` keyword in Java is used to refer to the immediate parent cl...
Meta Keywords: parent, class, super, java, constructor
-->

# Understanding the "super" Keyword in Java: A Comprehensive Guide

## Synopsis
The `super` keyword in Java is used to refer to the immediate parent class of a class. It serves multiple purposes, including accessing parent class constructors, methods, and fields, thereby facilitating inheritance and polymorphism in object-oriented programming.

## Documentation

### Purpose
The `super` keyword is an integral part of Java's inheritance model. It allows a subclass to directly access the properties and methods of its parent class. This is particularly useful for:
- Invoking a parent class constructor.
- Accessing overridden methods from the parent class.
- Referring to parent class fields that may be hidden by subclass fields.

### Usage
The `super` keyword can be used in three primary contexts:
1. **Calling Parent Class Constructor**: It must be the first statement in the subclass constructor.
   ```java
   class Parent {
       Parent() {
           System.out.println("Parent Constructor");
       }
   }

   class Child extends Parent {
       Child() {
           super(); // Calls Parent constructor
           System.out.println("Child Constructor");
       }
   }
   ```

2. **Accessing Parent Class Methods**: This is useful when a subclass overrides a method and you want to call the parent version.
   ```java
   class Parent {
       void display() {
           System.out.println("Display from Parent");
       }
   }

   class Child extends Parent {
       void display() {
           super.display(); // Calls Parent's display method
           System.out.println("Display from Child");
       }
   }
   ```

3. **Accessing Parent Class Fields**: If a field in the subclass has the same name as a field in the parent class, `super` can be used to differentiate between them.
   ```java
   class Parent {
       int number = 10;
   }

   class Child extends Parent {
       int number = 20;

       void showNumbers() {
           System.out.println("Parent number: " + super.number); // Accesses Parent's number
           System.out.println("Child number: " + this.number); // Accesses Child's number
       }
   }
   ```

## Examples
### Example 1: Calling Parent Constructor
```java
class Animal {
    Animal() {
        System.out.println("Animal created");
    }
}

class Dog extends Animal {
    Dog() {
        super(); // Calls Animal constructor
        System.out.println("Dog created");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
    }
}
```

### Example 2: Accessing Overridden Methods
```java
class Vehicle {
    void start() {
        System.out.println("Vehicle started");
    }
}

class Car extends Vehicle {
    void start() {
        super.start(); // Calls Vehicle's start method
        System.out.println("Car started");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.start();
    }
}
```

### Example 3: Accessing Parent Class Fields
```java
class Base {
    String message = "Hello from Base";
}

class Derived extends Base {
    String message = "Hello from Derived";

    void printMessages() {
        System.out.println(super.message); // Accesses Base's message
        System.out.println(this.message); // Accesses Derived's message
    }
}

public class Main {
    public static void main(String[] args) {
        Derived derived = new Derived();
        derived.printMessages();
    }
}
```

## Explanation
While the `super` keyword is straightforward, there are some common pitfalls to be aware of:
- **Constructor Calls**: If `super()` is not explicitly called in the subclass constructor, Java inserts a default call to the parent constructor. If the parent class does not have a no-argument constructor, a compile-time error occurs.
- **Method Overriding**: When overriding methods, ensure that you use `super` when you need to invoke the parent class's version, as Java will call the overridden method in the subclass by default.
- **Field Hiding**: Be cautious when fields in the subclass hide fields in the parent class. Always use `super` when you want to access the parent class's field.

## One Line Summary
The `super` keyword in Java is used to access methods, fields, and constructors of a parent class, enhancing the capabilities of inheritance and polymorphism.