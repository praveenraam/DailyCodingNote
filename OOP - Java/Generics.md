Topic No : 14
Previous Topic : [[Interfaces]]
Next Topic : [[OOP - Java/Exception Handling|Exception Handling]]

### What is generics
Generics means **parameterized types**. The idea is to allow a type (like `Integer`, `String`, etc., or user-defined types) to be a parameter to methods, classes, and interfaces.

### Syntax

```Java
BaseType <Type> obj = new BaseType <Type>();
```

```Java
class Test<T> {
    // An object of type T is declared
    T obj;
    Test(T obj) { 
	    this.obj = obj; 
	} // constructor
    public T getObject() {
	    return this.obj; 
	}
}
```
