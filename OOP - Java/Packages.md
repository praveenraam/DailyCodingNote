Topic No : 5
Previous Topic : [[Garbage collections]]
Next Topic : [[Static Keyword]]
Content : Java Packages, import
Video [Link](https://youtu.be/_Ya6CN13t8k?si=rxRsG5RzxBapipOt)
### What is packages

Packages are containers for the classes, it is just a folder that allows you to create comportments for the classes.

It simply allow us to store multiple files with the same name in different packages ( folders ). Those same name files are created for different use cases.

#### Mentioning in first line

```Java
Package folderName.folderName.folderName;
```

it is mandatory to mention the package at which the file is at

###### Example : 
```Java
package com.Introduction; // Like this, it mention that the file is located at Introduction folder which is at com folder.
```

### import statement

it is a keyword used to import functions or something from the other file it is located in different package or file.
If the files are inside the same package, we no need to import

```java
import file.file.functionName;
```

Main.java
```Java
package com.Introduction;  
  
public class Main {  
    public static void main(String[] args) { 
    }  
    public static void importExample(){  
        System.out.println("Hello from Main.java");  
    }  
}
```

Wrapper.java
```Java
package com.Introduction;  
import static com.Introduction.Main.importExample;  // This is how we import
public class Wrapper {  
    public static void main(String[] args) {  
        importExample();  
    }  
} // OUTPUT : Hello from Main.java
```

Only the functions created to be public can be done like this.

### Common use cases

We can see multiple imports in a java file

```Java
import java.util.ArrayList // For importing and using ArrayList
```

This means nothing but the Array List class is inside the util folder which is inside the java folder.

### In-Build Packages :


**Java folder contains all these**, 
###### "lang" packages : 
- Very Important language specific stuffs are present in this.
- This contains the primitive data types, operations everything
- This no need to be imported separately because it is done automatically or internally.
###### "io" package :
- It contains input output stuffs
- When we try to read or write files, optimize io for competitive programming these were used.
###### "util" package :
- It contains the data structures stuffs and collection frameworks inside it.
###### "applet" package :
- This is development focused one.
###### "awt" package :
- This is for creating GUI for window applications
###### "net" package : 
- This is for networking kind of works.