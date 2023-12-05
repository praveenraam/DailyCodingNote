Video[Link](https://youtu.be/vvanI8NRlSI?si=dA0uq1TeTuABykAu)
Topic No : 8
Next Topic [[Scoping]]

The functions/Methods came into the programming to avoid the repetition of code multiple number of time the came code  (Not to Dry)

==Dry means Repetition==
![[First Program#Creating Main function]]
![[First Program#Explaining of program]]

### Sum of Two numbers using function 

```Java
import java.util.Scanner;  
  
public class Sum {  
    public static void main(String[] args) {  
        sum();  // Here this call the function (Function call)
    }  
    
    static void sum() {  
        Scanner InpGet = new Scanner(System.in); 
        
        int num1,num2,Sum;  
        
        System.out.print("Enter Number 1 : ");  
        num1 = InpGet.nextInt();  
        System.out.print("Enter Number 2 : ");  
        num2 = InpGet.nextInt();  
        
        Sum = num1 + num2;  
        System.out.println("The sum of the both number : "+Sum);  
    }  
}
```

## Return type

- If you are not returning any values , then you use void keyword like in the above code example
```Java
static void function_name(){
	//body
}
```
- If you are returning a integer value , then you use int keyword 
```Java
import java.util.Scanner;  
  
public class Sum {  
    public static void main(String[] args) {  
        sum();  // Here this call the function (Function call)
    }  
    
    static void sum() {  
        Scanner InpGet = new Scanner(System.in); 
        
        int num1,num2,Sum;  
        
        System.out.print("Enter Number 1 : ");  
        num1 = InpGet.nextInt();  
        System.out.print("Enter Number 2 : ");  
        num2 = InpGet.nextInt();  
        
        Sum = num1 + num2;  
        return Sum; 
    }  
}

```
- Similarly for other datatype we need to mention it

==In any function if compiler hits the return statement , the function ends==

```Java
static int func(){
	//Body
	return 900;
	//These code won't execute 
}
```

Example : String

```Java
public class Str {  
    public static void main(String[] args) {  
        String Word = func();  
        System.out.println(Word);  
    }  
  
    static String func(){  
        return "Hello World!!";  
    }  
}
```

## Parameters 

##### These are nothing but passing of values while calling a function as a input for performing the function

### Example : 

#### Integer Function
```Java
import java.util.Scanner;  
  
public class Sum {  
    public static void main(String[] args) {  
        System.out.println(sumInp(88,98));  
    }  
    static int sumInp(int a,int b){  
        int sumValue = a+b;  
        return sumValue;  
    }  
} //Out = 186
```

#### String Function 
```Java
import java.util.Scanner;  
  
public class Greeting {  
    public static void main(String[] args) {  
        Scanner Inp = new Scanner(System.in);  
        
        System.out.print("Enter Your name : ");  
        String Name = Inp.nextLine(); 
         
        System.out.println(MyGreet(Name));  
    }  
    static String MyGreet(String name){  
        return "Good morning " + name ;  
    }  
  
}// Out = Good morning Praveen
```

## Swapping through parameters

### Creating new object
```Java
public class Swap {  
    public static void main(String[] args) {  
        String name = "Praveen";  
        swapper(name);  
        System.out.println(name);  
        System.out.println(naam); // Error   
    }  
    static void swapper(String naam){  
        naam = "My name";  
    }  
} //Out = Praveen
```
This is because , when you change value of parameter variable it wont affect the real variable outside the function.

At first , it points they both points the same Reference object in the heap , once you change the variable value of parameter , the Parameter variable create a new reference object in the heap as shown in the below image

You cannot the print the 'naam' parameter variable outside of the function inside the main or other functions. That can be accessed inside the function only

![[Pasted image 20231205110658.png]]


### Modifying the object

```Java
import java.util.Arrays;  
  
public class Swap {  
    public static void main(String[] args) {  
        int[] arr = {1,3,5,78,9};  
        swapper(arr);  
        System.out.println(Arrays.toString(arr));  
}  
    static void swapper(int[] number1){  
        number1[0] = 22;  
    }  
} // Out = [22, 3, 5, 78, 9]
```
If you make a change to the object via this ref variable , same object will be changed

![[Pasted image 20231205112408.png]]

After this topic , Scoping are covered in Next FIle
## Variable Arguments (Var Args)

This is used to pass n number of parameter to the function
```Java
import java.util.Arrays;  
  
public class Scopings {  
    public static void main(String[] args) {  
        func("Hello","World!","Shirt","Car");  
    }  
    
    static void func(String ...words){ 
        System.out.println(Arrays.toString(words));  
    }  
} // [Hello, World!, Shirt, Car] 
```

- ``...`` is used to mention that it is a Variable Argument Func 
- In ``...words`` , words is the variable that store the parameters in an Array while we call the Func
- It also can be a empty ( It even works if you didn't pass arguments )
#### Intake of multiple datatype value

```Java
static void func(int a,int b,String ...words){ 
        System.out.println(Arrays.toString(words));  
}
```
This is also possible , but while calling the Func , parameters should be passed in the right order 
```Java
import java.util.Arrays;  
  
public class VarArgs {  
    public static void main(String[] args) {  
        func(1,2,"Hello","World!","Shirt","Car");  
    }  
}
```

Var Args should always come at the end 
Error Example : 
```Java
static void func(int a,String ...words,int b){ 
	System.out.println(Arrays.toString(words));  
}
```


## Method overloading

You can have two Func with same number but you have to differ it with parameters 

```Java
import java.util.Arrays;  
  
public class Scopings {  
    public static void main(String[] args) {  
        func(1);  
        func("Vanakam");  
        func(1,4);  
    }  
    static void func(int number){  
        System.out.println(number);  
    }  
    static void func(String Word){  
        System.out.println(Word);  
    }  
    static void func(int number1,int number2){  
        System.out.println(number1+number2);  
    }  
}
```
Two or more function have same name with different arguments are called as method overloading

During the compile time it decide which Func should be run based in the parameter

Example with Var Args
```Java
import java.util.Arrays;  
  
public class Scopings {  
    public static void main(String[] args) {  
        demo(5);  
        demo("Hello");  
        demo();  // This gives error because the compiler can't decide which func to run
    }  
    static void demo(int ...V){  
        System.out.println(Arrays.toString(V));  
    }  
    static void demo(String ...V){  
        System.out.println(Arrays.toString(V));  
    }  
}
```

## Problems

### Prime number 

```Java
import java.util.Scanner;  
  
public class PrimeNumber {  
    public static void main(String[] args) {  
        Scanner InpGet = new Scanner(System.in);  
        int Number = InpGet.nextInt();  
        
        System.out.println(isPrime(Number));  
    }  
    static boolean isPrime(int n){  
        if(n <= 1){  
            return false;  
        }  
        int divider = 2;  
        while(divider*divider <= n){  
            if(n%divider == 0){  
                return false;  
            }  
            divider++;  
        }  
        return true;  
    }  
}
```

### Armstrong number

##### Cube of numbers separate and adding them to get the same number 

```Java
import java.util.Scanner;  
  
public class Armstrong {  
    public static void main(String[] args){  
        Scanner InpGet = new Scanner(System.in);  
        int InpNumber = InpGet.nextInt();  
        System.out.println(isArmstrong(InpNumber));  
    }   
    
    static boolean isArmstrong(int Number){  
        int Value=0;  
        int InpValue = Number;  
        while(Number > 0){  
            int remainder = Number%10;  
            Value= (remainder*remainder*remainder)+Value;  
            Number = Number/10;  
        }  
        return Value == InpValue;  
    }  
}
```

