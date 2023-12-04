Video [Link](https://youtu.be/ldYLYRNaucM?si=axqBnojALyZDQvn5)
Topic No : 6
Next Topic : [[Switch and Nested Conc]]

## Conditions

```Java
// Syntax of IF - Else
if(booleanExpression){
	// Body
} else{
	// Body
}

// Syntax of multiple IF - Else 
if(booleanExpression){
	//Body
} else if(booleanExpression){
	// Body
} else if(booleanExpression){
	// Body
} else{
	// Body
}
```

You can also skip writing else in those syntax if required

## Loops 

#### For loop

```Java
// For loop syntax
for(initialize;condition;increment/decrement){
	"Body of the loop"
}
//Program to print 1 to 5
for(int i=1;i<=5;i++){
	System.out.println(i);
}
```
Use when you know how many number of times loop going to run

#### While loop

```Java
// While loop syntax
initialisation;

while(condition){
	// Body	
	increment;
}
```
Use when you don't know how many number of times loop going to run
#### Do while

```Java
// Do while syntax
initialisation;

do{
	// Body
	
}while(condition)
```
Here the body is executed once and then the condition is checked



## Solving Questions

#### Largest Number

```Java
import java.util.Scanner;  
  
public class Inputs {  
    public static void main(String[] args) {  
        Scanner InpGet = new Scanner(System.in);  
        int a = InpGet.nextInt();  
        int b = InpGet.nextInt();  
        int c = InpGet.nextInt();  
        
        int max = a;  
        if(b>max){  
            max=b;  
        }  
        if(c>max){  
            max=c;  
        }
        System.out.println("The largest Number is "+max);  
    }  
}
```

#### Fibonacci Series

My Code
```Java
import java.util.Scanner;  
  
public class Inputs {  
    public static void main(String[] args) {  
        Scanner inpGet = new Scanner(System.in);   
        
        System.out.print("Enter a limit number : ");  
        int Max = inpGet.nextInt();  
        
        int a=0,b=1,i=1;  
        do{  
            int Total = a+b;  
            a=b;  
            b=Total;  
            i++;  
        }while(i<=Max);  
        System.out.println(Total+"  ");  
    }  
}
```

a is the first number
b is the second number
i is for increment count

a is initially zero , b is initially 1
On running the b no is assigned to a , total is assigned to b

#### Counting Occurrence

Given a numbers , Find the specific number how many times repeated in the given number

```Java
import java.util.Scanner;  
  
public class Inputs {  
    public static void main(String[] args) {  
        Scanner inpGet = new Scanner(System.in);  
        
        System.out.print("Enter the Given No : ");  
        int GnNo = inpGet.nextInt();  // 522442
        System.out.print("Enter the number to find : ");  
        int Fno = inpGet.nextInt();  // 2
        int Count = 0;  
        while(GnNo>0){  
            int Remainder = GnNo % 10;  
            if(Remainder == Fno){  
                Count++;  
            }  
            GnNo = GnNo/10;  
        }  
        System.out.println(Count);  
    }  
}
// Out = 3
```

### Reverse Number

```Java
import java.util.Scanner;  
  
public class Inputs {  
    public static void main(String[] args) {  
        Scanner inpGet = new Scanner(System.in);  
        System.out.print("Enter the Number to Reverse : ");  
        int GnNo = inpGet.nextInt();  // 54777
        int OutNo = 0;  
        while(GnNo>0){  
            int Remainder = GnNo % 10;  
            OutNo = (OutNo + Remainder)*10;  // (OutNo*10)+Remainder;
            GnNo /= 10;  
        }  
        System.out.println(OutNo/10);   // System.out.println(OutNo);
    }  
} 
//Out = 77745
```

#### Calculator Program



