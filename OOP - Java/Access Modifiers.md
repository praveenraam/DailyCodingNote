Topic No : 10
Previous Topic : [[Principles of OOP]]
Next Topic : [[Object Class]]
Video [Link](https://youtu.be/W145DXs8fFg?si=agqTUR-6dTkGcBv6)
Content : private, public, protected, default

### What are access modifiers

The access modifiers are nothing but the control of the data member for the security reason where and all it can be accessible in the project file.
### Rules of modifiers

![[Pasted image 20241222091414.png]]

### When to use which modifier

- **Private** : It is used for most sensitive information to hide.
- **Default** : It is used when you no need access outside the package
- **Protected** : Only allowed to the subclass of same and different packages, not even the own class can access it
- **Public** : When you need access everywhere

### Important about protected

- This basically allows only the subclass to access the data member even the own class can't access it with it's obj. 
- Sub class's subclass can also access, only the data member declared class can't access.

A.java
```Java
public class A{
	protected num;
	String name;
	A(){
		System.out.println("Obj A is created");
	}
}
```

B.java
```Java
public class B extends A{
	int variableB;
	B(){
		System.out.println("Obj B is created");
	}
}
```

C.java
```Java
public class C extends C{
	int variableC;
	C(){
		System.out.println("Obj C is created");
	}
}
```

Main.java
```Java
public class Main{
	public static void main(String[] args){
		A a = new A();
		B b = new B();
		int numA = a.num; // This gives error
		int numB = b.num; // This is possible.
		C c = new C();
		int numC = c.num; // This is possible.
	}
}
```

