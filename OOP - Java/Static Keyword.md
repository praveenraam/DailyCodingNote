Topic No : 6
Previous Topic : [[Packages]]
Next Topic : [[Inner Classes]]
Content : static keyword

### what is static

If something is not only related to specific obj but it need to be in class, there you need static

When a member is declared static, it can be accessed before any of the object of the class is created with the name of the class. Simply static members are not dependent on the object.
##### Example Case : 
```Java
package com.Static;  
  
public class Main {  
    public static void main(String[] args) {  
        Human hmn1 = new Human(21,"praven",10000,false);  
        System.out.println(hmn1.population);  
        Human hmn2 = new Human(31,"Sanju",15000,true);  
        System.out.println(hmn2.population);  
    }  
}  
  
class Human {  
    int age;  
    String Name;  
    int salary;  
    boolean married;  
    static long population;  
    
    public Human(int age,String Name,int salary,boolean married){  
        this.age = age;  
        this.Name = Name;  
        this.salary = salary;  
        this.married = married;  
        Human.population++;  // Instead of this we use className for making the count increase to the class static variable not to the obj instance variable. Using this keyword also works but it is good to use className.
    }  
} 
// 1
// 2
```

In the above example, we need population to be independent of the obj and need to calculate the number, so we use static keyword in front of the variable name. 

This can be also used for methods also. The variable or methods created using the static can be used without creating the object.

```Java
package com.Static;  
  
public class Main {  
    public static void main(String[] args) {  
        System.out.println(Human.population); 
    }  
} 
// Output : 0
```

##### Internal working
![[Pasted image 20241217203910.png]]

### Non static members inside the static

Any non static member can't be used inside the static method

Example
```Java
public class Main {  
    public static void main(String[] args) {  
        greetingFunc(); // runs error free
        greeting();  // Gives error
    }  
    void greeting(){  
        System.out.println("Non-Static");  
    }  
    static void greetingFunc(){  
        System.out.println("Static");  
    }  
}
```

```Java
void greeting(){  
	System.out.println("Non-Static");  
}  
static void greetingFunc(){  
	greeting(); // This also gives error.
	System.out.println("Static");  
}  
```

### Static inside a non-static member

This is totally fine to have, this is not limit itself within the boundaries.

```Java
public class Main {  
    public static void main(String[] args) {  
        greetingFunc();  
    }  
    void greeting(){  
        System.out.println("Non-Static");  
    }  
    static void greetingFunc(){ 
	    greeting(); // This is error and the below lines are error free 
        Main obj = new Main();  
        obj.greeting();  // We create a obj to call the non-static method.
    }  
}
```
This is completely possible to do.

```Java
public class Main {  
    public static void main(String[] args) {  
        greetingFunc();  
    }  
    void greeting(){  
        System.out.println("Non-Static");  
    }  
    void fun(){  
        greeting(); // This is possible because, anyway you need an obj to run fun
    }  
    static void greetingFunc(){  
        Main obj = new Main();  
        obj.greeting();  
    }  
}
```
This is an example where a non static method is called an another non static method.

### "this" keyword inside the static methods

We can't use the "this" keyword on the static methods


```Java
class Human {  
    int age;  
    String Name;  
    int salary;  
    boolean married;  
    static long population;  
    
    static void message(){  
        System.out.println(this.age); // This gives error.
		System.out.println(Human.population); // This is correct
    }  
    public Human(int age,String Name,int salary,boolean married){  
        this.age = age;  
        this.Name = Name;  
        this.salary = salary;  
        this.married = married;  
        Human.population++;  
    }  
}
```

### Static block

In case, we need to initialize the value of a static variable, we use static block. This get executes when the class is loaded into the memory.

```Java
package com.Static;  
  
class StaticBlock{  
    static int a = 10;  
    static int b;  
    
    static {  
        b = a*2;  
        System.out.println(StaticBlock.b);  
    }  
    
    public static void main(String[] args) {  
        System.out.println(StaticBlock.b);  
        
        StaticBlock obj1 = new StaticBlock();  
        System.out.println(StaticBlock.b);  
        
        StaticBlock.b += 2;  
    }  
} 
// Output : 
// 20
// 20
// 22
```