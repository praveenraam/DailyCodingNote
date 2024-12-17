Topic No :  2
Previous Topic : [[OOP - Java/Introduction|Introduction]]
Next Topic : [[Constructors]]
Video [Link](https://youtu.be/BSVKUk58K6U?si=ootRdgB11jU6AASE)
Content : new keyword


Incase we are having a class named student 
```Java
class Student{  
    int rollNo;  
    String Name;  
    float marks;   
}
```

#### Just Declaring
```Java
Student stdnt1;
```

This is just creating a reference variable created not pointing anything. This is just listed on the stack memory. It points null without initializing.

#### Creating a object
```Java
stdnt1 = new Student();
```

The "new" keyword dynamically allocates the memory which means it is allocating in the run time and returning the reference to it.

The Object created are stored in the heap memory.

![[Architecture#Dynamic Memory Allocation]]

#### Trying to print

```Java
public static void main(String[] args) {  
    Student student1 = new Student();    
	System.out.println(stdnt1); // FileName.ClassName@address(randomValue)
	System.out.println(stdnt1.rollNo); // 0
	System.out.println(stdnt1.Name); // null
	System.out.println(stdnt1.marks); // 0.0
}
```

Without initializing the instance variable, by default the values are null or 0 as per the datatype

#### Changing the value of instance variable 

```Java
stdnt1.rollNo = 12;
stdnt1.Name = "Praveen";
stdnt1.marks = 93.2;
```

If you try to print it now, the values will be printed.

#### Changing the value inside the class

```Java
package Introduction;  
  
public class Main {  
    public static void main(String[] args) {  
        Student stdnt1 = new Student();  
        System.out.println(stdnt1.marks); // 90.1
        System.out.println(stdnt1.rollNo); // 0  
    }  
}  
  
class Student{  
    int rollNo;  
    String Name;  
    float marks = 90.1;  
}
```


#### How value of the instance variable is accessed

![[Pasted image 20241216134834.png]]

- If you access the variable Kunal with it's instance variable, it first refer own object if there are any variable in the own object it returns, if not then it refers the class for the default value.

```Java
public static void main(String[] args) {  
    Student stdnt1 = new Student();  
    stdnt1.Name = "praveen"; stdnt1.rollNo = 10;  
    System.out.println(stdnt1.Name + " " + stdnt1.rollNo);  // These are found in stdnt1 obj
    
    Student stdnt2 = new Student();  
    System.out.println(stdnt2.Name + " " + stdnt2.rollNo);  // These are not found in stdnt2 obj, so it is refered in class for value
}
```

### Read after studying next topic : Memory allocation in "new"

```Java
Student copyStdnt1 = stdnt1;  
System.out.println(copyStdnt1.Name+" "+copyStdnt1.rollNo); // Praveen 10

copyStdnt1.name = "New praveen";
System.out.println(stdnt1.name); // New praveen
```

- The both reference variable copyStdnt1 and stdnt1 will be stored in the stack memory and the both will be pointing the same obj in the heap memory. 
- changing the value of instance variable using one reference variable will reflect when using the another.
- Multiple reference variables also can be initialized with the existing obj