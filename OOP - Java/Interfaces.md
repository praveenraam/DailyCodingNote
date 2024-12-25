Topic No : 13
Previous Topic : [[Abstract Class]]
Next Topic : [[Generics]]

### What is interface
An interface is a blueprint for a class. It defines a set of methods that a class must implement if it wants to be considered a type of that interface

### Why is interface
If we try to implement a multiple inheritance, we can't actually do it in java. To resolve the problem we got the Interface as solution.

### Syntax

``public interface InterfaceName``

We use a keyword `implements` as like `extends` for interfaces
``public class className implements interface1,interface2,interface3``

### Methods in Interfaces

We can't write a body of the method in Interfaces. we can only declare it. 

Engine.java
```java
public interface Engine{
	void run(); // You can't declare a body
	void start();
	void stop();
}
```

### Variable in Interfaces

We can have a variable, but it is default a static and final ones

Engine.java
```Java
public interface Engine{
	static final int PRICE1 = 20000; 
	int PRICE2 = 21000; // Both are similar internally.
}
```

### Example

![[Pasted image 20241224100522.png]]

We are writing code for this situation.

Engine.java
```Java
package com.Interfaces;  
  
public interface Engine {  
    int PRICE = 210000;  
    void run(); // same method is added in Brake also  
    void start();  
    void stop();  
}
```

Brake.java
```Java
package com.Interfaces;  
  
public interface Brake {  
    void apply();  
    void remove(); 
    void run(); // Car class will decide what to do with this method.
}
```

Car.java
```Java
package com.Interfaces;  
  
public class Car implements Engine,Brake{  
    @Override  
    public void apply() {  
        System.out.println("We are applying brakes");  
    }  
    @Override  
    public void remove() {  
        System.out.println("We stopped applying brakes");  
    }  
    @Override  
    public void run() {  
        System.out.println("The car is running");  
    }  
    @Override  
    public void start() {  
        System.out.println("The car has started");  
    }  
    @Override  
    public void stop() {  
        System.out.println("The car has stopped");  
    }  
}
```

Main.java
```Java
package com.Interfaces;  
  
public class Main {  
    public static void main(String[] args) {  
        Car car1 = new Car();  
        car1.start();  
        car1.run();  
        car1.apply();  
        car1.stop();  
        car1.remove();  
    }  
}
```
```Output
The car has started
The car is running
We are applying brakes
The car has stopped
We stopped applying brakes
```

Writing code would actually make things more difficult and complex, so we create a separate class for all interfaces and combining them in an another class.

### Example in proper case

##### Engine related Files
Engine.java
```Java
package com.Interfaces;   
public interface Engine {  
    void run();  
    void stop();  
    void start();  
}
```

EngineD.java
```Java
package com.Interfaces;   
public class EngineD implements Engine{  
    @Override  
    public void run() {  
        System.out.println("Diesel vehicle is running");  
    }  
    @Override  
    public void stop() {  
        System.out.println("Diesel vehicle is running");  
    }  
    @Override  
    public void start() {  
        System.out.println("Diesel vehicle is running");  
    }  
}
```

EngineI.java
```Java
package com.Interfaces;  
public class EngineI implements Engine {  
    @Override  
    public void run() {  
        System.out.println("Petrol vehicle is running");  
    }  
    @Override  
    public void stop() {  
        System.out.println("Petrol vehicle is stopped");  
    }  
    @Override  
    public void start() {  
        System.out.println("Petrol vehicle is started");  
    }  
}
```

EngineEv.java
```Java
package com.Interfaces;  
public class EngineEv implements Engine{  
    @Override  
    public void run() {  
        System.out.println("EV vehicle is running");  
    }   
    @Override  
    public void stop() {  
        System.out.println("EV vehicle is stopped");  
    }  
    @Override  
    public void start() {  
        System.out.println("EV vechicle is started");  
    }  
}
```

##### Media player Files
MediaPlayer.java
```Java
package com.Interfaces;  
public interface MediaPlayer {  
    void start();  
    void stop();  
    void exit();  
}
```

