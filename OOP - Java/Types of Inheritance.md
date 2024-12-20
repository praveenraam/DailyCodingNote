Previous Topic : [[Inheritance]]
Content : Single Inheritance, Multi level inheritance, multiple Inheritance, Hybrid Inheritance.

### Single Inheritance

The example we saw in the last in the Box Example is a type of Single Inheritance, where there are only parent and child character, not more than that.
![[Pasted image 20241220101403.png]]

### Multi Level Inheritance 

In the single inheritance, if we add an another grandchild, then that is called multi level inheritance.

Box.java : Grand Parent
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
    public Box(Box old){  
        this.w = old.w;  
        this.h = old.h;  
        this.l = old.l;  
    }  
    public void PrivateExampleChange(double newValue){  
        PrivateExample = newValue;  
    }  
}
```

BoxWeight.java : Parent
```Java
package com.Inheritance;  
  
public class BoxWeight extends Box{  
    double weight;  
    public BoxWeight(){  
        this.w = -1; // we can also change it from here also.  
        this.weight = -1;  
    }  
    public BoxWeight(double l,double h,double w,double weight){  
        super(l,h,w); // This calls the constructor of the parent class, initializing the parent class props  
        this.weight = weight;  
    }  
    public BoxWeight(double size,double weight){  
        super(size); // This call cube's constructor of the parent class  
        this.weight = weight;  
    }
}
```

BoxPrice.java : Child
```Java
package com.Inheritance;  
  
public class BoxPrice extends BoxWeight{  
    double cost;  
      
    public BoxPrice(){  
        this.cost = -1;  
    }  
    public BoxPrice(double size,double weight,double cost){  
        super(size,weight);  
        this.cost = cost;  
    }  
    public BoxPrice(double cost){  
        super();  
        this.cost = cost;  
    }       
}
```

Main.java
```Java
package com.Inheritance;  
  
public class Main {  
    public static void main(String[] args) {  
        BoxPrice obj1 = new BoxPrice(10);  
        BoxPrice obj2 = new BoxPrice(1,10,50);  
    }  
}
```

- The obj1 calls, Box Price's constructor, in that the super keyword call the Box Weight constructor, and the super keyword in that would call the Box constructor as per the arguments
- Similarly for the obj2, the calling of constructor and super is similar.


### Hierarchical Inheritance

If you create more than one child class for a single superclass, then it is Hierarchical Inheritance.

Box.java 
```Java
class Box {
	String name;
	public Box(String name){
		this.name = name;
	}
}
```

BoxWeight.java
```Java
class BoxWeight {
	double weight;
	public BoxWeight(String name,double weight){
		super(name);
		this.weight = weight;
	} 
}
```

BoxColor.java
```Java
class BoxColor {
	String color;
	public BoxColor(String name,String color){
		super(name);
		this.color = color;
	}
}
```

BoxSpace.java
```Java
class BoxSpace {
	double space;
	public BoxSpace(String name,double space){
		super(name);
		this.space = space;
	}
}
```
##### Figure rep :
![[Pasted image 20241220110645.png]]
### Multiple Inheritance

Java doesn't support multiple Inheritance due to it's properties.

![[Pasted image 20241220105239.png]]

If a variable named "A" is in both the base class, If we try to access from the Derived, there will a confusion in deciding which base class's "A" should be picked. To avoid this java doesn't support it.
![[Pasted image 20241220105404.png]]

To Implement this concept we use **Interfaces** concepts.

### Hybrid Inheritance
When there is combination of single and multiple inheritance, then  it is Hybrid.
As we know java don't support Multiple inheritance, so this is also not supported in java
![[Pasted image 20241220112110.png]]
