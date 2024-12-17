Topic No : 4
Previous Topic : [[Constructors]]
Next Topic : [[Packages]]
Content : Garbage collections, Finalize keyword


### Whenever the obj is not pointed by any reference variable, it is moved to the garbage collections

It is then deleted by the Java itself, it can't be controlled by us.
but we can control some actions before garbage is collecting this obj, that is done by ==**"finalize"**==
This function can't be called manually. An exception will be thrown

```Java
// Syntax
// Whenever the obj is about to move to the garbage collection finalize is called
@Override  
protected void finalize() throws Throwable {  
    System.out.println("The object is about to get destroyed");  
}
```

### Example 

```Java
package Introduction;  
  
public class Main {  
    public static void main(String[] args) {  
        Student stdnt1 = new Student(10,"Praveen",90.1f);  
        System.out.println(stdnt1.Name + " " + stdnt1.rollNo);  
        
        Student stdnt2 = new Student();   
        
        stdnt2 = new Student();  
    }  
}  
  
class Student {  
    int rollNo;  
    String Name;  
    float marks;  
    
    void changeName(String newName){  
        this.Name = newName;  
    }  
    void changeRollNo(int rollNo){  
        this.rollNo = rollNo;  
    }  
    
    Student (int rollNo,String Name,float marks) {  
        this.rollNo = rollNo;  
        this.Name = Name;  
        this.marks = marks;  
    }  
    Student(){  
        this (0,"Not set",0.0f);  
    }  
    Student(Student stdnt){  
        this.Name = stdnt.Name;  
        this.rollNo = stdnt.rollNo;  
        this.marks = stdnt.marks;  
    }  
    
    // Whenever the obj is about to move to the garbage collection finalize is called  
    @Override  
    protected void finalize() throws Throwable {  
        System.out.println("The object is about to get destroyed");  
    }  
} // The output is Praveen 10
```
#### For one obj not pointing the garbage collector won't start it's process, when there are multiple obj like this, it will start it's work.

```Java
for(int i=0;i<1000000;i++){  
    stdnt2 = new Student();  
}
```

If you include this snippet in the code, the garbage collector will start it's work to get object and the finalize method will be also called.