
[Video Link](https://youtu.be/nqB3qAtDLKU?si=cXvAxcoYJWWKvEOa)
Next Topic [[Advance concepts]]
### Methods 
- Methods are nothing but the function that we are defined inside the class 

```Java
class Maths {  
    public int add(int a,int b){  
        return a+b;  
    }  
}
```

### Classes and objects
- Classes are the templates that is used to define a object
- Ex : a human body is a template and you are an object

```Java
class ApplicationForm{  
    String Name;  
    int AdmissionNo ;  
    String Qualification;  
      
    public void setValue(String InpName,int InpAdmissionNo , String InpQualification) {  
        Name = InpName;  
        AdmissionNo = InpAdmissionNo;  
        Qualification = InpQualification;  
    }  
	public void InfoDisplayer(){  
	    System.out.println(STR."Name : \{Name}");  
	    System.out.println(STR."AddNo : \{AdmissionNo}");  
	    System.out.println(STR."Qualification : \{Qualification}");  
	}  
}
```

### Creating Object
- Using the constructor , we created the object
```Java
public class NewClass{  
    public static void main(String[] args){  
        ApplicationForm Student1 = new ApplicationForm();  
        Student1.setValue("Praveen", 1,"12th");  
        Student1.InfoDisplayer();  
    }  
}
```

### Access Modifiers
- Control the permission for who can be access or can't be access some methods and fields
![[Pasted image 20240211152011.png]]
##### Public 
- Any file in any package can be accessing this class or method or fields

- The main function must be a public , because it should be accessed by the compiler 
##### Private
- Any file under private , can only be accessed within the specific class , can't be accessed out side of the class
- In the above example in creating object , we created object in the a different class named 'New Class ' Incase if we give the methods as private , those give us error
- Fields also can be marked as private 
```Java
class ApplicationForm{  
    private String Name;  
    private int AdmissionNo ;  
    private String Qualification;  
  
    public void setValue(String InpName,int InpAdmissionNo , String InpQualification) {  
        Name = InpName;  
        AdmissionNo = InpAdmissionNo;  
        Qualification = InpQualification;  
    }  
    private void InfoDisplayer(){  
        System.out.println(STR."Name : \{Name}");  
        System.out.println(STR."AddNo : \{AdmissionNo}");  
        System.out.println(STR."Qualification : \{Qualification}");  
    }  
    public String getName() {  
        return Name;  
    }  
}  
public class FileName{  
    public static void main(String[] args){  
        ApplicationForm Student1 = new ApplicationForm();  
        Student1.setValue("Praveen", 1,"12th");  
        System.out.println(Student1.getName());  
    }  
}
```
##### Setter and getter 
- These are the methods that are used to modify , get the private fields 
- This is possible because the methods is a part of that class
- Ex : This methods should be given in public , so that user can be accessed'
```Java
public void setValue(String InpName,int InpAdmissionNo , String InpQualification) {
	// Setter method 
	Name = InpName;  
	AdmissionNo = InpAdmissionNo;  
	Qualification = InpQualification;  
} 
public String getName() { // Getter method 
	return Name;  
}
```

##### Protected
- This access modifier give permission within the java file , can't be accessed outside the file pr packages

##### Default
- Incase if you didn't specified any of the above , it will be taken under the default 
- These files can be accessed within the package , not outside the package

### Constructor
- The constructor is used while creating objects
- ``ClassName ObjName = new ClassName();``
The class name with parentheses is called as the constructor
```Java
class OldRecords{  
    int RollNo;  
    float Percentage;  
}  
class DaySkill{  
    public static void main(String[] args) {  
        OldRecords Std1 = new OldRecords();  
    }  
}
```
##### Using of Constructor
- The constructor does nothing without any action
```Java
class OldRecords{  
    int RollNo;  
    float Percentage;  
    OldRecords(){  
        System.out.println("This is default constructor");  
    }  
}  
class DaySkill{  
    public static void main(String[] args) {  
        OldRecords Std1 = new OldRecords();  
    }  
} // Output : This is default constructor
```
- Simply the constructor runs whenever you create an object , this can be called only once while creating the object
-  you can not only print out any sentence , also you can set default value to your fields
##### Parameterised Constructor
- Here we can also pass the parameters for the constructor 
```Java
class OldRecords{  
    int RollNo;  
    float Percentage;  
    OldRecords(int InpRollNo , float InpPercentage){  
        RollNo = InpRollNo;  
        Percentage = InpPercentage;  
    }  
    public void Display(){  
        System.out.println(STR."RollNo : \{RollNo} \nPercentage : \{Percentage}");  
    }  
}  
class DaySkill{  
    public static void main(String[] args) {  
        OldRecords Std1 = new OldRecords(1, 98.23F);  
        Std1.Display();  
    }  
}
```

