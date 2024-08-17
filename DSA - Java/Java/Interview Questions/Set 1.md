
##### Question 1 : 
\What are the differences between `final`, `finally`, and `finalize` in Java?

- **`final`** : when you declare a variable and use the keyword before the datatype , that data type can't be modified anymore. This can be used for all variable, methods and class
- **`finally`** : This is a keyword used in try catch block
- **`finalize`** : This is an method that is called by the garbage collector during deletion of the object, this can be overrides for our own use

##### Question 2 :
Explain the concept of type casting in Java. What is the difference between implicit and explicit casting?

- Implicit : This is automatically do the type casting, this is done when small is converted to large data type
- Explicit : This is opposite, this is done manually, this is done when large datatype is converted to small data type

```Java
int i = 100;
long l = i; // Implicit Casting
double d = 10.5;
int j = (int) d; // Explicit Casting

```

##### Question 3 : 
What is a `static` block in Java, and when is it executed?

- This is a block of code that runs after the class is loaded before even the main function, this meant that , function can be run without the object.

```Java
public class StaticBlockExample {
    static int x;
    
    static {
        x = 10; // Static block initializing the static variable
        System.out.println("Static block executed.");
    }
    
    public static void main(String[] args) {
        System.out.println("Value of x: " + x);
    }
}
```

```Output
Static block executed.
Value of x: 10
```

##### Question 4 :
What are the different types of loops in Java? Provide an example of each.

- For Loop 
- While Loop
- Do while
- For each (Enhanced)

##### Question 5 :
How does the `switch` statement work in Java? Can it be used with strings?

- Yes, String can be used in string, From java 7 this has been implemented

##### Question 6 :
Can we declare a variable using var keyword

- Yes, This keyword was introduced in java 10.
- This is local variable that compiler automatically determine type of variable been used

```Java
var message = "Hello, World!"; // The type is inferred as String
var number = 42;               // The type is inferred as int
var list = new ArrayList<String>(); // The type is inferred as ArrayList<String>

System.out.println(message); // Output: Hello, World!
System.out.println(number);  // Output: 42
System.out.println(list);    // Output: []
```

- Var is used instead of constructor or datatype or methods, can't be used with interfaces, method of return type and class
- you must initialize it

##### Question 7 :
What is the `StringBuilder` class, and how does it differ from `String`? Why is it considered more efficient in certain situations?

- The StringBuilder is mutable unlike the string, it has multiple functionalities like append, insertion and deletion at a certain index.
- The String is immutable that it create a new string object every time you modify it

**String Builder is more efficient in the case of using in loops as it reduces the memory and improves performance**

##### Question 8 :
What is the difference between `==` and `equals()` in Java?

- `==` compare the memory reference of the objects, for primitive data types check the value
- `.equals()` This compare the content of the object, by default it is same as == but some classes like string overrides it to act to compare content

##### Question 9 :
How does Java handle memory management? Explain the concept of garbage collection.

- **Memory Management** : Java handles memory management automatically through an automatic memory management system known as the Garbage Collector (GC). Java objects are allocated in heap.
- **Garbage Collection** : The process by which the Java Virtual Machine (JVM) identifies and discards objects that are no longer in use, freeing up memory. The GC periodically checks for objects that are not referenced by any active part of the program and reclaims their memory.

```Java
public class GarbageCollectionExample {
    public static void main(String[] args) {
        GarbageCollectionExample obj = new GarbageCollectionExample();
        obj = null; // Object is now eligible for garbage collection
        System.gc();
    }
}

```

**``System.gc()`` is used to suggest the JVM to run the garbage collector**

##### Question 10 :
What are the main differences between `ArrayList` and `LinkedList`? When would you use one over the other?
###### Array List : 
- It is a resizable array
- Access time is 0(1), so it is very fast
- But the insertion and delete take up to O(n), as it needed to rearrange the value by index
- Best case is to use when you need to access the values quick and don't needed to insert, delete value in between

###### LinkedList 
- It is a follower of double linked list
- Access time is 0(n) in worst case, it iterate from first to last
- but the insertion and deletion is very fast
- Best case is to use when you frequently use to insert and delete the value and no need fast random access