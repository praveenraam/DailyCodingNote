Topic No : 12
Previous Topic : [[Object Class]]
Next Topic : [[Interfaces]]

### What is abstract class : 

If we need a parent class where we need it show what to do, rather than how to do.
If we need a parent class methods must be override in sub class, then use abstract class.
It gives generalized class that followed by other class.

### Syntax :

``public abstract class ClassName`` -> for class
``abstract void methodName`` -> for methods

Parent.java
```Java
package com.AbstractClass;  
public abstract class Parent {  
	int age;
	Parent(){
		this.age = age;
	}
    abstract void careen(String name);  
    abstract void patner(String name,int age); 
}
```

Son.java
```Java
package com.AbstractClass;  
public class Son extends Parent{  
	Son(int age){
		super(age);
	}
	
    // either Son also a abstract or We must override the abstract function in the subclass  
    @Override  
    void careen(String name) {  
		System.out.println("Override : I'm "+name);
    }  
    @Override  
    void patner(String name, int age) {  
        System.out.println("Override : Her name is "+name+" and her age is "+age);  
    }  
}
```

Daughter.java
```Java
package com.AbstractClass;  
public class Daughter extends Parent{  
	Daughter(int age){
		super(age);
	}
	
    @Override  
    void careen(String name) {  
		System.out.println("Override : I'm "+name);
    }  
    @Override  
    void patner(String name,int age){  
        System.out.println("Override : His name is "+name+" and his age is"+age);  
    }  
}
```
We can see in the above example that we are making the children to override the parent class.

**You can also use constructor and super keyword as normal as other classes.**

### Creating obj of abstract class

##### Error Example
Main.java 
```java
package com.AbstractClass;  

public class Main {  
    public static void main(String[] args) {  
        Parent father = new Parent(85);  // Creating a normal obj like other will definitly give you error
    }  
}
```

##### Correct Example 
Main.java
```Java
package com.AbstractClass;  
  
public class Main {  
    public static void main(String[] args) {  
        Parent father = new Parent(48) {  
            @Override  
            void careen(String name) {  
            }  
            @Override  
            void patner(String name, int age) {  
            }  
        };  
    }  // Only creating obj like this is possible, as if we call any methods it would give error, so we need to override.
}
```

### Static and normal methods in abstract class
Parent.java
```Java
package com.AbstractClass;
public abstract class Parent {
	int age;
	Parent(){
		this.age = age;
	}
	static void Printer(){
		System.out.println("Static Method");
	}
	void normalMethod(){
		System.out.println("Normal Method");
	}
    abstract void careen(String name);
    abstract void patner(String name,int age);
}
```

Main.java
```Java
package com.AbstractClass;   
public class Main {  
    public static void main(String[] args) {  
        Parent.Printer();  
        Son son = new Son(22);
        sonl.normalMethod();
    }
}
```

### Static and final keyword in variable

Everything works fine like we learnt in the past.