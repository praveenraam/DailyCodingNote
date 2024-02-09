### Topics covered
- File handling 
- Exception handling

### Task 1

**File Handling with Exception Handling**
- Create a Java program for reading data from a file and handling both checked and unchecked exceptions. Design the following features:

**File Reader Class:**
- Implement a class named File Reader with a method to read data from a file.
- Handle the checked exception File Not Found Exception when the specified file is not found.
- Utilize the try-catch block to catch the checked exception and provide a meaningful error message.

**Data Processing Class:**
- Create a class named Data Processing that uses the File Reader class to read data from a file.
- Perform some data processing operations on the read data (e.g., calculating the average, counting occurrences, etc.).
- Handle any unchecked exceptions that may occur during data processing using the try-catch block.
- Display the processed data or appropriate error messages.

```Java
import java.io.BufferedReader;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

class FileReaderClass {
    public void readFile(String fileName) {
        try {
            FileReader fileReader = new FileReader(fileName);
            BufferedReader bufferedReader = new BufferedReader(fileReader);

            String line;
            while ((line = bufferedReader.readLine()) != null) {
                System.out.println(line);
            }

            bufferedReader.close();
        } catch (FileNotFoundException e) {
            System.out.println("Error: File not found. Please provide a valid file name.");
        } catch (IOException e) {
            System.out.println("Error reading the file: " + e.getMessage());
        }
    }
}

class DataProcessing {
    public void processData(String fileName) {
        FileReaderClass fileReader = new FileReaderClass();
        try {
            fileReader.readFile(fileName);
            System.out.println("Data processing completed successfully.");
        } catch (Exception e) {
            System.out.println("Error processing data: " + e.getMessage());
        }
    }
}

public class Main {
    public static void main(String[] args) {
        String fileName = "example.txt";
        DataProcessing dataProcessing = new DataProcessing();
        dataProcessing.processData(fileName);
    }
}
```

**Task 2**

**Custom Exception Handling in Banking System**
- Develop a simple banking system in Java where custom exceptions are used to handle specific scenarios. Design the following classes:

**Account Class:**
- Implement a class named Account that represents a bank account.
- Include methods for deposit, withdraw, and checking the balance.
- Introduce custom exceptions like Insufficient Funds Exception for handling insufficient balance during withdrawals.

**Bank Class:**
- Create a class named Bank that manages a collection of bank accounts.
- Include methods for adding accounts, performing transactions, and displaying account details.
- Demonstrate the use of custom exceptions to handle scenarios like insufficient funds.

```Java
class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String message) {
        super(message);
    }
}
class Account {
    private String accountNumber;
    private double balance;

    public Account(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    public void deposit(double amount) {
        balance += amount;
        System.out.println("Deposited: $" + amount);
    }

    public void withdraw(double amount) throws InsufficientFundsException {
        if (amount > balance) {
            throw new InsufficientFundsException("Insufficient funds to withdraw $" + amount);
        }
        balance -= amount;
        System.out.println("Withdrawn: $" + amount);
    }

    public double getBalance() {
        return balance;
    }

    public String getAccountNumber() {
        return accountNumber;
    }
}
class Bank {
    private Account[] accounts;
    private int numAccounts;

    public Bank(int capacity) {
        accounts = new Account[capacity];
        numAccounts = 0;
    }

    public void addAccount(Account account) {
        if (numAccounts < accounts.length) {
            accounts[numAccounts] = account;
            numAccounts++;
            System.out.println("Account added successfully.");
        } else {
            System.out.println("Cannot add more accounts. Bank capacity reached.");
        }
    }

    public void performTransaction(String accountNumber, double amount, String transactionType) {
        for (int i = 0; i < numAccounts; i++) {
            if (accounts[i].getAccountNumber().equals(accountNumber)) {
                try {
                    if (transactionType.equals("deposit")) {
                        accounts[i].deposit(amount);
                    } else if (transactionType.equals("withdraw")) {
                        accounts[i].withdraw(amount);
                    } else {
                        System.out.println("Invalid transaction type.");
                    }
                    System.out.println("Current Balance: $" + accounts[i].getBalance());
                } catch (InsufficientFundsException e) {
                    System.out.println(e.getMessage());
                }
                return;
            }
        }
        System.out.println("Account not found.");
    }

    public void displayAccountDetails(String accountNumber) {
        for (int i = 0; i < numAccounts; i++) {
            if (accounts[i].getAccountNumber().equals(accountNumber)) {
                System.out.println("Account Number: " + accounts[i].getAccountNumber());
                System.out.println("Balance: $" + accounts[i].getBalance());
                return;
            }
        }
        System.out.println("Account not found.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create bank and accounts
        Bank bank = new Bank(10);
        Account account1 = new Account("123456", 1000);
        Account account2 = new Account("789012", 500);

        // Add accounts to bank
        bank.addAccount(account1);
        bank.addAccount(account2);

        // Perform transactions
        bank.performTransaction("123456", 200, "withdraw");
        bank.performTransaction("789012", 600, "withdraw");
        bank.performTransaction("123456", 500, "deposit");

        // Display account details
        bank.displayAccountDetails("123456");
        bank.displayAccountDetails("789012");
    }
}
```

