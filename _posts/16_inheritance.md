---
title: "Inheritance"
previous: /_posts/15_methods_and_constructors_example.md
next: /_posts/17_inheritance_example.md
---
# Chapter 16: Inheritance in Java

## Understanding Inheritance

Inheritance is a fundamental principle of Object-Oriented Programming (OOP) that allows a class to inherit properties and methods from another class. It represents a relationship between two classes where one class (the child or subclass) derives characteristics from another class (the parent or superclass).

### Key Concepts of Inheritance

1. **Superclass (Parent Class)**: The class whose properties and methods are inherited.
2. **Subclass (Child Class)**: The class that inherits properties and methods from the superclass.
3. **Extends Keyword**: Used to establish an inheritance relationship in Java.

### Types of Inheritance

1. **Single Inheritance**: A subclass inherits from one superclass
2. **Multilevel Inheritance**: A class inherits from a class that itself has inherited from another class
3. **Hierarchical Inheritance**: Multiple classes inherit from a single superclass

### Inheritance Mechanics

When a class inherits from another:
- Subclass automatically gets all non-private members of the superclass
- Subclass can add its own methods and properties
- Subclass can override inherited methods to provide specialized implementation

### Method Overriding

Method overriding allows a subclass to provide a specific implementation of a method that is already defined in its superclass. Key rules include:
- Method in subclass must have same name and signature as in superclass
- Return type must be the same or a subtype
- Access modifier cannot be more restrictive

## Inheritance Example Demonstration

```java
// Superclass
class Animal {
    protected String name;
    
    public Animal(String name) {
        this.name = name;
    }
    
    public void eat() {
        System.out.println(name + " is eating");
    }
    
    public void sleep() {
        System.out.println(name + " is sleeping");
    }
}

// Subclass inheriting from Animal
class Dog extends Animal {
    private String breed;
    
    public Dog(String name, String breed) {
        super(name);  // Calling superclass constructor
        this.breed = breed;
    }
    
    // Method overriding
    @Override
    public void eat() {
        System.out.println(name + " the " + breed + " is eating dog food");
    }
    
    // Additional method specific to Dog
    public void bark() {
        System.out.println(name + " is barking");
    }
}
```

### Super Keyword

The `super` keyword is used to:
1. Call superclass constructor
2. Access superclass methods
3. Reference superclass variables

### Access Modifiers in Inheritance

- `public`: Accessible everywhere
- `protected`: Accessible within same package and subclasses
- `default`: Accessible within same package
- `private`: Not directly accessible in subclass

## Advanced Inheritance Concepts

### Multilevel Inheritance

```java
class Grandparent {
    void grandparentMethod() {
        System.out.println("Grandparent method");
    }
}

class Parent extends Grandparent {
    void parentMethod() {
        System.out.println("Parent method");
    }
}

class Child extends Parent {
    void childMethod() {
        System.out.println("Child method");
    }
}
```

### Abstract Classes in Inheritance

Abstract classes can define a template for subclasses, forcing them to implement certain methods.

```java
abstract class Shape {
    abstract double calculateArea();
    
    void display() {
        System.out.println("This is a shape");
    }
}

class Circle extends Shape {
    private double radius;
    
    Circle(double radius) {
        this.radius = radius;
    }
    
    @Override
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```

## Code Examples

### Problem Statement 1: Vehicle Inheritance Hierarchy
Create a vehicle management system demonstrating inheritance.

```java
class Vehicle {
    protected String brand;
    protected int year;

    public Vehicle(String brand, int year) {
        this.brand = brand;
        this.year = year;
    }

    public void start() {
        System.out.println("Vehicle is starting");
    }
}

class Car extends Vehicle {
    private int numDoors;

    public Car(String brand, int year, int numDoors) {
        super(brand, year);
        this.numDoors = numDoors;
    }

    @Override
    public void start() {
        System.out.println(brand + " car is starting");
    }

    public void honk() {
        System.out.println("Car is honking");
    }
}
```

### Problem Statement 2: Employee Payroll System
Design an inheritance-based employee management system.

```java
class Employee {
    protected String name;
    protected double baseSalary;

    public Employee(String name, double baseSalary) {
        this.name = name;
        this.baseSalary = baseSalary;
    }

    public double calculateSalary() {
        return baseSalary;
    }
}

class Manager extends Employee {
    private double bonus;

    public Manager(String name, double baseSalary, double bonus) {
        super(name, baseSalary);
        this.bonus = bonus;
    }

    @Override
    public double calculateSalary() {
        return baseSalary + bonus;
    }
}
```

### Problem Statement 3: Geometric Shape Calculator
Implement an inheritance-based shape calculation system.

```java
abstract class Shape {
    abstract double getArea();
    abstract double getPerimeter();
}

class Rectangle extends Shape {
    private double length;
    private double width;

    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }

    @Override
    double getArea() {
        return length * width;
    }

    @Override
    double getPerimeter() {
        return 2 * (length + width);
    }
}
```