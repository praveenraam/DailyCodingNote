Topic No : 15
Previous Topic : [[Generics]]
Next Topics : 

### What is Exception

An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions. These exceptions can occur for various reasons, such as invalid user input, file not found, or division by zero.

### Hierarchy of Exception from object class
![[Pasted image 20241225113143.png]]

### Throwable
- Throwable is nothing but the super class of exceptions and error.
### Types of Exceptions

There are two types of Exceptions
- **Checked** : Checked exceptions are the exceptions that are checked at compile-time.
	Ex : SQL Exception, Class Not Found Exception, 
- **Unchecked** : Unchecked exceptions, also known as runtime exceptions.
	Ex : Null Pointer Exception, Array Index Out Of Bounds Exceptions, Arithmetic Exception 

##### Keywords involved
- ``try``
- ``catch``
- ``finally``
- ``throws``
- ``throw``
### Syntax

```Java
try{
	// Trying something that may give exception.
}
catch(Specific_Exception e){
	// If any exception rises, this block of code will run.
}
catch(Exception e){
	// You can write multiple catch blocks, even 14 for every exception to make them throw a specific messages for them separately.
	// This is optional.
}
final{
	// This will get execute no matter what happens. 
	// This is optional.
}
```

This is used to give an Exception on our own.
```Java
void methodName() throws ExceptionName{
	throw ExceptionName("Message");
}
```
### Example

Main.java
```Java
package com.ExceptionHandling;  
  
public class Main {  
    public static void main(String[] args) {  
        int a = 10;  
        int b = 0;  
        try {  
            System.out.println(a / b);  // Arithmetic Exception
        }  
        catch (ArithmeticException e){  
            System.out.println(e.getMessage());  
        }    
        catch{
	        System.out.println("Not a arithmetic Exception\n"+e.getMessage())
        }
        finally {  
            System.out.println("Ending the code");  
        }
    }  
}
```
```Output
/ by zero
Ending the code
```

```Java
package com.ExceptionHandling;  
  
public class Main {  
    public static void main(String[] args) {  
        int a = 10;  
        int b = 0;  
        try {  
            System.out.println(a / b);  
        }  
        catch (ArtihmeticException e){  
            System.out.println(e.getMessage());  
        }
        catch{
	        System.out.println("Not a arithmetic Exception\n"+e.getMessage())
        }
        finally {  
            System.out.println("Ending the code");  
        }  
    }  
    int divide(int a,int b) throws ArithmeticException{  
        if(b == 0) throw  new ArithmeticException("Dividing by zero is not allowed");  
        return a/b;  
    }  
}
```
```Output
/ by zero
Ending the code
```

We use ``throws`` near function name saying ==this may throw Exception==
We use ``throw`` to give the Exception
### Inbuilt Exceptions

- **ArithmeticException:** It is thrown when an exceptional condition has occurred in an arithmetic operation.
- **ArrayIndexOutOfBoundsException:** It is thrown to indicate that an array has been accessed with an illegal index. The index is either negative or greater than or equal to the size of the array.
- **ClassNotFoundException:** This Exception is raised when we try to access a class whose definition is not found
- **FileNotFoundException:** This Exception is raised when a file is not accessible or does not open.
- **IOException:** It is thrown when an input-output operation failed or interrupted
- **InterruptedException:** It is thrown when a thread is waiting, sleeping, or doing some processing, and it is interrupted.
- **NoSuchFieldException:** It is thrown when a class does not contain the field (or variable) specified
- **NoSuchMethodException:** It is thrown when accessing a method that is not found.
- **NullPointerException:** This exception is raised when referring to the members of a null object. Null represents nothing
- **NumberFormatException:** This exception is raised when a method could not convert a string into a numeric format.
- **RuntimeException:** This represents an exception that occurs during runtime.
- **StringIndexOutOfBoundsException:** It is thrown by String class methods to indicate that an index is either negative or greater than the size of the string
- **IllegalArgumentException :** This exception will throw the error or error statement when the method receives an argument which is not accurately fit to the given relation or condition. It comes under the unchecked exception. 
- **IllegalStateException :** This exception will throw an error or error message when the method is not accessed for the particular operation in the application. It comes under the unchecked exception.

### Creating Custom Exceptions

MyException.java
```Java
package com.ExceptionHandling;  
  
public class MyException extends Exception{  
    public MyException(String message){  
        super(message);  
    }  
}
```

Main.java
```Java
package com.ExceptionHandling;  
public class Main {  
    public static void main(String[] args) {  
        int a = 10;  
        int b = 0;  
        String Message = "CodeRed";  
        try {  
            if(Message.equals("CodeRed")){  
                throw new MyException("My message says CodeRed");  
            }  
        }  
        catch (MyException e){  
            System.out.println(e.getMessage());  
        }  
        catch (Exception e){  
            System.out.println();  
        }  
        finally {  
            System.out.println("Ending the code");  
        }  
    }
}
```
```Output
My message says CodeRed
Ending the code
```