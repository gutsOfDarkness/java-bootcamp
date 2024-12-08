---
title: "Control Flow Statements Example"
previous: /_posts/7_control_flow_statements.md
next: /_posts/9_loops.md
---
# Chapter 8: Control Flow Statements

## Theoretical Overview

### Introduction to Control Flow
Control flow statements are fundamental building blocks in Java that allow programmers to make decisions and control the execution of code based on specific conditions. They provide the ability to alter the sequential flow of a program, enabling more dynamic and responsive software design.

### If-Else Statements
The if-else statement is the most basic control flow mechanism in Java. It allows you to execute different code blocks based on whether a specific condition is true or false. The basic syntax follows a simple logic:
- If a condition is true, execute one block of code
- If the condition is false, execute an alternative block of code

#### Simple If Statement
The simplest form of control flow is the basic if statement:
```java
if (condition) {
    // Code to execute when condition is true
}
```

#### If-Else Statement
Expanding on the simple if statement, the if-else allows you to specify an alternative path:
```java
if (condition) {
    // Code to execute when condition is true
} else {
    // Code to execute when condition is false
}
```

#### Nested If-Else Statements
You can create more complex decision-making structures by nesting if-else statements:
```java
if (firstCondition) {
    // Code for first condition
} else if (secondCondition) {
    // Code for second condition
} else {
    // Default code if no conditions are met
}
```

### Switch Statements
Switch statements provide an alternative to multiple if-else statements when you want to compare a single variable against multiple possible values. They are particularly useful for handling multiple discrete conditions.

#### Basic Switch Syntax
```java
switch (variable) {
    case value1:
        // Code for value1
        break;
    case value2:
        // Code for value2
        break;
    default:
        // Code if no cases match
}
```

#### Enhanced Switch Statement (Java 12+)
Modern Java versions introduce a more concise switch syntax:
```java
switch (variable) {
    case value1 -> // Direct assignment or method call
    case value2 -> // Another direct action
    default -> // Default action
}
```

### Key Considerations
1. **Condition Evaluation**: Always ensure conditions are clear and precise
2. **Code Readability**: Use control flow to make code logic transparent
3. **Performance**: Choose the most appropriate control flow mechanism
4. **Avoid Unnecessary Complexity**: Keep decision-making structures as simple as possible

## Code Examples

### Example 1: Basic Grade Classification
**Problem Statement**: Write a program that classifies a student's grade based on their numeric score.

```java
public class GradeClassifier {
    public static void main(String[] args) {
        int score = 85;
        
        if (score >= 90) {
            System.out.println("Grade A: Excellent!");
        } else if (score >= 80) {
            System.out.println("Grade B: Very Good");
        } else if (score >= 70) {
            System.out.println("Grade C: Good");
        } else if (score >= 60) {
            System.out.println("Grade D: Satisfactory");
        } else {
            System.out.println("Grade F: Needs Improvement");
        }
    }
}
```

### Example 2: Switch Statement for Day of Week
**Problem Statement**: Create a program that prints the type of day based on the day number.

```java
public class DayTypeIdentifier {
    public static void main(String[] args) {
        int dayNumber = 6;
        
        switch (dayNumber) {
            case 1, 2, 3, 4, 5:
                System.out.println("Weekday");
                break;
            case 6, 7:
                System.out.println("Weekend");
                break;
            default:
                System.out.println("Invalid Day");
        }
    }
}
```

### Example 3: Complex Condition Handling
**Problem Statement**: Develop a program to determine loan eligibility based on multiple conditions.

```java
public class LoanEligibilityChecker {
    public static void main(String[] args) {
        int age = 28;
        double salary = 50000;
        boolean hasCreditHistory = true;
        
        if (age >= 25 && age <= 45) {
            if (salary >= 40000) {
                if (hasCreditHistory) {
                    System.out.println("Loan Approved!");
                } else {
                    System.out.println("Loan Requires Additional Review");
                }
            } else {
                System.out.println("Insufficient Salary");
            }
        } else {
            System.out.println("Age Not in Eligible Range");
        }
    }
}
```
