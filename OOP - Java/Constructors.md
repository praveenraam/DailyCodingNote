Topic No : 3
Previous topic : [[new Keyword]]
Next topic : [[Garbage collections]]
Content : constructors, this keyword, final keyword

#### Constructor is a special function, this defines what happens when object is created

### By Default constructor

- A special function that runs when we create a object and allocates some variables
- If you need to change the it for your own purposes, you can do it.


![[new Keyword#Changing the value of instance variable]]

We are just focusing on the code.

If you have more variables there will be code repetition to avoid it we can use constructor function to pass arguments to pass those values and initialize it

##### We will be using "this" keyword

```Java
package Introduction;  
  
public class Main {  
    public static void main(String[] args) {  
        Student stdnt1 = new Student(10,"Praveen",90.1f);  
        System.out.println(stdnt1.Name + " " + stdnt1.rollNo);  // 10
         
        Student stdnt2 = new Student(12,"Selva",91.2f);
        System.out.println(stdnt2.Name + " " + stdnt2.rollNo);  // 12
    }  
}  
  
class Student{  
    int rollNo;  
    String Name;  
    float marks;  
    
    Student (int rollNo,String Name,float marks) {  
        this.rollNo = rollNo;  
        this.Name = Name;  
        this.marks = marks;  
    }  
}
```

On the process, the "this" is replaced by the reference variable name.
this refers to what obj you are referring to.

### Constructor Overloading

```Java
package Introduction;  
  
public class Main {  
    public static void main(String[] args) {  
        Student stdnt1 = new Student(10,"Praveen",90.1f);  
        System.out.println(stdnt1.Name + " " + stdnt1.rollNo);  
  
        Student stdnt2 = new Student();  
        System.out.println(stdnt2.Name + " " + stdnt2.rollNo);  
    }  
}  
  
class Student {  
    int rollNo;  
    String Name;  
    float marks;  
    Student (int rollNo,String Name,float marks) {  
        this.rollNo = rollNo;  
        this.Name = Name;  
        this.marks = marks;  
    }  
    Student(){  
        this.rollNo = 0;  
        this.Name = "Not set";  
        this.marks = 0.0f;  
    }  
}
// Output : 
// Praveen 10
// Not set 0
```

Creating function with already existing name with different parameter is called method overloading

-  If parameters are passed, it will call the method with parameters, if there is no parameters that specific parameter will be called.

```Java
Student(Student stdnt){  
    this.Name = stdnt.Name;  
    this.rollNo = stdnt.rollNo;  
    this.marks = stdnt.marks;  
}
```

This is also a constructor that takes another obj as input parameter. 

```Java
Student stdnt3 = new Student(stdnt1);  
System.out.println(stdnt3.Name);
```


### Constructor calling from another constructor

```Java
Student(){  
	this.rollNo = 0;  
	this.Name = "Not set";  
	this.marks = 0.0f;  
}  
// This is replaced by this
Student(){  
    this (0,"Not set",0.0f);  
}
// Both are same
```

Passing the parameters correctly will be calling the desired constructor

### Final keyword

The variable declared with final keyword can't be altered

```Java
// Syntax
final datatype VARIABLENAME = VALUE;
```

It is mandatory to use all Capitalize for the variable name for knowing it, it is declared with final keyword.

```Java
final int VALUE = 2;
VALUE = 3; // This gives error.
```

When you declare a variable, it must be initialized. 

### Final for Primitive vs Non Primitive

For Primitive data types you can reassign the value 

For non primitive data types, you can't change the reference point but you can change the value

```Java
class Output{
	public static void main(String args[]){
		final Student stdnt1 = new Student(10,"Praveen",93.1);
		stdnt1.name = "PraveenRaam"; // this is possible
		stdnt1 = new Student(11,"selva",91.1); // This is not possible
	}
}
```
You can't change the reference variable pointing obj, but can change the value of objects
