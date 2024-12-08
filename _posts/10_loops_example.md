---
title: "Loops Example"
previous: /_posts/9_loops.md
next: /_posts/11_introduction_to_oop.md
---
# Chapter 10: Loops Example (Practical Implementation)

## Comprehensive Loops Demonstration

### Introduction
This chapter builds upon the theoretical knowledge of loops from Chapter 9, providing practical, real-world examples that showcase the versatility and power of loops in Java programming.

### Practical Scenario Overview
We'll explore three progressively complex scenarios that demonstrate different loop types, highlighting their unique characteristics and use cases.

## Code Examples

### Example 1: Simple Array Manipulation
**Problem Statement**: Create a program that calculates the average of numbers in an array using a standard for loop.

```java
public class ArrayAverage {
    public static void main(String[] args) {
        int[] numbers = {12, 45, 67, 23, 89, 54, 32};
        int sum = 0;
        
        // Using a standard for loop to calculate sum
        for (int i = 0; i < numbers.length; i++) {
            sum += numbers[i];
        }
        
        double average = (double) sum / numbers.length;
        System.out.println("Array Average: " + average);
    }
}
```

**Learning Objectives**:
- Understand how to iterate through array elements
- Perform calculations using loops
- Type casting for precise mathematical operations

### Example 2: User Interaction and Input Validation
**Problem Statement**: Develop a guessing game that uses a while loop for continuous play and input validation.

```java
import java.util.Random;
import java.util.Scanner;

public class NumberGuessingGame {
    public static void main(String[] args) {
        Random random = new Random();
        Scanner scanner = new Scanner(System.in);
        
        int targetNumber = random.nextInt(100) + 1;
        int userGuess;
        int attempts = 0;
        
        System.out.println("Welcome to the Number Guessing Game!");
        
        while (true) {
            System.out.print("Guess a number between 1 and 100: ");
            userGuess = scanner.nextInt();
            attempts++;
            
            if (userGuess == targetNumber) {
                System.out.println("Congratulations! You guessed the number in " + attempts + " attempts.");
                break;
            } else if (userGuess < targetNumber) {
                System.out.println("Too low. Try again!");
            } else {
                System.out.println("Too high. Try again!");
            }
        }
        
        scanner.close();
    }
}
```

**Learning Objectives**:
- Implement an infinite loop with a break condition
- Use nested conditional statements
- Handle user interactions
- Demonstrate input validation techniques

### Example 3: Advanced List Processing
**Problem Statement**: Create a complex program that processes a list of student records, demonstrating nested loops and advanced filtering.

```java
import java.util.ArrayList;
import java.util.List;

class Student {
    String name;
    int age;
    double grade;
    
    Student(String name, int age, double grade) {
        this.name = name;
        this.age = age;
        this.grade = grade;
    }
}

public class StudentRecordProcessor {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();
        students.add(new Student("Alice", 22, 85.5));
        students.add(new Student("Bob", 20, 78.3));
        students.add(new Student("Charlie", 23, 92.1));
        students.add(new Student("Diana", 21, 88.7));
        
        // Nested loop for comprehensive student analysis
        for (Student student : students) {
            System.out.println("\nAnalyzing student: " + student.name);
            
            // Performance categorization
            if (student.grade >= 90) {
                System.out.println("Excellent Performance!");
            } else if (student.grade >= 80) {
                System.out.println("Very Good Performance");
            } else {
                System.out.println("Satisfactory Performance");
            }
            
            // Age-based scholarship eligibility
            if (student.age <= 22 && student.grade >= 85) {
                System.out.println("Eligible for Scholarship");
            } else {
                System.out.println("Not eligible for Scholarship");
            }
        }
    }
}
```

**Learning Objectives**:
- Work with custom objects and lists
- Use enhanced for-each loop
- Implement complex conditional logic
- Demonstrate object-oriented programming concepts alongside loop usage

## Key Takeaways
1. Loops are versatile tools for repetitive tasks
2. Choose the right loop type based on specific requirements
3. Combine loops with conditional statements for powerful data processing
4. Practice and experiment to gain loop mastery

**Pro Tips**:
- Always have a clear termination condition
- Be cautious of performance implications with nested loops
- Use break and continue judiciously
- Consider performance and readability when designing loop structures