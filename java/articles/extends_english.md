<!--
Meta Description: # Understanding "extends" in Java: Inheritance Made Simple ## Synopsis The `extends` keyword in Java is used to create a subclass from a superclass, e...
Meta Keywords: class, subclass, java, inheritance, superclass
-->

# Understanding "extends" in Java: Inheritance Made Simple

## Synopsis
The `extends` keyword in Java is used to create a subclass from a superclass, enabling inheritance. This feature promotes code reusability and establishes a hierarchical relationship between classes.

## Documentation
The `extends` keyword is fundamental in Java's Object-Oriented Programming (OOP) paradigm, allowing developers to define a new class that inherits properties and behaviors (methods) from an existing class. The class that is being extended is known as the superclass or parent class, while the new class is termed the subclass or child class.

### Purpose
- **Code Reusability**: By extending a class, you can utilize existing code, reducing redundancy.
- **Hierarchical Classification**: It helps in organizing classes into a hierarchy, promoting logical structure and easier maintenance.
- **Polymorphism Support**: Subclasses can override methods, allowing for dynamic method resolution.

### Usage
To use the `extends` keyword, follow this syntax:

```java
class SubclassName extends SuperclassName {
    // Additional fields and methods
}
```

### Details
- A subclass inherits all accessible fields and methods (except private members) from its superclass.
- Java allows single inheritance only, meaning a class can only extend one superclass. However, a subclass can implement multiple interfaces.
- Constructors of the superclass are not inherited but can be called using `super()` within the subclass's constructor.

## Examples
### Basic Example of Inheritance

```java
// Superclass
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

// Subclass
class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}

// Main Class
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat(); // Inherited method
        dog.bark(); // Subclass method
    }
}
```

### Overriding Methods

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myCat = new Cat();
        myCat.sound(); // Output: Cat meows
    }
}
```

## Explanation
### Common Pitfalls
- **Private Members**: Private fields of a superclass are not accessible in a subclass. This can lead to confusion if developers expect to access them directly.
- **Constructor Calls**: Forgetting to invoke `super()` in the subclass constructor can lead to a compilation error if the superclass does not have a no-argument constructor.
- **Inheritance Depth**: Deep inheritance hierarchies can make code harder to read and maintain. Aim for a balance between inheritance and composition.

### Gotchas
- **Diamond Problem**: While Java does not support multiple inheritance of classes (to avoid the "diamond problem"), it allows a class to implement multiple interfaces. Be cautious of method signature conflicts when doing so.
- **Final Classes**: A class declared with the `final` keyword cannot be extended. Attempting to do so will result in a compilation error.

## One Line Summary
The `extends` keyword in Java is used for class inheritance, allowing a subclass to inherit fields and methods from a superclass, thus promoting code reusability and organization.