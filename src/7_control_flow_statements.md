# Chapter 7: Control Flow Statements

## Understanding Control Flow: Guiding Program Execution

Control flow statements are the decision-makers of your program. They determine the path your code takes, allowing you to create complex, dynamic behaviors by controlling how and when different blocks of code are executed. Think of control flow statements as the traffic signals of your program, directing the flow of execution based on specific conditions.

## Types of Control Flow Statements

### 1. Conditional Statements: If-Else

Conditional statements allow your program to make decisions. They evaluate a boolean expression and execute different code blocks based on whether the condition is true or false.

#### Basic If Statement
```java
if (condition) {
    // Code executed if condition is true
}
```

#### If-Else Statement
```java
if (condition) {
    // Code executed if condition is true
} else {
    // Code executed if condition is false
}
```

#### If-Else-If Ladder
```java
if (condition1) {
    // Executed if condition1 is true
} else if (condition2) {
    // Executed if condition2 is true
} else if (condition3) {
    // Executed if condition3 is true
} else {
    // Executed if no previous conditions are true
}
```

### 2. Switch Statements: Multiple Condition Evaluation

Switch statements provide an alternative to multiple if-else statements when comparing a single variable against multiple possible values.

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

#### Modern Java Switch Expression (Java 14+)
```java
int result = switch (day) {
    case MONDAY, TUESDAY, WEDNESDAY -> 6;
    case THURSDAY, FRIDAY -> 8;
    case SATURDAY, SUNDAY -> 0;
};
```

## Advanced Conditional Techniques

### Ternary Operator: Compact Conditional Expression
```java
// Syntax: condition ? valueIfTrue : valueIfFalse
int result = (age >= 18) ? 1 : 0;
```

### Nested Conditionals
```java
if (outerCondition) {
    if (innerCondition) {
        // Most specific condition
    }
}
```

## Control Flow Best Practices

1. **Keep Conditionals Simple**
   - Avoid deeply nested conditionals
   - Use early returns to reduce nesting
   
2. **Use Switch for Multiple Conditions**
   - Preferred when comparing a single variable against multiple values
   
3. **Prefer Explicit Conditions**
   - Write clear, readable boolean expressions
   - Avoid complex logical combinations

## Common Pitfalls

- Forgetting `break` in switch statements
- Unintended fall-through in switch cases
- Overly complex conditional logic

## Code Examples

### Example 1: User Authentication System (Problem Statement)
**Problem**: Create a user authentication system demonstrating various control flow techniques.

```java
public class AuthenticationSystem {
    // Simulate user roles and authentication
    public static String authenticateUser(String username, String password, boolean isAdmin) {
        // Nested conditional logic
        if (username == null || username.isEmpty()) {
            return "Invalid Username";
        }

        if (password == null || password.length() < 8) {
            return "Password Too Short";
        }

        // Switch expression for role-based access
        return switch (username) {
            case "admin" -> isAdmin ? "Admin Access Granted" : "Access Denied";
            case "manager" -> "Manager Dashboard";
            case "user" -> "Standard User Access";
            default -> "Unknown User";
        };
    }

    public static void main(String[] args) {
        // Test various authentication scenarios
        String[] usernames = {"admin", "manager", "user", ""};
        String[] passwords = {"adminpass", "managerpass", "userpass", ""};
        boolean[] adminStatuses = {true, false, false, false};

        for (int i = 0; i < usernames.length; i++) {
            String result = authenticateUser(usernames[i], passwords[i], adminStatuses[i]);
            System.out.println("User: " + usernames[i] + ", Result: " + result);
        }
    }
}
```

### Example 2: Grade Classification System (Problem Statement)
**Problem**: Develop a grade classification system using multiple control flow techniques.

```java
public class GradeClassifier {
    // Classify student performance using complex conditional logic
    public static String classifyGrade(double score) {
        // Using if-else-if ladder for grade classification
        if (score < 0 || score > 100) {
            return "Invalid Score";
        }

        // Ternary operator for pass/fail determination
        boolean isPassing = score >= 60;
        
        // Nested ternary for detailed grade classification
        return isPassing
            ? (score >= 90 ? "A (Excellent)" 
              : (score >= 80 ? "B (Very Good)" 
              : (score >= 70 ? "C (Good)" 
              : "D (Passing)")))
            : "F (Fail)";
    }

    public static void main(String[] args) {
        // Test grade classifications
        double[] scores = {45, 65, 75, 85, 95, 105};
        
        for (double score : scores) {
            String grade = classifyGrade(score);
            System.out.printf("Score: %.2f, Grade: %s\n", score, grade);
        }
    }
}
```

### Example 3: Seasonal Activity Recommender (Problem Statement)
**Problem**: Create a program that recommends activities based on season and temperature using switch and conditional statements.

```java
public class SeasonalActivityRecommender {
    // Recommend activities based on season and temperature
    public static String recommendActivity(String season, int temperature) {
        return switch (season.toLowerCase()) {
            case "summer" -> 
                temperature > 90 ? "Stay indoors with air conditioning" :
                temperature > 80 ? "Beach day or pool party" :
                "Outdoor sports and picnics";
            
            case "winter" ->
                temperature < 32 ? "Indoor activities, drink hot cocoa" :
                temperature < 50 ? "Skiing or snowboarding" :
                "Light winter walks";
            
            case "spring", "autumn" ->
                temperature > 70 ? "Hiking or gardening" :
                temperature > 50 ? "Outdoor photography" :
                "Museum visits or indoor crafts";
            
            default -> "Invalid season";
        };
    }

    public static void main(String[] args) {
        String[] seasons = {"summer", "winter", "spring", "autumn"};
        int[] temperatures = {95, 25, 65, 55};

        for (int i = 0; i < seasons.length; i++) {
            String recommendation = recommendActivity(seasons[i], temperatures[i]);
            System.out.printf("Season: %s, Temperature: %d°F\n", seasons[i], temperatures[i]);
            System.out.println("Recommended Activity: " + recommendation + "\n");
        }
    }
}
```

## Learning Objectives

By mastering control flow statements, you will:
1. Understand how to create decision-making logic in programs
2. Learn to handle complex conditional scenarios
3. Develop skills in writing clear, efficient conditional code
4. Explore different approaches to controlling program execution

## Key Takeaways

- Control flow statements are essential for creating dynamic, responsive programs
- Choose the right control flow technique based on your specific use case
- Strive for readability and simplicity in your conditional logic
- Modern Java provides powerful, concise ways to handle complex conditions

These examples demonstrate the versatility and power of control flow statements in Java, showing how they can be used to create intelligent, adaptive program behaviors.