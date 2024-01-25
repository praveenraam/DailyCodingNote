
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

### Problem
#### Summation
##### Parameterised way
```Java
static int paraSummation(int n,int sum){  
    if(n<1) return sum;  
    return Summation1(n-1,sum+n);  
}
```
##### Functional way
```Java
static int recursiveSummation(int n){  
    if(n==1 || n==0) return 1;  
    return n+(Summation(n-1));  
}
```

#### Factorial
```Java
static int ParaFactorial(int n,int total){  
    if(n==1 || n==0) return total;  
    return ParaFactorial(n-1,total*n);  
}  
static int RecursiveFactorial(int n){  
    if(n==1 || n==0) return n;  
    return n*RecursiveFactorial(n-1);  
}
```

#### Reverse an array
```Java
public class Solution {  
    public static void main(String[] args) {  
        int[] gnArray1 = {12,145,153,156,677};  
        int[] gnArray2 = {12,145,153,156,677};  
        int[] resArray = new int[gnArray1.length];  
        ReverseArray(gnArray1,resArray,0,gnArray1.length-1);  
        RevArray(gnArray1,0,gnArray1.length-1);  
        SinglePointer(gnArray2,0);  
        System.out.println("Reverse Array Output : "  + Arrays.toString(resArray) +  "\nRev Array Output : " + Arrays.toString(gnArray1) + "\nSingle Pointer Output : " + Arrays.toString(gnArray2));  
  
    }  
    static void ReverseArray(int[] gnArray,int[] resArray,int counter,int place){  
        if(place < 0) return;  
        resArray[counter] = gnArray[place];  
        ReverseArray(gnArray,resArray,counter+1,place-1);  
    }  
    static void RevArray(int[] gnArray,int P1,int P2){  
        if(P1>=P2) return;  
        int temp = gnArray[P1];  
        gnArray[P1] = gnArray[P2];  
        gnArray[P2] = temp;  
        RevArray(gnArray,P1+1,P2-1);  
    }  
    static void SinglePointer(int[] gnArray,int counter){  
        if(gnArray.length/2 <= counter) return;  
        int temp = gnArray[counter];  
        gnArray[counter] = gnArray[gnArray.length-counter-1];  
        gnArray[gnArray.length-counter-1] = temp;  
        SinglePointer(gnArray,counter+1);  
    }  
}
```
**Output** :
Reverse Array Output : [677, 156, 153, 145, 12]
Rev Array Output : [677, 156, 153, 145, 12]
Single Pointer Output : [677, 156, 153, 145, 12]



#### Palindrome
```Java
static boolean isPalindrome(String Inp,int counter){  
     int length = Inp.length();  // Not necessary
     if(counter >= length/2) return true;  
     if(Inp.charAt(counter) != Inp.charAt(length-counter-1)) return false;  
     else return isPalindrome(Inp, counter + 1);  
 }
```
#### 
