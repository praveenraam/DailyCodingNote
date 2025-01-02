
### Question 1

```Java
public class HelloWorld {
    public static void main(String[] args) {
        HelloWorld obj = new HelloWorld(n);
    }
    static int a = 10;
    static int n;
    int b = 5;
    int c;
    public HelloWorld(int m) {
        System.out.println(a + " " + b + " " + c + " " + n + " " + m);
    }
    
    }
    // Instance Block
    {
        b = 30;
        n = 20;
    }
    // Static Block
    static
    {
        a = 60;
    }

} 
```
```Output
60 30 0 20 0
```
### Key Concepts:
1. **Static Variables**:
    - `a` and `n` are static variables. Static variables are shared by all instances of the class and are initialized only once when the class is loaded.
2. **Instance Variables**:
    - `b` and `c` are instance variables. They are specific to each instance of the class and are initialized every time an object is created.
3. **Static Block**:
    - A static block is executed when the class is loaded into memory. In this case, `a` is set to 60 in the static block.
4. **Instance Block**:
    - The instance block is executed every time an object is created, before the constructor. In this case, it sets `b` to 30 and `n` to 20.
5. **Constructor**:
    - The constructor takes an argument `m` (which is `n`), and prints the values of `a`, `b`, `c`, `n`, and `m`. `m` output is zero as the n is 0 when it is passed into the constructor, after that only instance block is executed and them n became `20`.