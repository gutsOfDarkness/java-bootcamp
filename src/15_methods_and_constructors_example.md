---
title: "Methods and Constructors Example"
previous: /_posts/14_methods_and_constructors.md
next: /_posts/16_inheritance.md
---
# Chapter 15: Methods and Constructors in Java

## Understanding Methods

Methods are fundamental building blocks in Java that encapsulate a set of instructions designed to perform a specific task. They are essential for organizing code, promoting reusability, and creating modular programs. A method is essentially a block of code that only runs when it is called, allowing developers to break down complex problems into smaller, manageable pieces.

### Method Definition and Structure

A typical method in Java consists of several key components:
1. Access Modifier (optional): Defines the visibility of the method
2. Return Type: Specifies the type of value the method will return
3. Method Name: A descriptive identifier for the method
4. Parameters (optional): Input values the method can accept
5. Method Body: The actual code to be executed

```java
accessModifier returnType methodName(parameters) {
    // Method body
    // Code to be executed
    return value; // If return type is not void
}
```

### Method Signatures

A method signature includes the method name and parameter list. Java uses method signatures to distinguish between different methods, enabling method overloading.

### Method Overloading

Method overloading allows multiple methods with the same name but different parameter lists within the same class. This provides flexibility in method usage and improves code readability.

Example of Method Overloading:
```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }

    public int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

## Understanding Constructors

Constructors are special methods used to initialize objects when they are created. They have the same name as the class and do not have a return type. Constructors ensure that an object is created in a valid state by setting initial values to object attributes.

### Types of Constructors

1. Default Constructor
   - Automatically created by Java if no constructor is defined
   - Takes no parameters
   - Initializes object with default values

2. Parameterized Constructor
   - Accepts parameters to initialize object attributes
   - Allows custom initialization of object state

### Constructor Overloading

Similar to method overloading, constructor overloading allows multiple constructors with different parameter lists.

Example of Constructor Overloading:
```java
public class Student {
    private String name;
    private int age;

    // Default Constructor
    public Student() {
        name = "Unknown";
        age = 0;
    }

    // Parameterized Constructor
    public Student(String name) {
        this.name = name;
        this.age = 0;
    }

    // Another Parameterized Constructor
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

### Constructor Chaining

Constructors can call other constructors using the `this()` keyword, which helps in reducing code duplication.

```java
public class Person {
    private String name;
    private int age;

    public Person() {
        this("Unknown", 0);  // Calls another constructor
    }

    public Person(String name) {
        this(name, 0);  // Calls constructor with two parameters
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

## Code Examples

### Problem Statement 1: Create a Bank Account Management System
Design a `BankAccount` class with constructors to initialize account details and methods to deposit and withdraw money.

```java
public class BankAccount {
    private String accountHolder;
    private double balance;

    // Default Constructor
    public BankAccount() {
        this.accountHolder = "Anonymous";
        this.balance = 0.0;
    }

    // Parameterized Constructor
    public BankAccount(String accountHolder, double initialBalance) {
        this.accountHolder = accountHolder;
        this.balance = initialBalance;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: $" + amount);
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawn: $" + amount);
        } else {
            System.out.println("Insufficient funds");
        }
    }

    public double getBalance() {
        return balance;
    }
}
```

### Problem Statement 2: Method Overloading for Shape Calculation
Create a class with overloaded methods to calculate the area of different shapes.

```java
public class ShapeCalculator {
    // Calculate area of a circle
    public double calculateArea(double radius) {
        return Math.PI * radius * radius;
    }

    // Calculate area of a rectangle
    public double calculateArea(double length, double width) {
        return length * width;
    }

    // Calculate area of a triangle
    public double calculateArea(double base, double height, boolean isTriangle) {
        return 0.5 * base * height;
    }
}
```

### Problem Statement 3: Constructor Chaining in Employee Management
Implement a class demonstrating constructor chaining with different initialization scenarios.

```java
public class Employee {
    private String name;
    private int id;
    private String department;

    public Employee() {
        this("Unknown", 0, "General");
    }

    public Employee(String name) {
        this(name, 0, "General");
    }

    public Employee(String name, int id) {
        this(name, id, "General");
    }

    public Employee(String name, int id, String department) {
        this.name = name;
        this.id = id;
        this.department = department;
    }

    public void displayDetails() {
        System.out.println("Name: " + name);
        System.out.println("ID: " + id);
        System.out.println("Department: " + department);
    }
}
```