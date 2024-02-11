[Video Link](https://youtu.be/nqB3qAtDLKU?si=5KQBTnZyyH-5O4vZ&t=5599)
Next Topic [[Advance concepts]]
Know Basics [[Advance concepts#Inheritance]]

### Single Inheritance

- A parent and a child class is Single Inheritance
```Java
class Father {  
    char gender = 'M';  
    void display(){  
        System.out.println(STR."Gender : \{gender}");  
    }  
}  
class Son extends Father{  
      
}  
public class DaySkill{  
    public static void main(String[] args) {  
        Son son = new Son();  
        son.display();  
    }  
} // output ::  Gender : M
```

### Multi-Level Inheritance

- Here even the parent class was extended from an another class
``` Java
class GrandFather {  
    char gender = 'M';  
    int age = 66;
    boolean isBloodLine = true;  
}  
  
class Father {  // All the characters are of grandfather is passed to Father
    int age = 45;  
}  
class Daughter extends Father{ // All the characters are of Father is passed to Daughter
    char gender = 'F';  
    int age = 24;  
}  
class GrandSon extends Daughter{ // All are passed from Daughter and few were changed
	isBloodLine = false;
    char gender = 'M';  
    int age = 3;  
}
```
- This is multi-level Inheritance

### Hierarchical Inheritance

- Single parent class and many child class
```Java
class Father{  
    char gender = 'M';  
    int age = 42;  
}  
class Son extends Father{  
    int age = 21;  
}  
class Daughter extends Father{  
    char gender = 'F';  
    int age = 22;  
}  
class Son2 extends Father{  
    int age = 19;  
}
```

### Hybrid Inheritance
- Combination of more than one type of above inheritance is Hybrid Inheritance
For Example : This is an example of Multi-level and Hierarchical inheritance
```Java
class Father{  
    char gender = 'M';  
    int age = 42;  
}  
class Son extends Father{  
    int age = 21;  
}  
class Daughter extends Father{  
    char gender = 'F';  
    int age = 22;  
}  
class GrandSon extends Son{  
    int age = 1;  
}
```

### Abstract Classes & methods
- This type of class can be declared using keyword ``abstract``
- While creating with the keyword , we can't define object for that class , only we can inherit using extends
```Java
abstract class Computer{  
    void turnOn(){  
        System.out.println("System Turns On");  
    }  
    abstract void turnOff();  
}  
class Hp extends Computer{  
    @Override  
    void turnOff() {  
        System.out.println("Hp System is Turning off");  
    }  
}  
class Dell extends Computer{  
    @Override  
    void turnOff() {  
        System.out.println("Dell System is Turning off");  
    }  
}  
class Main{  
    public static void main(String[] args) {  
        Hp SystemHp = new Hp();  
        Dell SystemDell  = new Dell();  
        
        SystemHp.turnOn();  // System Turns On
        SystemDell.turnOn();  // System Turns On
        SystemHp.turnOff();  // Hp System is Turning off
        SystemDell.turnOff();  // Dell System is Turning off
    }  
}
```
- There is only declaration part in the Parent class , we must define the method in child class
- We declared ``abstract void turnOff`` in the below code which mentions that the function must be over ride in the child class.
### Interface Multiple Inheritance

- Multiple Inheritance meant two parent and a child class
- This can't be done directly in java , can be done only using the Interface concepts

- The interface in Java is __a__ mechanism to achieve Abstraction .
- There can be only abstract methods in the Java interface, not the method body. 
- It is used to achieve abstraction and multiple inheritances in Java using Interface

```Java
interface Father{  // We use interface keyword instead 
    abstract void goTalk();  
}  
interface Mother{  
    abstract  void dontTalk();  
}  
class Son implements Father,Mother{  // extends changes to implement in interface 
    @Override  
    public void goTalk() {  
        System.out.println("Go talk to the girl");  
    }  
  
    @Override  
    public void dontTalk() {  
        System.out.println("Don't talk to the girl");  
    }  // Override must be done , else error occurs 
}
```
