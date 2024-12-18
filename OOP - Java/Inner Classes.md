Topic No : 7
Previous Topic : [[Static Keyword]]
Next Topic : 
Content : 

The inner classes is nothing but the class that is created inside the another class.

```Java
package com.Static;  
  
public class InnerClasses {  
    class TestClass1{  
    
    }  
  
    static class TestClass2{  
      
    }  
}
```

In the above example you can see that we used static keyword before a class, this is possible only with the inner class.

```Java
package com.Static;  
  
public class InnerClasses {  
    class TestClass1{   }  // This is correct
    static class TestClass2{    }  // This is correct
}
static class ErrorClass{  } // This gives error
```

### Creating of objects

```Java
package com.Static;  
  
public class InnerClasses {  
    class NonStaticClass{  
        String name;  
        NonStaticClass(String name){  
            this.name = name;  
        }  
    }  
    static class StaticClass{  
        String name;  
        StaticClass(String name){  
            this.name = name;  
        }  
    }  
    
    public static void main(String[] args) {  
        StaticClass obj1 = new StaticClass("Obj1");  // This is error free because it does not depend on InnerClasses class obj.  
        NonStaticClass obj2 = new NonStaticClass("Obj2");  // This is error because it is depend on the obj of InnerClasses.
    }  
}
```
