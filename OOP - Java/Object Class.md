Topic No : 11
Previous Topic : [[Access Modifiers]]
Next Topic : 

### What is object class

Object class is the parent of all the class you create, it is indirectly inherited to all the classes.
This is top most class of the hierarchy
This is on the "lang" package, which is also imported internally.

### Methods in object

##### hashcode
Hash the value and return it
##### equals
Compare whether the values are same or not 
##### instanceOf  Operator
This is used to get whether the a obj is subclass's obj of parent class

```Java
public class Main {  
    public static void main(String[] args) {  
        BoxWeight obj1 = new BoxWeight(1,2,3,4);  
        System.out.print(obj1 instanceof Box);  // True
    }  
}
```

##### getClass
This is used to get the class of the object 
```Java
package com.Inheritance;  
  
public class Main {  
    public static void main(String[] args) {  
        BoxWeight obj1 = new BoxWeight(1,2,3,4);  
        System.out.print(obj1.getClass());  
    }  
} // Output : class com.Inheritance.BoxWeight
```
Use can access multiple methods after keeping (.) on getClass() method to access more information. ``obj1.getClass().methodName()``

This can't be override because it is declared final.
##### clone 

##### toString
