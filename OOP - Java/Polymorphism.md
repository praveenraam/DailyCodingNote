Topic referred from [[Principles of OOP]]
Content : 

### What is polymorphism

Poly - Many
Morphism - way to represent

Now we create a superclass Shapes and subclass Triangle, Circle and Square.

Shapes.java
```Java]
public class Shapes {  
    public void Area(){  
        System.out.println("The area for shapes");  
    }   
}
```

Triangle.java
```Java
public class Triangle extends Shapes{  
    public void Area(){  
        System.out.println("The area is 0.5*h*b");  
    }  
}
```

Circle.java
```Java
public class Circle extends Shapes{  
    public void Area(){  
        System.out.println("The area is pie*r*r");  
    }  
}
```

Square.java
```Java 
public class Square extends Shapes{  
    public void Area(){  
        System.out.println("The area is l*l");  
    }  
}
```

Main.java
```Java
public class Main {  
    public static void main(String[] args) {  
        Shapes shape = new Shapes();  
        Circle circle = new Circle();  
        Square sqaure = new Square();  
        Triangle triangle = new Triangle();  
        
        shape.Area();     // The area for shapes  
        circle.Area();    // The area is pie*r*r
        sqaure.Area();    // The area is l*l
        triangle.Area();  // The area is 0.5*h*b
    }  
}
```
In this example, we call the same functions but it gave us output in different ways. Writing different constructors are also polymorphism.
In this we used hierarchical Inheritance type to create the subclasses.
### Types of polymorphism

##### Static / Compile time Polymorphism : 
This is achieved by method overloading.

What is method overloading?

It is when multiple methods with the same name exist with different parameters.

Ex : multiple constructors in class, we used box class for example.

The compile time polymorphism is named after java decides which method to run at the compile time. 

```Java
public class AdditionCalculator {

	public int sum(int a, int b,int c,int d){
		return a+b+c+d;
	}
	public int sum(int a,int b){
		return a+b;
	}
	public int sum(int a,int b,int c){
		return a+b+c;
	}
	public int sum(String a,int b){
		return Integer.parseInt(a)+b;
	}
	public int sum(int a,String b){
		return a+Integer.parseInt(b);
	}
	public double sum(double a,double b){
		return a+b;
	}
	
	public static void main(String[] args){
		AdditionCalculator calc = new AdditionCalculator();
		int val1 = calc.sum(1,2);
		int val2 = calc.sum(2,4,2);
		int val3 = calc.sum(2,3,4,5,1); // This will give error.
	}
}
```

##### Run time / Dynamic Polymorphism

Achieved by overriding.

The overriding is nothing but the same function with different body.
This overriding is mention with the annotation.

Shapes.java
```Java]
public class Shapes {  
    public void Area(){  
        System.out.println("The area for shapes");  
    }   
}
```
Triangle.java
```Java
public class Triangle extends Shapes{ 
	@Override // These are overriding the function of superclass.
    public void Area(){  
        System.out.println("The area is 0.5*h*b");  
    }  
}
```
Circle.java
```Java
public class Circle extends Shapes{  
	@Override // These are overriding the function of superclass.
    public void Area(){  
        System.out.println("The area is pie*r*r");  
    }  
}
```

Main.java
```Java
public class Main{
	public static void main(String[] args){
		Shape shape = new Shape();
		Shape circle = new Circle();
		Shape square = new Square();
		
		circle.Area(); // The output will be from the class Circle Area, because it is overriding from the parent class
	}
}
// Output : The area is pie*r*r
```

After overriding is done on a function, which Area to be called is depend on the object type, not the reference type. This is mentioned as ==**Upcasting**== 

##### How java decide which method to run in dynamic polymorphism

This is decided with dynamic programming dispatch.