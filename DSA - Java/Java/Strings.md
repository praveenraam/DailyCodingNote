Topic No : 16
Video [Link](https://youtu.be/zL1DPZ0Ovlo?si=sOwEVPVMmb5nbPET)
Next Topic :[[]]

- It is a collection of characters (Char)
	 Ex : Your name is a string (A collection of character)
- String should be in the Double quotes 
-  String is similar to Num array that stores Characters (Can't perform all the methods that are applicable for the Num array)
- It is a most used Java class (Everything starts with Capital Letter is a class)

### Internal working of String 

- Every time we create a String Variable , we create a object of the String class

##### Concepts
###### String Pool : 
- Every String variable we create , that is stored in a separate pool
- If you create two different variable for a same value , both the variables points to the same object 
- Example : ![[Pasted image 20240112193204.png]]
###### Immutability : 
- Strings are immutable in java 
- Incase if you try to change the value of a variable it may reflect in the another one also
- This is majorly implement for security reasons
- So , to avoid that we can't change the value once it is defined
###### Creating New Object

```Java
class Solutions{
  public static void main(String[] args){
	  String A = "Praveen";
	  System.out.println(A);
	  A = "Praveen Raam";
  }
}
```

- This will create a new object , and the object the variable points will be changed to the new object ![[Pasted image 20240112194050.png]]
### String Creation : ' new ' keyword
- You can create different objects by same value in java by telling manually (explicit)
- Example
```Java
class Solutions{
   public static void main(String[] args){
	   String A = new String("Praveen");
	   String B = new String("Praveen");
   }
}
```
- The created values are not stored in the pool(this is also inside the heap) , but stored inside the heap outside the pool
###### Comparison of Strings 
- In this case , the ' == ' comparison function gives us false if we try to compare A and B --> Refer : [[Input Program#' == ']]
```Java
class Solutions{
   public static void main(String[] args){
	   String A = new String("Praveen");
	   String B = new String("Praveen");
	   System.out.println(A==B); // returns false
   }
}
```

- We have to use the Dot Equals method to compare variables
```Java
class Solutions{
   public static void main(String[] args){
	   String A = new String("Praveen");
	   String B = new String("Praveen");
	   System.out.println(A.equals(B)); // returns true
   }
}
```

### Methods

**While using the Methods of String , the original string won't be changed , it will create a new object once the method is over , the space in loop is cleared. 

You can only save it to an another variable for the next reference**
###### charAt : 
- This methods or function return the character at the specific position
- This is similar to `` numArray.[position] ``
- Syntax :  `` ExampleString.charAt[position] ``
- Example : 
```Java
class Solution {
	public static void main(String[] args){
		String A = "HelloWorld!!"
		System.out.println(A.charAt(4)) // Output : o
		System.out.println(A.charAt(0)) // Output : H
	}
}
```
###### Concatenation (+)
- Add the two different strings to one string
```Java
class Solution{
   public static void main(String[] args){
	   System.out.println('a'+'b'); // 195 as ASCII Value
	   System.out.println("a"+"b"); // ab - concatenation
	   System.out.println('a'+3); // 100
	   System.out.println((char)('a'+3)); // d
	   System.out.println("a"+1); // a1 
	   // Before printing a1 it will be as "a"+"1" , converted to String
	   System.out.println('a'+""+1) // a1
   }
}
```
Here the plus (+) operator is overloaded to add the two strings.

`` System.out.println("a"+"b") ``
- Here the object "a" and "b" is created once the print function is finished , it is erased from the heap
###### toCharArray :
- This function converts your string to character array and you can use that
``System.out.println(Arrays.toString(Variable.toCharArray()));
###### Length :
- Returns the length of the String `` Variable.length() ``
###### toLowerCase :
- Returns the String in lower case ``Variable.toLowerCase();``
###### toUpperCase :
- Returns the String in Upper case ``Variable.toUpperCase();``
###### indexOf :
- Returns the index of the Specific character ``Variable.indexOf('char');
###### lastIndexOf :
- Returns the last index of the specific character `` Variable.lastIndexOf('char');``
###### strips :
- Return the string without the space characters (White Spaces) ``Variables.strips();``

### String Builder

![[String Problem#Print all the Alphabets]]

###### Better Solution :
To avoid this we use String builder , which only make the changes to the existing String object

**Declaring a StringBuilder :**
`` StringBuilder VariableName = new StringBuilder(); ``

**Adding to  StringBuilder Variables :**
``VariableName.append('ValueInChar' or "ValueInString")``
