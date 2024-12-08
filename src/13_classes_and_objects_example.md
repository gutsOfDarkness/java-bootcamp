---
title: "Classes and Objects Example"
previous: /_posts/12_classes_and_objects.md
next: /_posts/14_methods_and_constructors.md
---
# Chapter 13: Classes and Objects Example (Practical Implementation)

## Comprehensive Object-Oriented Programming Demonstration

### Introduction
This chapter builds upon the theoretical knowledge from Chapter 12, providing practical, real-world examples that showcase the power and flexibility of classes and objects in Java programming.

### Practical Scenario Overview
We'll explore three progressively complex scenarios that demonstrate object-oriented principles, highlighting how classes and objects can be used to model real-world systems effectively.

## Code Examples

### Example 1: Simple Library Management System
**Problem Statement**: Create a library management system that tracks books, allows borrowing, and manages inventory.

```java
import java.util.ArrayList;
import java.util.List;

class Book {
    private String title;
    private String author;
    private String isbn;
    private boolean isAvailable;
    
    public Book(String title, String author, String isbn) {
        this.title = title;
        this.author = author;
        this.isbn = isbn;
        this.isAvailable = true;
    }
    
    public boolean borrow() {
        if (isAvailable) {
            isAvailable = false;
            return true;
        }
        return false;
    }
    
    public void returnBook() {
        isAvailable = true;
    }
    
    @Override
    public String toString() {
        return "Title: " + title + ", Author: " + author + 
               ", ISBN: " + isbn + ", Available: " + isAvailable;
    }
}

class Library {
    private List<Book> books;
    
    public Library() {
        this.books = new ArrayList<>();
    }
    
    public void addBook(Book book) {
        books.add(book);
    }
    
    public Book findBookByIsbn(String isbn) {
        for (Book book : books) {
            if (book.toString().contains(isbn)) {
                return book;
            }
        }
        return null;
    }
    
    public void displayAllBooks() {
        for (Book book : books) {
            System.out.println(book);
        }
    }
}

public class LibraryManagementSystem {
    public static void main(String[] args) {
        Library library = new Library();
        
        // Adding books
        library.addBook(new Book("Java Programming", "John Doe", "ISBN-001"));
        library.addBook(new Book("Object-Oriented Design", "Jane Smith", "ISBN-002"));
        
        // Display all books
        library.displayAllBooks();
        
        // Borrow a book
        Book bookToBorrow = library.findBookByIsbn("ISBN-001");
        if (bookToBorrow != null && bookToBorrow.borrow()) {
            System.out.println("Book borrowed successfully.");
        } else {
            System.out.println("Book cannot be borrowed.");
        }
    }
}
```

### Example 2: Student Grade Management System
**Problem Statement**: Develop a comprehensive student grade tracking and analysis system.

```java
import java.util.ArrayList;
import java.util.List;

class Student {
    private String name;
    private String studentId;
    private List<Double> grades;
    
    public Student(String name, String studentId) {
        this.name = name;
        this.studentId = studentId;
        this.grades = new ArrayList<>();
    }
    
    public void addGrade(double grade) {
        if (grade >= 0 && grade <= 100) {
            grades.add(grade);
        } else {
            System.out.println("Invalid grade. Must be between 0 and 100.");
        }
    }
    
    public double calculateAverageGrade() {
        if (grades.isEmpty()) {
            return 0.0;
        }
        
        double sum = 0;
        for (Double grade : grades) {
            sum += grade;
        }
        return sum / grades.size();
    }
    
    public String getGradeClassification() {
        double average = calculateAverageGrade();
        
        if (average >= 90) return "A";
        if (average >= 80) return "B";
        if (average >= 70) return "C";
        if (average >= 60) return "D";
        return "F";
    }
    
    @Override
    public String toString() {
        return "Name: " + name + 
               ", Student ID: " + studentId + 
               ", Average Grade: " + calculateAverageGrade() + 
               ", Grade Classification: " + getGradeClassification();
    }
}

class StudentManagementSystem {
    private List<Student> students;
    
    public StudentManagementSystem() {
        this.students = new ArrayList<>();
    }
    
    public void addStudent(Student student) {
        students.add(student);
    }
    
    public Student findStudentById(String studentId) {
        for (Student student : students) {
            if (student.toString().contains(studentId)) {
                return student;
            }
        }
        return null;
    }
    
    public void displayAllStudents() {
        for (Student student : students) {
            System.out.println(student);
        }
    }
}

public class StudentGradeTracker {
    public static void main(String[] args) {
        StudentManagementSystem system = new StudentManagementSystem();
        
        // Create and add students
        Student student1 = new Student("Alice Johnson", "ST-001");
        student1.addGrade(85.5);
        student1.addGrade(92.3);
        student1.addGrade(78.6);
        
        Student student2 = new Student("Bob Smith", "ST-002");
        student2.addGrade(75.2);
        student2.addGrade(88.7);
        student2.addGrade(65.4);
        
        system.addStudent(student1);
        system.addStudent(student2);
        
        // Display all students and their grades
        system.displayAllStudents();
    }
}
```

