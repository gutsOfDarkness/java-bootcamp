# Chapter 6: Operators and Expressions Example (Practical)

## Practical Applications of Operators and Expressions

In this chapter, we'll transform the theoretical knowledge of operators into practical, real-world programming scenarios. Our goal is to demonstrate how operators and expressions are used to solve practical problems, making abstract concepts tangible and immediately applicable.

### 1. Calculator Application

**Problem Statement**: 
Design a simple calculator that performs basic arithmetic operations while demonstrating various operators and error handling.

```java
import java.util.Scanner;

public class SimpleCalculator {
    // Method to perform basic arithmetic operations
    public static double calculate(double num1, double num2, char operator) {
        // Using switch expression to handle different operations
        return switch (operator) {
            case '+' -> num1 + num2;
            case '-' -> num1 - num2;
            case '*' -> num1 * num2;
            case '/' -> {
                // Handling division by zero with error checking
                if (num2 == 0) {
                    throw new ArithmeticException("Cannot divide by zero");
                }
                yield num1 / num2;
            }
            case '%' -> num1 % num2;
            default -> throw new IllegalArgumentException("Invalid operator");
        };
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            // User input for calculation
            System.out.print("Enter first number: ");
            double num1 = scanner.nextDouble();

            System.out.print("Enter operator (+, -, *, /, %): ");
            char operator = scanner.next().charAt(0);

            System.out.print("Enter second number: ");
            double num2 = scanner.nextDouble();

            // Performing calculation and displaying result
            double result = calculate(num1, num2, operator);
            System.out.printf("Result: %.2f %c %.2f = %.2f\n", num1, operator, num2, result);

        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());
        } catch (IllegalArgumentException e) {
            System.out.println("Invalid operation: " + e.getMessage());
        } catch (Exception e) {
            System.out.println("An unexpected error occurred.");
        }
    }
}
```

### 2. Grade Point Average (GPA) Calculator

**Problem Statement**: 
Create a program that calculates a student's GPA using compound assignment and logical operators.

```java
public class GPACalculator {
    public static void main(String[] args) {
        // Course grades and credit hours
        double[] grades = {3.7, 4.0, 3.3, 3.0, 3.5};
        int[] creditHours = {3, 4, 3, 2, 3};

        // Variables to track total grade points and credit hours
        double totalGradePoints = 0;
        int totalCreditHours = 0;

        // Calculating GPA using compound operators
        for (int i = 0; i < grades.length; i++) {
            // Multiply grade by credit hours
            double gradePoints = grades[i] * creditHours[i];
            
            // Compound addition operators
            totalGradePoints += gradePoints;
            totalCreditHours += creditHours[i];
        }

        // Calculate GPA with precision
        double gpa = totalGradePoints / totalCreditHours;

        // Determine academic standing using logical operators
        boolean isHonorRoll = gpa >= 3.5;
        boolean isAcademicProbation = gpa < 2.0;

        // Output results
        System.out.printf("Total Grade Points: %.2f\n", totalGradePoints);
        System.out.printf("Total Credit Hours: %d\n", totalCreditHours);
        System.out.printf("GPA: %.2f\n", gpa);
        System.out.println("Honor Roll Status: " + (isHonorRoll ? "Yes" : "No"));
        System.out.println("Academic Probation: " + (isAcademicProbation ? "Yes" : "No"));
    }
}
```

### 3. Discount Calculator for E-commerce

**Problem Statement**: 
Develop a program that calculates product discounts using various operators and conditional logic.

```java
public class DiscountCalculator {
    // Method to calculate final price with multiple discount rules
    public static double calculateFinalPrice(double originalPrice, int quantity, boolean isNewCustomer) {
        // Base price calculation
        double totalPrice = originalPrice * quantity;

        // Discount calculations using compound operators
        // Quantity-based discount
        if (quantity > 10) {
            totalPrice *= 0.9;  // 10% discount for bulk purchase
        }

        // New customer bonus
        if (isNewCustomer) {
            totalPrice *= 0.95;  // Additional 5% off for new customers
        }

        // Seasonal discount logic using ternary and comparison operators
        boolean isSeasonalSale = true;
        double finalPrice = isSeasonalSale 
            ? (totalPrice * 0.85)  // 15% off during seasonal sale
            : totalPrice;

        // Rounding to two decimal places
        return Math.round(finalPrice * 100.0) / 100.0;
    }

    public static void main(String[] args) {
        // Test different scenarios
        double[] prices = {50.00, 100.00, 200.00};
        int[] quantities = {5, 15, 25};
        boolean[] customerStatuses = {true, false};

        for (double price : prices) {
            for (int quantity : quantities) {
                for (boolean isNewCustomer : customerStatuses) {
                    double finalPrice = calculateFinalPrice(price, quantity, isNewCustomer);
                    
                    System.out.printf("Original Price: $%.2f, Quantity: %d, New Customer: %b\n", 
                                      price, quantity, isNewCustomer);
                    System.out.printf("Final Price: $%.2f\n\n", finalPrice);
                }
            }
        }
    }
}
```

## Learning Objectives

Through these practical examples, you will:
1. Apply arithmetic, comparison, and logical operators in real-world scenarios
2. Understand how to handle complex computational logic
3. Learn error handling and input validation techniques
4. Practice using compound assignment and ternary operators
5. Develop problem-solving skills using Java's operator system

## Key Insights

- Operators are not just mathematical symbols but powerful tools for creating complex logic
- Careful operator selection can make code more readable and efficient
- Always consider edge cases and potential errors when designing computational logic
- Compound operators can simplify and streamline code

These examples demonstrate the versatility of Java operators, showing how they can be used to solve practical problems across different domains.