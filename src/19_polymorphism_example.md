# Chapter 19: Polymorphism Example (Practical)

## Practical Examples

### Example 1: Method Overloading

**Problem Statement:**
Create a class `Calculator` with overloaded methods `add()` to add integers and doubles.

**Code:**
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println("Sum of integers: " + calc.add(5, 10));
        System.out.println("Sum of doubles: " + calc.add(5.5, 10.5));
    }
}
```

### Example 2: Method Overriding

**Problem Statement:**
Create a superclass `Vehicle` with a method `move()`. Create a subclass `Car` that overrides the `move()` method.

**Code:**
```java
class Vehicle {
    void move() {
        System.out.println("Vehicle is moving");
    }
}

class Car extends Vehicle {
    @Override
    void move() {
        System.out.println("Car is moving");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle myCar = new Car();
        myCar.move();
    }
}
```

### Example 3: Polymorphic Behavior

**Problem Statement:**
Create a superclass `Employee` with a method `work()`. Create two subclasses `Developer` and `Manager` that override the `work()` method. Demonstrate polymorphic behavior by calling the `work()` method on instances of `Developer` and `Manager`.

**Code:**
```java
class Employee {
    void work() {
        System.out.println("Employee is working");
    }
}

class Developer extends Employee {
    @Override
    void work() {
        System.out.println("Developer is coding");
    }
}

class Manager extends Employee {
    @Override
    void work() {
        System.out.println("Manager is managing");
    }
}

public class Main {
    public static void main(String[] args) {
        Employee emp1 = new Developer();
        Employee emp2 = new Manager();
        emp1.work();
        emp2.work();
    }
}
```