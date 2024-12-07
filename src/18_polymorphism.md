# Chapter 18: Polymorphism (Theory)

Polymorphism is one of the core concepts of Object-Oriented Programming (OOP). It allows objects to be treated as instances of their parent class rather than their actual class. The two types of polymorphism in Java are compile-time (or static) polymorphism and runtime (or dynamic) polymorphism.

## Compile-time Polymorphism

Compile-time polymorphism is achieved through method overloading. Method overloading allows a class to have more than one method with the same name, as long as their parameter lists are different.

### Example:
```java
class MathOperations {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```

## Runtime Polymorphism

Runtime polymorphism is achieved through method overriding. Method overriding allows a subclass to provide a specific implementation of a method that is already defined in its superclass.

### Example:
```java
class Animal {
    void makeSound() {
        System.out.println("Some sound");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark");
    }
}
```

In the above example, the `makeSound()` method is overridden in the `Dog` class. When the method is called on an instance of `Dog`, the overridden method is executed.

## Benefits of Polymorphism

1. **Code Reusability:** Polymorphism allows for code to be reused across different classes.
2. **Flexibility:** It provides flexibility to the code by allowing objects to be treated as instances of their parent class.
3. **Maintainability:** Polymorphism makes the code more maintainable and easier to extend.

## Conclusion

Polymorphism is a powerful feature of OOP that enhances the flexibility and maintainability of the code. By allowing objects to be treated as instances of their parent class, polymorphism enables code reusability and flexibility.