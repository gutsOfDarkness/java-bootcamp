# Chapter 17: Inheritance Example (Practical)

## Practical Examples

### Example 1: Creating Subclasses

**Problem Statement:**
Create a superclass `Animal` with a method `makeSound()`. Then, create two subclasses `Dog` and `Cat` that override the `makeSound()` method to print different sounds.

**Code:**
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

class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Meow");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        Animal myCat = new Cat();
        myDog.makeSound();
        myCat.makeSound();
    }
}
```

### Example 2: Using Inheritance

**Problem Statement:**
Create a superclass `Person` with fields `name` and `age`, and a method `display()`. Create a subclass `Student` that adds a field `studentId` and overrides the `display()` method.

**Code:**
```java
class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

class Student extends Person {
    String studentId;

    Student(String name, int age, String studentId) {
        super(name, age);
        this.studentId = studentId;
    }

    @Override
    void display() {
        super.display();
        System.out.println("Student ID: " + studentId);
    }
}

public class Main {
    public static void main(String[] args) {
        Student student = new Student("Alice", 20, "S12345");
        student.display();
    }
}
```

### Example 3: Method Overriding

**Problem Statement:**
Create a superclass `Shape` with a method `draw()`. Create two subclasses `Circle` and `Rectangle` that override the `draw()` method to print different shapes.

**Code:**
```java
class Shape {
    void draw() {
        System.out.println("Drawing a shape");
    }
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
        Shape myCircle = new Circle();
        Shape myRectangle = new Rectangle();
        myCircle.draw();
        myRectangle.draw();
    }
}
```
