Video [Link](https://youtu.be/vvanI8NRlSI?si=dA0uq1TeTuABykAu&t=2801)
Topic No : 9
Next Topic [[Arrays]]


## Method/Function scoping

Across the Methods or Function the variable can't be accessed 
#### Ex:
```Java
public class Scopings {  
    public static void main(String[] args) {  
        int a =20;  
        System.out.println(VariableFromMethod);  
    }  
  
    static void VariableChecker(){  
        int VariableFromMethod = 20;  
        System.out.println(a);  
    }  
}
```
Error Message : 
	  java: cannot find symbol
	  symbol:   variable VariableFromMethod

==This means Variable created inside a function can be accessed inside only that specific function==

#### From the previous topic we covered mentioned below , the changes you make inside the function will reflect inside that specific function

![[Function (Methods)#Creating new object]]

## Block Scope

Block are curly braces ( { } )

- Inside a main function you have a block , If you declare and init a variable inside the function you can modify it inside the block but cannot init again inside the block
- You can reassign the value multiple number of times
- You can initialize a new variable inside the block that is not init outside of the block and assign a value to it
- But , the variable created inside the block can't be accessed outside of the block
- Variable initialized inside can be again init in the outside of the block 

==Any things init inside can't used outside , anything from outside can used inside==

#### All the rules are applicable for the conditional and loops
#### Example
```Java
public class Scopings {  
    public static void main(String[] args) {  
        int a = 20;  
        int b = 100 ;  
        
        {  
            int a = 33;//Error: Can't init a value already initiated outside the block  
            b = 55 ; // Can reassign the value  
            String C = "Hello";  
            System.out.println(b + "" + a); // Can use it inside the Block  
        }  // After the block end , we can't track the Variable 'C'
        System.out.println(C); // Error : Can't access that are init inside the block  
    }  
}
```

## Shadowing

```Java
public class Scopings {  
    static int A = 100 ;  
    public static void main(String[] args) {  
        System.out.println(A); // 100  
        int A; //Shadowing : This is shadows the variable at line 2   
		System.out.println(A); // Error : A is not initialized  
        A = 20;  
        System.out.println(A); // 20  
        Func(); // 100  
    }   
    static void Func(){  
        System.out.println(A); // Access A at line 2  
    }  
}
```


After Shadowing concepts , all other topics are taken notes in the Function method