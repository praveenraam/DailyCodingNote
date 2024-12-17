Topic No : 6
Previous Topic : [[Packages]]
Next Topic : 
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