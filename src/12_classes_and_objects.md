---
title: "Classes and Objects"
previous: /_posts/11_introduction_to_oop.md
next: /_posts/13_classes_and_objects_example.md
---
# Chapter 12: Classes and Objects

## Theoretical Overview (1000 words)

### Understanding Classes: The Blueprint of Objects
A class in Java is fundamentally a blueprint or template that defines the structure and behavior of objects. Just as an architectural blueprint specifies every detail of a house before construction, a class defines the attributes (data) and methods (behaviors) that future objects will possess.

#### Anatomy of a Class
A typical Java class consists of several key components:
1. **Class Declaration**: Defines the class name and visibility
2. **Instance Variables (Fields)**: Represent the object's state
3. **Constructors**: Special methods for initializing objects
4. **Methods**: Define the behaviors and actions of objects

```java
public class Car {
    // Instance Variables (Fields)
    private String model;
    private String color;
    private int year;
    
    // Constructor
    public Car(String model, String color, int year) {
        this.model = model;
        this.color = color;
        this.year = year;
    }
    
    // Method
    public void displayCarInfo() {
        System.out.println("Model: " + model + ", Color: " + color + ", Year: " + year);
    }
}
```

### Objects: Living Instances of Classes
An object is a concrete instance of a class, created with the `new` keyword. Each object has its own unique set of instance variables but shares the method definitions with its class.

#### Object Lifecycle
1. **Declaration**: Defining a reference variable
2. **Instantiation**: Creating the object using `new`
3. **Initialization**: Setting initial state
4. **Usage**: Interacting with the object
5. **Destruction**: Becoming eligible for garbage collection

```java
// Object creation and usage
Car myCar = new Car("Toyota", "Blue", 2022);
myCar.displayCarInfo();
```

### Constructors: Object Initialization Mechanisms
Constructors are special methods that initialize objects when they are created. They have the same name as the class and no return type.

#### Types of Constructors
1. **Default Constructor**: Provided automatically if no constructor is defined
2. **Parameterized Constructor**: Accepts arguments for initial object setup
3. **Copy Constructor**: Creates a new object based on an existing object

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
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    // Copy Constructor
    public Student(Student other) {
        this.name = other.name;
        this.age = other.age;
    }
}
```

### Access Modifiers: Controlling Object Interactions
Access modifiers determine the visibility and accessibility of class members:
- **public**: Accessible from anywhere
- **private**: Accessible only within the same class
- **protected**: Accessible within the same package and subclasses
- **default (no modifier)**: Accessible within the same package

```java
public class BankAccount {
    private double balance;  // Only accessible within the class
    
    public void deposit(double amount) {  // Publicly accessible method
        if (amount > 0) {
            balance += amount;
        }
    }
}
```

### Method Overloading: Flexible Method Definitions
Method overloading allows multiple methods with the same name but different parameter lists.

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
    
    public double add(double a, double b) {
        return a + b;
    }
}
```

## Code Examples

### Example 1: Basic Class and Object Creation
**Problem Statement**: Design a simple library book tracking system.

```java
public class Book {
    private String title;
    private String author;
    private boolean isAvailable;
    
    public Book(String title, String author) {
        this.title = title;
        this.author = author;
        this.isAvailable = true;
    }
    
    public void displayInfo() {
        System.out.println("Title: " + title);
        System.out.println("Author: " + author);
        System.out.println("Available: " + (isAvailable ? "Yes" : "No"));
    }
    
    public void borrowBook() {
        if (isAvailable) {
            isAvailable = false;
            System.out.println(title + " has been borrowed.");
        } else {
            System.out.println(title + " is not available.");
        }
    }
}
```

### Example 2: Complex Object Interactions
**Problem Statement**: Create a simple banking application demonstrating object relationships.

```java
public class BankAccount {
    private String accountNumber;
    private double balance;
    
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }
    
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: $" + amount);
        }
    }
    
    public boolean withdraw(double amount) {
        if (amount > 0 && balance >= amount) {
            balance -= amount;
            System.out.println("Withdrawn: $" + amount);
            return true;
        }
        return false;
    }
    
    public double getBalance() {
        return balance;
    }
}
```

### Example 3: Advanced Object Management
**Problem Statement**: Develop a student management system with comprehensive object interactions.

```java
public class Student {
    private String name;
    private int age;
    private double[] grades;
    
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
        this.grades = new double[5];
    }
    
    public void addGrade(int index, double grade) {
        if (index >= 0 && index < grades.length) {
            grades[index] = grade;
        }
    }
    
    public double calculateAverageGrade() {
        double total = 0;
        for (double grade : grades) {
            total += grade;
        }
        return total / grades.length;
    }
    
    public void displayStudentInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Average Grade: " + calculateAverageGrade());
    }
}
```

### Key Learning Objectives
1. Master the concept of classes as object blueprints
2. Understand object creation and lifecycle
3. Learn constructor variations and their purposes
4. Practice implementing methods and managing object state
5. Explore access modifiers and their significance