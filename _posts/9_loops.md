---
title: "Loops"
previous: /_posts/8_control_flow_statements_example.md
next: /_posts/10_loops_example.md
---
# Chapter 9: Loops

## Theoretical Overview (1000 words)

### Introduction to Loops
Loops are essential control flow mechanisms in Java that allow programmers to repeatedly execute a block of code. They provide an efficient way to perform repetitive tasks without writing redundant code. Java offers three primary types of loops: for loop, while loop, and do-while loop.

### For Loop
The for loop is the most structured and commonly used loop in Java. It is ideal when you know in advance how many times you want to iterate.

#### Basic For Loop Structure
```java
for (initialization; condition; update) {
    // Code to be repeated
}
```

##### Components of For Loop
1. **Initialization**: Sets the initial value of the loop variable
2. **Condition**: Determines how long the loop continues
3. **Update**: Modifies the loop variable after each iteration

#### Enhanced For Loop (For-Each Loop)
Introduced in Java 5, this loop simplifies iteration over arrays and collections:
```java
for (elementType element : collection) {
    // Process each element
}
```

### While Loop
The while loop executes a block of code as long as a specified condition remains true. It's useful when the number of iterations is not known beforehand.

#### Basic While Loop Structure
```java
while (condition) {
    // Code to be repeated
    // Update condition variable
}
```

#### Key Characteristics
- Condition is checked before each iteration
- Loop may not execute at all if condition is initially false
- Requires explicit condition management

### Do-While Loop
Similar to the while loop, but guarantees that the code block is executed at least once before checking the condition.

#### Basic Do-While Loop Structure
```java
do {
    // Code to be repeated
    // Update condition variable
} while (condition);
```

#### Unique Characteristics
- Condition is checked after each iteration
- Ensures the code block runs at least once
- Useful for scenarios requiring guaranteed first execution

### Loop Control Statements
Java provides additional loop control mechanisms:
- **break**: Exits the loop immediately
- **continue**: Skips the current iteration and moves to the next

### Best Practices
1. **Avoid Infinite Loops**: Always ensure loops have a clear termination condition
2. **Be Mindful of Performance**: Complex loops can impact application efficiency
3. **Use Appropriate Loop Type**: Choose the loop that best fits your specific scenario
4. **Keep Loop Bodies Concise**: Maintain readability and maintainability

## Code Examples

### Example 1: Multiplication Table Generator
**Problem Statement**: Create a program that generates a multiplication table for a given number.

```java
public class MultiplicationTableGenerator {
    public static void main(String[] args) {
        int number = 7;
        
        for (int i = 1; i <= 10; i++) {
            System.out.println(number + " x " + i + " = " + (number * i));
        }
    }
}
```

### Example 2: User Input Validation
**Problem Statement**: Implement a program that repeatedly asks for input until a valid response is received.

```java
import java.util.Scanner;

public class InputValidator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int userInput;
        
        do {
            System.out.print("Enter a number between 1 and 10: ");
            userInput = scanner.nextInt();
        } while (userInput < 1 || userInput > 10);
        
        System.out.println("Valid input received: " + userInput);
    }
}
```

### Example 3: Advanced Array Processing
**Problem Statement**: Develop a program that processes an array using different loop types and demonstrates loop control statements.

```java
public class ArrayProcessor {
    public static void main(String[] args) {
        int[] numbers = {10, 25, 30, 45, 60, 75, 90};
        int sum = 0;
        
        // Enhanced for loop for processing
        for (int num : numbers) {
            if (num > 50) {
                continue; // Skip numbers greater than 50
            }
            sum += num;
        }
        
        System.out.println("Sum of numbers <= 50: " + sum);
    }
}
```