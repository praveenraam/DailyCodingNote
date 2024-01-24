
[Video Link](https://youtu.be/yVdKa8dnKiE?si=D-C0hvUrrg7YCRHk)

When the Function call itself , it is called Recursion 
### Infinite Recursion 

```Java
class Myclass{
	public static void Print(int n){
		System.out.println(n);
		Print(n+1);
	}
}
```

This is function tend to run infinite no of times , but once the size of the stack is over it throws an error and exits the program
	i.e : Every time the function is called , it stored inside the memory and call the function again ( without quitting stack and without clearing Space ) before the function itself ending.

### Base condition

This is nothing but the condition written to avoid the infinite condition

```Java
class Myclass(){
	public static void print(int from,int till){  
	    if(from > till) return; // Base cafe 
	    System.out.println(from);
	    print(from+1,till);
	}
}
```

##### Printing name for N times
```Java
public class Solution {
    public static void myNamePrint(String Name , int Times){  
        System.out.println(Name);  
        if(Times == 1) return;  
        else myNamePrint(Name,Times-1);  
    }  
}
```
Time Complexity - O(N) 
Space Complexity - O(N)

##### Print 1 to N
```Java
class Myclass{
	static void OneToN(int Counter,int End){  
	    if(Counter > End) return;  
	    System.out.println(Counter);  
	    OneToN(Counter+1,End);  
	}
}
```

##### Print N to 1
```Java
class MyClass{
	static void NtoOne(int Start){
		if(Start == 0) return;
		System.out.println(Start);
		NtoOne(Start-1);
	}
}
```


### Using Backtracking

##### Print 1 to N 
```Java
class MyClass{
	static void OneToN(int till){  
	    if(till == 0) return;  
	    OneToN(till-1);  
	    System.out.println(till);  
	}
}
```

##### Print N to 1
```Java
class myClass{
	static void NtoOne(int counter,int till){  
	    if(counter > till ) return;  
	    NtoOne(counter+1,till);  
	    System.out.println(counter);  
	}
}
```