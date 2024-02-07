### Topics
- Looping statements
- Control flow statements
- Arrays
- String
### Task 1 : 
Employee Salary Calculator

Create a Java program that calculates the monthly salary for group of employees. Utilize looping statements, arrays and strings to achieve the following:

Allow the user to input the number of employees For each employee, prompt the user to enter their name, basic salary, and any allowances. Calculate the total monthly salary for each employee by adding the basic salary and allowances

Display the details of each employee, including their name, their salary, allowances, and total monthly salary

```Java
public static void main(String[] args) {    
    Scanner scanner = new Scanner(System.in);  
    System.out.print("Enter number of employees : ");  
    int n = scanner.nextInt();  
    SalaryCalculator(n);  
}

public static void SalaryCalculator(int n){  
    Scanner Input = new Scanner(System.in);  
  
    String[] name = new String[n];  
    double[] salary = new double[n];  
    double[] allowance = new double[n];  
  
    for(int i=0;i<n;i++){  
        System.out.println();  
        System.out.print(STR."Enter the name of the Employee \{i + 1} : ");  
        name[i] = Input.next();  
        System.out.print("Enter the salary : ");  
        salary[i] = Input.nextInt();  
        System.out.print("Enter the allowance : ");  
        allowance[i] = Input.nextInt();  
    }  
    for(int i=0;i<n;i++){  
        System.out.println();  
        System.out.println(STR."Employee - \{i + 1} details");  
        System.out.println(STR."Name : \{name[i]}");  
        System.out.println(STR."Salary : \{salary[i]}");  
        System.out.println(STR."Allowance : \{allowance[i]}");  
        System.out.println(STR."Totoal Salary : \{allowance[i]+salary[i]}");  
    }  
}
```

### Task 2

Gradebook System

Build a gradebook system in Java that allows a teacher to input and analyze students' grades. Implement the following functionalities:

Allow the user to input the number of students, For each student, prompt the user to enter their name and grades for three subjects (e.g., Math, English, social science, Tamil ), Store the student information in arrays and calculate the average grade for each student. Display the names, grades, and average grade for each student. Determine and display the highest average grade and the corresponding student

```Java
public static void gradeSheetSystem(int n){  
    Scanner Input = new Scanner(System.in);  
    String[] name = new String[n];  
    double[] math = new double[n];  
    double[] SocSci = new double[n];  
    double[] Eng = new double[n];  
    
    for(int i=0;i<n;i++){  
        System.out.println();  
        System.out.print("Enter the Student name : ");  
        name[i] = Input.next();  
        System.out.print("Maths Mark : ");  
        math[i] = Input.nextInt();  
        System.out.print("Social Mark : ");  
        SocSci[i] = Input.nextInt();  
        System.out.print("English Mark : ");  
        Eng[i] = Input.nextInt();  
    }  
    
    for(int i=0;i<n;i++){  
        System.out.println(STR."Name of the Student : \{name[i]}");  
        System.out.println(STR."Maths Mark : \{math[i]}");  
        System.out.println(STR."Social Mark : \{SocSci[i]}");  
        System.out.println(STR."English Mark : \{Eng[i]}");  
        System.out.println(STR."Average Mark : \{(math[i]+SocSci[i]+Eng[i])/3}");  
        System.out.println();  
    }   
}
```


