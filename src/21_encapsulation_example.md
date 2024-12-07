# Chapter 21: Encapsulation Example (Practical)

## Practical Examples

### Example 1: Using Access Modifiers

**Problem Statement:**
Create a class `BankAccount` with private fields `accountNumber` and `balance`. Provide public getters and setters for these fields.

**Code:**
```java
public class BankAccount {
    private String accountNumber;
    private double balance;

    // Getter for accountNumber
    public String getAccountNumber() {
        return accountNumber;
    }

    // Setter for accountNumber
    public void setAccountNumber(String accountNumber) {
        this.accountNumber = accountNumber;
    }

    // Getter for balance
    public double getBalance() {
        return balance;
    }

    // Setter for balance
    public void setBalance(double balance) {
        this.balance = balance;
    }
}

public class Main {
    public static void main(String[] args) {
        BankAccount account = new BankAccount();
        account.setAccountNumber("123456789");
        account.setBalance(1000.0);
        System.out.println("Account Number: " + account.getAccountNumber());
        System.out.println("Balance: " + account.getBalance());
    }
}
```

### Example 2: Implementing Getters and Setters

**Problem Statement:**
Create a class `Employee` with private fields `name` and `salary`. Provide public getters and setters for these fields.

**Code:**
```java
public class Employee {
    private String name;
    private double salary;

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for salary
    public double getSalary() {
        return salary;
    }

    // Setter for salary
    public void setSalary(double salary) {
        this.salary = salary;
    }
}

public class Main {
    public static void main(String[] args) {
        Employee emp = new Employee();
        emp.setName("John Doe");
        emp.setSalary(50000.0);
        System.out.println("Employee Name: " + emp.getName());
        System.out.println("Employee Salary: " + emp.getSalary());
    }
}
```

### Example 3: Encapsulation in Action

**Problem Statement:**
Create a class `Product` with private fields `id`, `name`, and `price`. Provide public getters and setters for these fields.

**Code:**
```java
public class Product {
    private int id;
    private String name;
    private double price;

    // Getter for id
    public int getId() {
        return id;
    }

    // Setter for id
    public void setId(int id) {
        this.id = id;
    }

    // Getter for name
    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter for price
    public double getPrice() {
        return price;
    }

    // Setter for price
    public void setPrice(double price) {
        this.price = price;
    }
}

public class Main {
    public static void main(String[] args) {
        Product product = new Product();
        product.setId(1);
        product.setName("Laptop");
        product.setPrice(75000.0);
        System.out.println("Product ID: " + product.getId());
        System.out.println("Product Name: " + product.getName());
        System.out.println("Product Price: " + product.getPrice());
    }
}
```