Video [Link](https://youtu.be/TAtrPoaJ7gc?si=oqv-OgcwKSocjO3U)
Topic No : 2
Next Topic [[Data Types]]

Download JDK Oracle [Link](https://www.oracle.com/java/technologies/downloads/)
Download IntelliJ IDEA Community Edition [Link](https://www.jetbrains.com/idea/download/?section=windows)

## Creating Main function

```Java
public class Main {
	public static void main(String[] args){
		System.out.println("Hello World!!");
	}
}
```

- ==The name of the file should be the name of the class== 
- In first line the ``public class Main`` the main should be replaced with the file name , first letter capitalized : Ex File name is Popup.java , The class should be ``public class Popup``
- Incase if you need the .class file of the source code file you need execute these commands in the terminal ``javac filename.java``
- You can run that new file created with .class extension using command ``java filename``

![[Pasted image 20231202132213.png]]

## Explaining of program

### 1st Line
##### 'public' word
It means that the class can be accessed from anywhere 

##### 'class' word
- It is a named group of properties and methods
- All functions inside the classes are methods

##### 'Main' word
- It is the name of the class (As the name of the file is also Class)

### 2nd Line
##### 'main' word 
- This main is in the second line , which is the entry point of the program

##### 'public' word
- As the main is the entry point , it makes sense that it should be available to the program

##### 'static' word
- The variable that are independent of the object , that are static , they should be said that they can be act individual without declaring of any objects. So , we mention it as static
- Simply , the static is to say that you need to run the main function in the second line without creating an object

##### 'void' word
- It mentions the return value of the function , as it return nothing it is void
- Incase it return a number you need to mention it as 'int'

##### 'String[]' word
- It is nothing but a collection of string data stored in a array



## Change location of the byte file

In terminal ``javac -d location_you_need_to_keep_file(../../ or . or ../) filename``






## Output in java

```Java
public class Main {  
    public static void main(String[] args) {  
        System.out.println("Hello world!");  
    }  
}
```

The output is ``Hello World!``

## Input in Java

```Java
import java.util.Scanner;  
  
public class Main {  
    public static void main(String[] args) {  
        Scanner input = new Scanner(System.in); // creating a new object named input 
    }  
}
```

``Scanner input = new Scanner(System.in); `` This create a new object using constructor

``system.in`` inside the brackets mention to get input from the user keyboard , it changes as per how and what will the input will be .

```Java
import java.util.Scanner;  
  
public class Main {  
    public static void main(String[] args) {  
        Scanner input = new Scanner(System.in);
        System.out.print(input.next());  
    }  
}
```

``input.next()`` As the input is a object of the scanner class , it contains all the property of scanner 
The next keyword get the word that you type in the terminal after the execution instance

``System.out.print(input.next());`` This line first get a input from the keyboard and print the same input in the terminal

```
Input : "Heyy How are you?"
Output : "Heyy"
```

Incase we used ``system.nextLine()``

```
Input : "Heyy How are you?"
Output : "Heyy How are you?"
```

