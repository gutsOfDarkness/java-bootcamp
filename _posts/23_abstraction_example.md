---
title: "Abstraction Example"
previous: /_posts/22_abstraction.md
next: /path/to/next
---
# Chapter 23: Abstraction Example (Practical)

## Practical Examples

### Example 1: Implementing Abstract Classes

**Problem Statement:**
Create an abstract class `Shape` with an abstract method `draw()`. Create two subclasses `Circle` and `Rectangle` that implement the `draw()` method.

**Code:**
```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle");
    }
}

class Rectangle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a rectangle");
    }
}

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle();
        Shape rectangle = new Rectangle();
        circle.draw();
        rectangle.draw();
    }
}
```

### Example 2: Using Interfaces

**Problem Statement:**
Create an interface `Animal` with a method `makeSound()`. Create two classes `Dog` and `Cat` that implement the `Animal` interface.

**Code:**
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

class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal dog = new Dog();
        Animal cat = new Cat();
        dog.makeSound();
        cat.makeSound();
    }
}
```

### Example 3: Multiple Interfaces

**Problem Statement:**
Create two interfaces `Printable` and `Showable` each with a method `print()` and `show()` respectively. Create a class `Document` that implements both interfaces.

**Code:**
```java
interface Printable {
    void print();
}

interface Showable {
    void show();
}

class Document implements Printable, Showable {
    @Override
    public void print() {
        System.out.println("Printing document");
    }

    @Override
    public void show() {
        System.out.println("Showing document");
    }
}

public class Main {
    public static void main(String[] args) {
        Document doc = new Document();
        doc.print();
        doc.show();
    }
}
```