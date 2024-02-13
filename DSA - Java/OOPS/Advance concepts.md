[Video Link](https://youtu.be/nqB3qAtDLKU?si=8pv6ItayjOumeaJU&t=3947)
Next Topic [[Exception handling]]
### Encapsulation
- _Binding (or wrapping) code and data together into a single unit are known as encapsulation_. 
- For example, a capsule, it is wrapped with different medicines.
### Abstraction
- Hiding the unnecessary process and information is called as the abstraction
- For example, You no need to know what happens behind the process when you press the accelerator in a car , you only need to know that car moves while pressing accelerator
### Inheritance
- Inheritance is getting of information from the parent class to a sub class
- A sub class is an extended version of the parent class , that is modified as per that class requirement
- This can be implemented with extends keyword
- Only sub class have the content of the parent class , not parent class have the information of the sub class
- This parent class also be called as Super class
```Java
class Animal {  
    int NoOfLegs = 4;  
    String FoodEaten = "Non-Veg";  
    String LivePlace = "Wild";  
}  
class Dog extends Animal{  
    boolean canBark = true;  
}  
class DaySkill{  
    public static void main(String[] args) {  
        Animal animal = new Animal();  
        Dog dog = new Dog();  
        
        System.out.println(dog.NoOfLegs);  
        System.out.println(dog.FoodEaten);  
    }  
}
```
```Output 
4
Non-Veg
```

##### Method over riding 
- This is changing the value from the parent in the sub class is called as the method over riding , this is applicable for the both field and methods

``` Java
class Animal {  
    int NoOfLegs = 4;  
    String FoodEaten = "Non-Veg";  
    String LivePlace = "Wild";  
  
    void Displayer(){  
        System.out.println("This is an Animal");  
    }  
  
}  
class Dog extends Animal{  
    boolean canBark = true;  
    String LivePlace = "Domestic";  
    @Override  
    void Displayer(){  
        System.out.println("This is a dog");  
    }  
}  
class DaySkill{  
    public static void main(String[] args) {  
        Animal animal = new Animal();  
        Dog dog = new Dog();  
  
        System.out.println(dog.LivePlace);  
        System.out.println(animal.LivePlace);  
        dog.Displayer();  
    }  
}
```
```Output
Domestic
Wild
This is a dog
```

### Polymorphism
- Poly mean small ,  morphism mean many
- It is an object-oriented approach that allows the developer to assign and perform several actions using a single function
- The given example also follows method overloading
- Simply methods have many forms
```Java
class Sample{  
    void display(){  
        System.out.println("Hello World!!");  
    }  
    void display(String Word) {  
        System.out.println(STR."Hello \{Word}");  
    }  
}  
public class DaySkill{  
    public static void main(String[] args) {  
        Sample Object = new Sample();  
        Object.display();  
        Object.display("User");  
    }  
}
```
```Output
Hello World!!
Hello User
```

### Static keyword
##### Using on Methods
- Static keyword is used to access or run a methods without creating an object or using an object
- Using this we can save the memory of creating an object , then running a program
- Why ``public static void main(String[] args){}`` ?
We avoid wasting memory on creating object for the main method , we called directly
```Java
class SampleClass{  
    static void display(){  // used static keyword
        System.out.println("Called without Objects");  
    }  
    void Display2(){  // Without static keyword
        System.out.println("Called only using Objects");  
    }  
}  
class Main{  
    public static void main(String[] args) {  
        SampleClass.display();  // Called without Objects
          
        SampleClass Object = new SampleClass();  
        Object.Display2();  // Called only using Objects
        Object.display // -> give us error as it is static method
    }  
}
```
##### Using on fields or variables
- These also follows the same rule as like for Methods 
- Can be accessed without creating object

- Using the static keyword for variable , while extending for other class 
- Not another variable is created for the child class , it uses the same variable 
- If you modify for the child class , it will be reflected for the parent class also.
- Simply , using static on variable will become common to all the classes
For example
```Java
class Father{  
    static char gender = 'M';  
    static int age = 45;  
}  
class Daughter extends Father{  
}  
class Main{  
    public static void main(String[] args){  
        System.out.println(STR."Father Age before : \{Father.gender}");  
        System.out.println(STR."Father gender before : \{Father.age}");  
        
        Daughter.age = 24;  
        Daughter.gender = 'F';  
        
        System.out.println(STR."Daughter gender : \{Father.gender}");  
        System.out.println(STR."Daughter age : \{Father.age}");   
        
        System.out.println(STR."Father gender after: \{Father.gender}");  
        System.out.println(STR."Father Age after: \{Father.age}");  
    }  
}
```
```Output
Father Age before : M
Father gender before : 45
Daughter gender : F
Daughter age : 24
Father gender after: F
Father Age after: 24
```

### Final keyword
- ``final variable = value;`` this is the syntax for the final keyword
- While you use this keyword , we can't modify the variable anywhere of the program
- This can be also used while declaring a method
```Java
class Sample{
	final void display(){
		System.out.println("This is Parent Class || Note");
	} // This function can't be modified , even in the child class
}
```

### Super keyword
- Super keyword is used to get the specific property of the parent class
```Java
class Parent{
	char gender = 'M';
}
class Daughter extends Parent {
	char gender = 'F';
}
class Main {
	public static void main(String[] args){
		Daughter daughter = new Daughter();
		System.out.println(daughter.super.gender); // M will be printed
	}
}
```

### This keyword
- This keyword refers to the current object
```Java
class Parent{
	char gender;
	int age;
	void Setter(char gender,int age){
		this.gender = gender; // this.gender refer to object , gender refer to parameter
		this.age = age; // this.age refer to object , age refer to parameter
	}
}
```

