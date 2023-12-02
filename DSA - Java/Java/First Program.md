Download JDK Oracle [Link](https://www.oracle.com/java/technologies/downloads/)
Download IntelliJ IDEA Community Edition [Link](https://www.jetbrains.com/idea/download/?section=windows)

Video [Link](https://youtu.be/TAtrPoaJ7gc?si=oqv-OgcwKSocjO3U)
## Creating Main function

```Java
public class Main {
	public static void main(String[] args){
		System.out.println("Hello World!!");
	}
}
```

- ==The name of the file should be the name of the class== 
- In first line the ``public class Main`` the main should be replaced with the file name , first letter capitalized : Ex File name is Popup.java , The class should be ``public class Popup``
- Incase if you need the .class file of the source code file you need execute these commands in the terminal ``javac filename.java``
- You can run that new file created with .class extension using command ``java filename``

![[Pasted image 20231202132213.png]]

## Explaining of program

### 1st Line
##### 'public' word
It means that the class can be accessed from anywhere 

##### 'class' word
- It is a named group of properties and methods
- All functions inside the classes are methods

##### 'Main' word
- It is the name of the class (As the name of the file is also Class)

### 2nd Line
##### 'main' word 
- This main is in the second line , which is the entry point of the program

##### 'public' word
- As the main is the entry point , it makes sense that it should be available to the program

##### 'static' word
- The variable that are independent of the object , that are static , they should be said that they can be act individual without declaring of any objects. So , we mention it as static
- Simply , the static is to say that you need to run the main function in the second line without creating an object

##### 'void' word
- It mentions the return value of the function , as it return nothing it is void
- Incase it return a number you need to mention it as 'int'

##### 'String[]' word
- It is nothing but a collection of string data stored in a array



## Change location of the byte file

In terminal ``javac -d location_you_need_to_keep_file(../../ or . or ../) filename``


