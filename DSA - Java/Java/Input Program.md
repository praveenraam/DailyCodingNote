Video [Link](https://youtu.be/TAtrPoaJ7gc?si=XPlzWbbj9sRuJbX-&t=3308)
Topic No : 4
Next Topic : [[Type conversion and casting]]

#### Int Input Program

```Java
import java.util.Scanner;  
  
public class Inputs {  
    public static void main(String[] args) {  
        Scanner inputs = new Scanner(System.in);  
        System.out.println("Please , Enter your Roll Number : ");  
        int rollNo = inputs.nextInt();  
        System.out.println("Your Roll Number is "+rollNo);  
    }  
}
```

#### String Input Program

```Java
import java.util.Scanner;  
  
public class Inputs {  
    public static void main(String[] args) {  
        Scanner inputs = new Scanner(System.in);  
        System.out.print("Enter Some Sentence : ");  
        String Words = inputs.nextLine();  
        System.out.println(Words);  
    }  
}
```

Similar for all other Data Types

#### Sum of Two Numbers

```Java
import java.util.Scanner;

public class TwoSum{
	public static void main(String[] args){
		Scanner inputs = new Scanner(System.in);
		System.out.println("Enter Two Numbers");
		float Num1 = inputs.nextfloat();
		float Num2 = inputs.nextfloat();
		System.out.println(Num1+Num2)
	}
}
// Inp = 30 40
// Out = 70.0
```

As the input is given in the Integer Format , but the output came is float. This is because of type casting inside the JVM

#### Comparisons
- There are two ways to compare
###### Double Equals to ' == '
- Incase we use double equals to method , It checks whether both the variables points to the same Value or Object 
- Incase no , it return false 
- Example ![[Pasted image 20240112194729.png]]
###### Dot Equals to Method
`` variable1.equals(variable2) ``
- This is the syntax to compare both the Variables by the Value
- Now both the cases will be true from the last topic![[Pasted image 20240112194729.png]]
