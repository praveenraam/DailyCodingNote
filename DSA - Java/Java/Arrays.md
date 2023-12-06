Video [Link](https://youtu.be/n60Dn0UsbEk?si=GogqE5HHSXcz5Qk7)
Topic No : 10
Next Topic [[2D-Arrays]]

## Syntax

```Java
Data_type[] variable_name = new data_type[size];
//or Directly
Data_type[] Variable_name = {data,data,data,....};
```

#### Example : Storing 5 Roll Numbers

```Java
int Rollnumbers = new int[5];
// Or directly
int Rollnumbers = {23,24,25,26,27};
```

- The datatype at first represent the type of data going to be stored in the Array
- We can't include an another datatype inside that array other than the mentioned one

## New keyword

It means used to create an object


## How arrays works

```Java
int[] ros; // Declaration of array. Ros are defined in the stack
ros = new int[5]; // Init of Array. now the object is created in the memory Heap
```

#### Dynamic Memory Allocation

This is nothing but the memory allocations are done in the Run Time of the program
![[Pasted image 20231205204424.png]]

#### Internal representation of Array

For array , Memory allocation should be done continuously

- As we know that objects are created in Heap memory
- But , in Heap object are not continuous
- Dynamic Memory allocation
Hence , coming to the conclusion Arrays in Java may not be store continuously (Depends on JVM)

## Index of Array

##### ==The position of the array starts from Index of 0 and continuously goes on==
That mean the first element can be get with index position of 0 and second element with 1 index position.

Example:
![[Pasted image 20231206090032.png]]

- Once you declared an Array and not init it , default it contains 0 in the all the positions
- In case of String , it contains 'null' inside of the not init positions

## Null 

- Null is a special literal , you can cast it to any particular non primitives data type but can't declare a null type Variable
```Java
String str = null;
int num = null; //Error : can't assign to the primitives
```

![[Pasted image 20231206092731.png]]

## Array input

```Java
int[] arr = new int[5];
int[0] = 23;
int[1] = 24;
int[2] = 25;
int[3] = 26;
int[4] = 28;
```

## Array input using Loop

```Java
Scanner Inp = new Scanner(System.in);
int[] arr = new int[5];
//Input
for(int i=0;i<arr.length;i++){ //arr.length return size of the element
	arr[i] = Inp.nextInt();
} 
// Inp = 1 2 3 4 5

//Output
for(int i=0;i<arr.length;i++){
	System.out.print(" "+arr[i]);
}
// Out = 1  2  3  4  5
```

## Foreach loop

```Java
// Java
for(data_type Ref_variable : arr_name){
	// Body
}

for(int num : arr){
	System.out.print(" "+ num + " "); // num represent the element of the Array
}
// Out = 1  2  3  4  5
```

==If you try to print array position more than the size gives us error : Out of bound ==

## toString Method

``` Java
System.out.println(Arrays.toString(array_name));
//Out = [2,4,5,6,6];
```
Here the toString method converts the array to the String format and prints it out 


## Storing of Objects in Heap

- Inside the Stack there will be a reference variable pointing the Array inside the Heap memory
- The Elements inside the array are also reference variable pointing an objects inside the Heap memory
- This is how objects are stored inside Heap (Non Primitive Values)
- 
![[Pasted image 20231206102540.png]]

## Passing Arrays inside the Functions

Changing of Array's value inside the Func reflects the Main Func

##### Example :

```Java
import java.util.Scanner;  
import java.util.Arrays;  
  
public class Arr {  
    public static void main(String[] args) {  
        int[] Arrs = new int[3];  
        Change(Arrs);  
        System.out.println(Arrays.toString(Arrs));  
    }  
    static void Change(int[] Nums){  
        Nums[0] = 12;  
    }  
} // Out = [12,0,0]
```

![[Pasted image 20231206104109.png]]
This is known as mutable Behaviour

