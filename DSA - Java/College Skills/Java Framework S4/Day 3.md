### Topic 
- Class and objects
- Encapsulation

### Notes

##### Creating Object
   `` className objectName = new className();``

### Tasks

##### Library Management System

Develop a simple Library Management System in Java that incorporates the concepts of classes, objects, constructors, methods, encapsulation, and data abstraction. Create the following classes:

Book Class:
Attributes: Book ID, Title, Author, Availability (boolean), etc.

Methods: Constructor to initialize the book details, methods to get and set availability, display book information.

Library Class:
Attributes: List of books (an array or collection), etc.
Methods: Method to add books to the library, display available books, borrow a book, return a book.  
  
User Interface:
Implement a simple user interface (command-line or graphical) for users to interact with the Library Management System.

Allow users to view available books, borrow a book, return a book, etc.

```Java
import java.util.*;  
  
public class DaySkill {  
        public void main(String[] args) {  
            Library library = new Library();  
            
            library.addBook(new Book(1, "Java Programming", "John Doe"));  
            library.addBook(new Book(2, "Python Programming", "Jane Smith"));  
            library.addBook(new Book(3, "C++ Programming", "Alan Turing"));  
            
            Scanner scanner = new Scanner(System.in);  
            
            while (true) {  
                System.out.println("\nMenu:");  
                System.out.println("1. View available books");  
                System.out.println("2. Borrow a book");  
                System.out.println("3. Return a book");  
                System.out.println("4. Exit");  
                System.out.print("Enter your choice: ");  
                int choice = scanner.nextInt();  
                 
                switch (choice) {  
                    case 1:  
                        library.displayAvailableBooks();  
                        break;  
                    case 2:  
                        System.out.print("Enter the book ID to borrow: ");  
                        int borrowId = scanner.nextInt();  
                        library.borrowBook(borrowId);  
                        break;  
                    case 3:  
                        System.out.print("Enter the book ID to return: ");  
                        int returnId = scanner.nextInt();  
                        library.returnBook(returnId);  
                        break;  
                    case 4:  
                        System.out.println("Exiting...");  
                        System.exit(0);  
                        break;  
                    default:  
                        System.out.println("Invalid choice. Please try again.");  
                }  
            }  
        }  
    }  
    
    class Book {  
        private int bookId;  
        private String title;  
        private String author;  
        private boolean availability;  
        
        public Book(int bookId, String title, String author) {  
            this.bookId = bookId;  
            this.title = title;  
            this.author = author;  
            this.availability = true;  
        }  
        
        public int getBookId() {  
            return bookId;  
        }  
        public String getTitle() {  
            return title;  
        }  
        public String getAuthor() {  
            return author;  
        }  
        public boolean isAvailable() {  
            return availability;  
        }  
        public void setAvailability(boolean availability) {  
            this.availability = availability;  
        }  
        public void displayBookInfo() {  
            System.out.println("Book ID: " + bookId);  
            System.out.println("Title: " + title);  
            System.out.println("Author: " + author);  
            System.out.println("Availability: " + (availability ? "Available" : "Not Available"));  
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
        public void displayAvailableBooks() {  
            System.out.println("Available Books:");  
            for (Book book : books) {  
                if (book.isAvailable()) {  
                    book.displayBookInfo();  
                }  
            }  
        }  
        public void borrowBook(int bookId) {  
            for (Book book : books) {  
                if (book.getBookId() == bookId && book.isAvailable()) {  
                    book.setAvailability(false);  
                    System.out.println("Book successfully borrowed.");  
                    return;  
                }  
            }  
            System.out.println("Book not found or not available for borrowing.");  
        }  
        
        public void returnBook(int bookId) {  
            for (Book book : books) {  
                if (book.getBookId() == bookId && !book.isAvailable()) {  
                    book.setAvailability(true);  
                    System.out.println("Book successfully returned.");  
                    return;  
                }  
            }  
            System.out.println("Book not found or already available.");  
        }  
	}
```


##### Employee Payroll System

Build an Employee Payroll System in Java that showcases the concepts of classes, objects, constructors, methods, encapsulation, and data abstraction. Create the following classes:

Employee Class:
Attributes: Employee ID, Name, Position, Salary, etc.
Methods: Constructor to initialize employee details, methods to calculate and retrieve salary, display employee information.

Payroll Processor Class:
Attributes: List of employees (an array or collection), etc.
Methods: Method to add employees, calculate total payroll, display employee details, etc.

User Interface:
Implement a user interface (command-line or graphical) for users to interact with the Employee Payroll System.
Allow users to add employees, view employee details, calculate total payroll, etc

```Java
import java.util.ArrayList;  
import java.util.List;  
import java.util.Scanner;  
  
class Employee {  
    private int employeeId;  
    private String name;  
    private String position;  
    private double salary;  
    public Employee(int employeeId, String name, String position, double salary) {  
        this.employeeId = employeeId;  
        this.name = name;  
        this.position = position;  
        this.salary = salary;  
    }  
    public int getEmployeeId() {  
        return employeeId;  
    }  
    public String getName() {  
        return name;  
    }  
    public String getPosition() {  
        return position;  
    }  
    public double getSalary() {  
        return salary;  
    }  
    public void displayEmployeeInfo() {  
        System.out.println("Employee ID: " + employeeId);  
        System.out.println("Name: " + name);  
        System.out.println("Position: " + position);  
        System.out.println("Salary: $" + salary);  
    }  
}  
  
class PayrollProcessor {  
    private List<Employee> employees;  
    public PayrollProcessor() {  
        this.employees = new ArrayList<>();  
    }  
    public void addEmployee(Employee employee) {  
        employees.add(employee);  
    }  
    public double calculateTotalPayroll() {  
        double totalPayroll = 0;  
        for (Employee employee : employees) {  
            totalPayroll += employee.getSalary();  
        }  
        return totalPayroll;  
    }  
    
    public void displayEmployeeDetails() {  
        System.out.println("Employee Details:");  
        for (Employee employee : employees) {  
            employee.displayEmployeeInfo();  
        }  
    }  
}  
  
class PayRollProcess {  
    public static void main(String[] args) {  
        PayrollProcessor payrollProcessor = new PayrollProcessor();  
        Scanner scanner = new Scanner(System.in);  
        
        while (true) {  
            System.out.println("\nMenu:");  
            System.out.println("1. Add Employee");  
            System.out.println("2. View Employee Details");  
            System.out.println("3. Calculate Total Payroll");  
            System.out.println("4. Exit");  
            System.out.print("Enter your choice: ");  
            int choice = scanner.nextInt();  
            
            switch (choice) {  
                case 1:  
                    System.out.print("Enter Employee ID: ");  
                    int employeeId = scanner.nextInt();  
                    System.out.print("Enter Name: ");  
                    String name = scanner.next();  
                    System.out.print("Enter Position: ");  
                    String position = scanner.next();  
                    System.out.print("Enter Salary: ");  
                    double salary = scanner.nextDouble();  
                    Employee employee = new Employee(employeeId, name, position, salary);  
                    payrollProcessor.addEmployee(employee);  
                    break;  
                case 2:  
                    payrollProcessor.displayEmployeeDetails();  
                    break;  
                case 3:  
                    double totalPayroll = payrollProcessor.calculateTotalPayroll();  
                    System.out.println("Total Payroll: $" + totalPayroll);  
                    break;  
                case 4:  
                    System.out.println("Exiting...");  
                    System.exit(0);  
                    break;  
                default:  
                    System.out.println("Invalid choice. Please try again.");  
            }  
        }  
    }  
}
```