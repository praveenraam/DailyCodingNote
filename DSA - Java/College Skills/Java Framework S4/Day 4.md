### Topics 
- OOPS concept in Java

### Task 

##### Task 1:

**Shape Hierarchy**
Create a shape hierarchy in Java that utilizes inheritance, polymorphism, abstract classes, and interfaces. Define the following classes and interfaces:

**Shape (Abstract Class):**
Declare an abstract class Shape with attributes and methods common to all shapes.
Include abstract methods like calculate Area and calculate Perimeter.
  
**Circle Class (Subclass of Shape):**
Create a class Circle that extends the Shape class.
Implement necessary methods and attributes for a circle (e.g., radius).

**Rectangle Class (Subclass of Shape):**
Create a class Rectangle that extends the Shape class.
Implement necessary methods and attributes for a rectangle (e.g., length, width).

**Triangle Class (Subclass of Shape):**
Create a class Triangle that extends the Shape class.
Implement necessary methods and attributes for a triangle (e.g., base, height).

**Resizable Interface:**
Declare an interface Resizable with a method resize that can be implemented by shapes to resize them.

```Java
abstract class Shape {  
    abstract double calculateArea();  
    abstract double calculatePerimeter();  
}  
class Circle extends Shape {  
    private double radius;  
    public Circle(double radius) {  
        this.radius = radius;  
    }  
    @Override  
    double calculateArea() {  
        return Math.PI * radius * radius;  
    }  
    @Override  
    double calculatePerimeter() {  
        return 2 * Math.PI * radius;  
    }  
}  
class Rectangle extends Shape {  
    private double length;  
    private double width;  
    public Rectangle(double length, double width) {  
        this.length = length;  
        this.width = width;  
    }  
    @Override  
    double calculateArea() {  
        return length * width;  
    }  
    @Override  
    double calculatePerimeter() {  
        return 2 * (length + width);  
    }  
}   
class Triangle extends Shape {  
    private double base;  
    private double height;  
    public Triangle(double base, double height) {  
        this.base = base;  
        this.height = height;  
    }  
    @Override  
    double calculateArea() {  
        return 0.5 * base * height;  
    }  
    @Override  
    double calculatePerimeter() {  
        return 3 * base;  
    }  
}  
interface Resizable {  
    void resize(double factor);  
} 
public class DaySkill {  
    public static void main(String[] args) {  
  
        Shape circle = new Circle(5);  
        Shape rectangle = new Rectangle(4, 6);  
        Shape triangle = new Triangle(3, 4);  
  
        System.out.println("Circle Area: " + circle.calculateArea());  
        System.out.println("Circle Perimeter: " + circle.calculatePerimeter());  
  
        System.out.println("Rectangle Area: " + rectangle.calculateArea());  
        System.out.println("Rectangle Perimeter: " + rectangle.calculatePerimeter());  
  
        System.out.println("Triangle Area: " + triangle.calculateArea());  
        System.out.println("Triangle Perimeter: " + triangle.calculatePerimeter());  
    }  
}
```

##### Task 2

**Banking System with Interfaces Tas**
Develop a simplified banking system in Java that leverages interfaces for various account types. Create the following classes and interfaces:

**Account (Interface):**
Declare an interface Account with methods like deposit, withdraw, and get Balance.

**Savings Account Class (Implements Account):**
Create a class Savings Account that implements the Account interface.
Implement methods specific to a savings account, such as interest calculation.

**Current Account Class (Implements Account):**
Create a class Current Account that implements the Account interface
Implement methods specific to a current account, such as overdraft limit.

**Bank Class:**
Create a class Bank that manages a collection of accounts.
Demonstrate polymorphism by storing both Savings Account and Current Account objects in the same collection.

```Java
import java.util.*;  
interface Account {  
    void deposit(double amount);  
    void withdraw(double amount);  
    double getBalance();  
}  
  
class SavingsAccount implements Account {  
    private double balance;  
    private double interestRate;  
  
    public SavingsAccount(double balance, double interestRate) {  
        this.balance = balance;  
        this.interestRate = interestRate;  
    }  
  
    @Override  
    public void deposit(double amount) {  
        balance += amount;  
    }  
  
    @Override  
    public void withdraw(double amount) {  
        if (balance >= amount) {  
            balance -= amount;  
        } else {  
            System.out.println("Insufficient funds!");  
        }  
    }  
  
    public void calculateInterest() {  
        balance += balance * interestRate;  
    }  
    @Override  
    public double getBalance() {  
        return balance;  
    }  
}  
  
class CurrentAccount implements Account {  
    private double balance;  
    private double overdraftLimit;  
    
    public CurrentAccount(double balance, double overdraftLimit) {  
        this.balance = balance;  
        this.overdraftLimit = overdraftLimit;  
    }  
    
    @Override  
    public void deposit(double amount) {  
        balance += amount;  
    }   
    @Override  
    public void withdraw(double amount) {  
        if (balance - amount >= -overdraftLimit) {  
            balance -= amount;  
        } else {  
            System.out.println("Exceeds overdraft limit!");  
        }  
    }  
    @Override  
    public double getBalance() {  
        return balance;  
    }  
}  
  
// Bank Class  
class Bank {  
    private List<Account> accounts;  
    
    public Bank() {  
        accounts = new ArrayList<>();  
    }  
    public void addAccount(Account account) {  
        accounts.add(account);  
    }  
    
    public void displayAllBalances() {  
        for (Account account : accounts) {  
            System.out.println("Balance: " + account.getBalance());  
        }  
    }  
}  
 
public class Main {  
    public static void main(String[] args) {  
        Bank bank = new Bank();  
        
        Account savingsAccount = new SavingsAccount(1000, 0.05);  
        Account currentAccount = new CurrentAccount(2000, 500);  
        
        savingsAccount.deposit(500);  
        savingsAccount.withdraw(200);  
        
        currentAccount.deposit(1000);  
        currentAccount.withdraw(2500);  
        
        bank.addAccount(savingsAccount);  
        bank.addAccount(currentAccount);  
        
        bank.displayAllBalances();  
    }  
}
```