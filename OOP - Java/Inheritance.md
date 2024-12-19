Topic reference From [[Principles of OOP]]

### Passing the properties of parent to the child is called Inheritance

Inheritance is a mechanism in OOP where a **child class (subclass)** inherits the **properties (attributes) and behaviors (methods)** of a **parent class (superclass)** and the children also have it own attributes and methods.

The child's own prop can't be accessed by the parent class.

### Private modifier
The properties and the methods that are declared as private can't be access by the child.
Any member declared private, that can be only used within that file.
### Extends keyword

This keyword is used to make a class to child class by inheriting from some other class

#### Syntax
```Java
class ChildClassName extends ParentClassName{
	
}
```
#### Example
```Java
package com.Inheritance;  
  
public class BaseExample {  
    String name;  
}  
class Child extends BaseExample{
	public int number; // Own property
    Child(String name,int number){  
        this.name = name; // Inherited Property
        this.number = number;
    }  
}
```
It take the instance variable "name" from the Base_Example class, Base_Example class do not have access to the "number" instance variable.

### Example of Inheritance

Box.java : parent class
```Java
package com.Inheritance;  
  
public class Box {  
    double l;  
    double h;  
    double w;  
    private double PrivateExample;  
    public Box (){  
        this.l = -1;  
        this.h = -1;  
        this.w = -1;  
    }  
    // For cube  
    public Box(double size){  
        this.l = size;  
        this.h = size;  
        this.w = size;  
    }  
    public Box(double l,double h, double w){  
        this.l = l;  
        this.h = h;  
        this.w = w;  
    }
    public void PrivateExampleChange(double newValue){  
	    PrivateExample = newValue;  
	}
}
```

BoxWeight.java : child class
```Java
package com.Inheritance;  
  
public class BoxWeight extends Box{  
    double weight;  
    public BoxWeight(){  
        this.w = -1; // we can also change it from here also. If we need  
        this.weight = -1;  
    }  
    public BoxWeight(double l,double h,double w,double weight){  
        super(l,h,w); // This calls the constructor of the parent class,and initializing the parent class props  
        this.weight = weight;  
    }  
    public BoxWeight(double size,double weight){  
        super(size); // This call cube's contructor of the parent class  
        this.weight = weight;  
    }  
    public void AccessProps(){  
        System.out.print(this.l+" "+this.h+" "+this.w+" "); // These are accessible from parent  
        System.out.println(this.PrivateExample); // This is Not because it is private  
        PrivateExampleChange(29.01); // This is possible to do, because we call a certain function and change the value using the function inside that Box.java file 
    }  
}
```

### Creating Objects

Main.java
```Java
package com.Inheritance;  
  
public class Main {  
    public static void main(String[] args) {  
        Box box1 = new Box();  
        Box box2 = new Box(1,2,4);  
        Box box3 = new Box(2);  
        System.out.println(box1.l + " " + box1.h + " " + box1.w); // -1 -1 -1
        System.out.println(box2.l + " " + box2.h + " " + box2.w); // 1 2 4
        System.out.println(box3.l + " " + box3.h + " " + box3.w); // 2 2 2
  
        BoxWeight box4 = new BoxWeight();
        BoxWeight box5 = new BoxWeight(1,2,4,5);  
        BoxWeight box6 = new BoxWeight(5,2,1,5);  
  
        System.out.println(box4.l + " " + box4.h + " " + box4.w + " " + box4.weight); // -1 -1 -1 -1
        System.out.println(box5.l + " " + box5.h + " " + box5.w + " " + box4.weight); // 1 2 3 
        System.out.println(box6.l + " " + box6.h + " " + box6.w + " " + box4.weight); // 5 2 1 5  
        
        Box box7 = new BoxWeight(1,2,3,5);  
        System.out.println(box7.l + " " + box7.h + " " + box7.w);  // 1 2 3
        System.out.println(box7.weight);  // This is error, can't access

		BoxWeight box8 = new Box(1,2,4); // This is not possible, Gives error.
    }  
}
```
##### Box 7
The "box7" reference variable actually created with Box as class and calling Box Weight's constructor. So the reference variable will only have access to the class that is created with, in this case it is Box class and it only have access limited to Box class.

There the weight variable will be also initialized but it can't access.

**The reference variable is of type Box in stack is pointing the object created is of Box Weight in heap. Super class can be referred to the sub class is what we applied here**
![[Pasted image 20241219122629.png]]

##### Box 8
The vice-verse of the Box7 is Box8, that is not possible to do, as the parent are not aware of the props of the child