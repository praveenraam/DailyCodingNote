### Topics 
- Data types

### Task 1 
```java
public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    
    System.out.println("What is your first number?");
    float num1 = input.nextFloat();
    System.out.println("What is your second number?");
    float num2= input.nextFloat();
    System.out.println("What operation would you like to perform?");
    String Operation = input.next();
    switch (Operation) {
        case "addition":
            System.out.println(num1 + num2);
            break;
        case "subtraction":
            System.out.println(num1 - num2);
            break;
        case "multiplication":
            System.out.println(num1 * num2);
            break;
        case "division":
            if (num1 == 0 || num2 == 0) ;
        {
            System.out.println("You can not divide by or with a zero!");
        }
        
        System.out.println(num1 / num2);
        break;
        default:
            System.out.println("Invalid Operation!");
    }
}
```
### Task 2
- Incomplete
