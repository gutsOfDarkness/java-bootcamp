---
title: "Abstraction"
previous: /_posts/21_encapsulation_example.md
next: /_posts/23_abstraction_example.md
---
# Chapter 22: Abstraction (Theory)

Abstraction is one of the key principles of Object-Oriented Programming (OOP). It is the process of hiding the implementation details and showing only the functionality to the user. Abstraction helps in reducing complexity and allows the programmer to focus on what an object does instead of how it does it.

## Key Concepts of Abstraction

### 1. Abstract Classes
An abstract class is a class that cannot be instantiated and is meant to be subclassed. It can have both abstract methods (without a body) and concrete methods (with a body). Abstract methods must be implemented by subclasses.

### Example:
```java
abstract class Animal {
    abstract void makeSound();

    void sleep() {
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark");
    }
}
```

### 2. Interfaces
An interface is a reference type in Java that is similar to a class. It is a collection of abstract methods. A class implements an interface, thereby inheriting the abstract methods of the interface. Interfaces are used to achieve complete abstraction.

### Example:
```java
interface Animal {
    void makeSound();
}

class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Bark");
    }
}
```

## Benefits of Abstraction

1. **Reduces Complexity:** By hiding the implementation details, abstraction reduces the complexity of the code.
2. **Increases Reusability:** Abstract classes and interfaces can be reused across different parts of the application.
3. **Enhances Maintainability:** Abstraction makes the code easier to maintain and modify.
4. **Improves Security:** By exposing only the necessary details, abstraction helps in protecting the data from unauthorized access.

## Conclusion

Abstraction is a powerful feature of OOP that helps in managing complexity and improving the maintainability of the code. By hiding the implementation details and exposing only the necessary functionality, abstraction allows the programmer to focus on what an object does rather than how it does it.