Topic No : 8
Previous Topic : [[Inner Classes]]
Next Topic : [[Principles of OOP]]
Content : 

This is a class where you can only create a single obj.

You can achieve this using by using private in front of the constructor, and create an obj inside the class and return it through a static function.


```Java
package com.Singleton;  
  
import java.security.Signature;  
  
public class Singleton {  
    private Singleton(){  
    
    }  
    String name;  
    public static Singleton obj;  
    
    public static Singleton getInstance(String name){  
        if(obj == null) obj = new Singleton();  
        obj.name = name;  
        return obj;  
    }  // We created a single obj and return the same one with changing the name for n number of time it is called.
}
```

In the above code, you can see that we made constructor private which made it impossible to access from other files, so we can't create obj 

And we created a method that return a "Singleton" obj for allowing them to create a single obj

In main.java
```Java
package com.Singleton;  
  
public class Main {  
    public static void main(String[] args){  
        Singleton obj1 = Singleton.getInstance("Rahul");  
        Singleton obj2 = Singleton.getInstance("Kumar");  
        
        // Both are reference variable are pointing the same object.
        System.out.println(obj1.name);  // Kumar
        System.out.println(obj2.name);  // Kumar
    }  
}
```
When we see the output of the code, the both obj name is "Kumar" because the obj1 and obj2 are two reference variable pointing the same obj, that mean we are allowed for only one obj.

