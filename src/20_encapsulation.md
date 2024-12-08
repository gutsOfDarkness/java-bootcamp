---
title: "Encapsulation"
previous: /_posts/19_polymorphism_example.md
next: /_posts/21_encapsulation_example.md
---
# Chapter 20: Encapsulation (Theory)

Encapsulation is one of the fundamental principles of Object-Oriented Programming (OOP). It is the mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class are hidden from other classes and can be accessed only through the methods of their current class. This is also known as data hiding.

## Key Concepts of Encapsulation

### 1. Data Hiding
Encapsulation helps in protecting the data from unauthorized access and modification. By making the data members private, we can restrict their access from outside the class.

### 2. Access Modifiers
Access modifiers are keywords that set the accessibility of classes, methods, and other members. The most common access modifiers are:
- **private:** The member is accessible only within the same class.
- **default (no modifier):** The member is accessible within the same package.
- **protected:** The member is accessible within the same package and subclasses.
- **public:** The member is accessible from any other class.

### 3. Getters and Setters
Getters and setters are methods that provide access to the private data members. Getters return the value of a private field, while setters set the value of a private field.

### Example:
```java
public class Person {
    private String name;
    private int age;

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for age
    public int getAge() {
        return age;
    }

    // Setter for age
    public void setAge(int age) {
        this.age = age;
    }
}
```

## Benefits of Encapsulation

1. **Control:** Encapsulation provides control over the data by restricting unauthorized access and modification.
2. **Flexibility:** It allows the flexibility to change the implementation details without affecting the external code.
3. **Maintainability:** Encapsulation improves the maintainability of the code by keeping the data and methods that operate on the data together.
4. **Reusability:** Encapsulated code can be reused across different parts of the application.

## Conclusion

Encapsulation is a powerful feature of OOP that enhances the security, maintainability, and flexibility of the code. By hiding the data and providing controlled access through methods, encapsulation ensures that the data is protected and the code is easier to manage.