AppPlayer.java
```Java
package com.Interfaces;  
public class AppPlayer implements MediaPlayer{  
    @Override  
    public void start() {  
        System.out.println("App Player Music is playing");  
    }  
    @Override  
    public void stop() {  
        System.out.println("App player is stopped music");  
    }   
    @Override  
    public void exit() {  
        System.out.println("App play was exited");  
    }  
}
```

CD_Player.java
```Java
package com.Interfaces;  
public class CD_Player implements MediaPlayer{  
    @Override  
    public void start() {  
        System.out.println("CD Music is playing");  
    } 
    @Override  
    public void stop() {  
        System.out.println("CD Music has playing");  
    } 
    @Override  
    public void exit() {  
        System.out.println("CD Music was exited");  
    }  
}
```

##### Creating a Car
Car.java
```Java
package com.Interfaces;  
  
public class Car {  
    private Engine engine;  
    private MediaPlayer mediaPlayer;  
    // Constructor
    Car(Engine engine,MediaPlayer mediaPlayer){  
        this.engine = engine;  
        this.mediaPlayer = mediaPlayer;  
    }  
    
    public Engine getEngine(){  
        return engine;  
    }  
    public MediaPlayer getMediaPlayer(){  
        return mediaPlayer;  
    }  
    
    void stopEngine(){  
        engine.stop();  
    }  
    void runEngine(){  
        engine.run();  
    }  
    void startEngine(){  
        engine.start();  
    }  
    void playMedia(){  
        mediaPlayer.start();  
    }  
    void stopMedia(){  
        mediaPlayer.stop();  
    }  
    void exitMedia(){  
        mediaPlayer.exit();  
    }   
}
```

##### Main class
Main.java
```Java
package com.Interfaces;  
public class Main {  
    public static void main(String[] args) {  
        Car OldCar = new Car(new EngineD(),new CD_Player());  
        Car EffCar = new Car(new EngineI(),new AppPlayer());  
        Car EvCar = new Car(new EngineEv(),new AppPlayer());  
         
        OldCar.startEngine();  
        EffCar.startEngine();  
        EvCar.startEngine();  
    }  
}
```
```Output
Diesel vehicle is running
Petrol vehicle is started
EV vechicle is started
```


### Extends in Interfaces

A.java
```Java
public interface A{
	void greet();
}
```

B.java
```Java
public interface B extends A{
	void Welcome();
}
```

Main.java
```Java
public class Main implements B{
	@override
	void greet(){
		
	}
	@override
	void Welcome(){
		
	}
}
```
We have override both the methods

### `default` in Interfaces

The default keyword is used to declare a method like in a class and subclasses using it. but as class implementing interfaces should not carry that method in same name.

This motives to eliminate code repetition. Necessary if Same method body going to repeat in all class implementing interface.

A.java
```Java
public interface A{
	default void greet(){
		System.out.println("A Greet");
	};
	void Hello();
}
```

B.java
```Java
public interface A{
	default void greet(){
		System.out.println("B Greet");
	}; // Having this method in B gives error.
	void Welcome();
}
```

Main.java
```Java
public class Main implements A,B{ //  Error will be there because both have greet.
	@override
	void Welcome(){
	}
	@override 
	void Hello(){
	}
}
```
We shouldn't have same named method on interfaces that class implements. 
- If you **==override that same named method==** error can be rectified

### Nested Interfaces

Creating a `interface` inside a class is called nested interface.

A.java
```
package com.Interfaces.NestedInterface;  
  
public class A {  
    public interface Demo{  
        boolean isOdd(int num);  
    }  
}  
class B implements A.Demo{  
    @Override  
    public boolean isOdd(int num) {  
        return (num & 1) == 1;  
    }  
}
```

Main.java
```Java
package com.Interfaces.NestedInterface;  
  
public class Main {  
    public static void main(String[] args) {  
        B obj = new B();  
        System.out.println(obj.isOdd(21));  
        System.out.println(obj.isOdd(22));  
    }  
}
```
```Output
true
false
```