### Example 3: Banking Application with Advanced Object Interactions
**Problem Statement**: Create a comprehensive banking system demonstrating complex object relationships and interactions.

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Date;

class Transaction {
    private Date timestamp;
    private String type;
    private double amount;
    
    public Transaction(String type, double amount) {
        this.timestamp = new Date();
        this.type = type;
        this.amount = amount;
    }
    
    @Override
    public String toString() {
        return "Type: " + type + 
               ", Amount: $" + amount + 
               ", Time: " + timestamp;
    }
}

class BankAccount {
    private String accountNumber;
    private String accountHolder;
    private double balance;
    private List<Transaction> transactionHistory;
    
    public BankAccount(String accountHolder, String accountNumber) {
        this.accountHolder = accountHolder;
        this.accountNumber = accountNumber;
        this.balance = 0.0;
        this.transactionHistory = new ArrayList<>();
    }
    
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            transactionHistory.add(new Transaction("Deposit", amount));
            System.out.println("Deposit of $" + amount + " successful.");
        } else {
            System.out.println("Invalid deposit amount.");
        }
    }
    
    public boolean withdraw(double amount) {
        if (amount > 0 && balance >= amount) {
            balance -= amount;
            transactionHistory.add(new Transaction("Withdrawal", amount));
            System.out.println("Withdrawal of $" + amount + " successful.");
            return true;
        } else {
            System.out.println("Insufficient funds or invalid withdrawal amount.");
            return false;
        }
    }
    
    public void printTransactionHistory() {
        System.out.println("Transaction History for " + accountHolder);
        for (Transaction transaction : transactionHistory) {
            System.out.println(transaction);
        }
    }
    
    public double getBalance() {
        return balance;
    }
}

class Bank {
    private List<BankAccount> accounts;
    
    public Bank() {
        this.accounts = new ArrayList<>();
    }
    
    public BankAccount createAccount(String accountHolder) {
        String accountNumber = generateAccountNumber();
        BankAccount newAccount = new BankAccount(accountHolder, accountNumber);
        accounts.add(newAccount);
        return newAccount;
    }
    
    private String generateAccountNumber() {
        // Simple account number generation
        return "ACC-" + (accounts.size() + 1);
    }
}

public class BankingApplication {
    public static void main(String[] args) {
        Bank bank = new Bank();
        
        // Create bank accounts
        BankAccount account1 = bank.createAccount("Alice Johnson");
        BankAccount account2 = bank.createAccount("Bob Smith");
        
        // Perform transactions
        account1.deposit(1000.0);
        account1.withdraw(300.0);
        account1.deposit(500.0);
        
        account2.deposit(2000.0);
        account2.withdraw(750.0);
        
        // Print transaction histories
        account1.printTransactionHistory();
        account2.printTransactionHistory();
    }
}
```

### Key Learning Objectives
1. Understand complex object interactions
2. Learn to design interconnected classes
3. Practice implementing real-world scenarios using OOP principles
4. Develop skills in creating robust and flexible class structures
5. Explore advanced object management techniques