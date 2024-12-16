Video [Link](https://youtu.be/4EP8YzcN0hQ?si=OjKwPlTzFmwAowEy)
Topic No : 1
Next Topic [[First Program]]
## Java's file execution Steps

#### Step 1

==All the java files will be in the .java extension==

That file contains the code that we write 
#### Step 2

When you execute the file , this is compiled and converted into bytes code with the extension of .class 

This .class file can run on a system , you need a JVM (Java virtual machine). This is the reason why java is called as platform independent 

#### Step 3

That .class file is run on the JVM and it is converted to the machine code ( 0's and 1's )
This file is interpreted on JVM 

![[Pasted image 20231202093202.png]]

## Platform independence

==This is nothing but shows that the code can run on all the operating system==

- The main motive is to convert the source file into the machine code so that the computer understands
- Compiler turns source into executable file , this executable file is set of instruction for computer

- If we compile the C/C++ code , we get the .exe file which is platform dependent
  but incase of the java , we get the byte code , then the JVM converts into machine code
- Java is platform independent but the JVM is platform dependent


## What is JDK

- Provides environment to develop and run the java program
- It includes a package that contains
	 - Provide environment to develop a program
	 - JRE - to execute your program
	 - Compiler Name  - javac
	 - archiver - jar
	 - docs generator - javadocs
	 - interpreter and loader

## What is JRE

- It is an installation package that provides environment to only run the program 
- It consist of 
	- Deployment technologies
	- User interface toolkit
	- Integration Lib
	- Base Lib
	- JVM
- After we get the .class file the next things happens at runtime 
	- class loader loads all the classes needed to execute the program 
	- JVM sends code to Byte code verifier to check the format of the code


## How JVM Works

![[Pasted image 20231202095830.png]]


## Process on execution

![[Pasted image 20231202111617.png]]

The JVM requirements are provided by the JRE of JDK like lib , env .
JRE is a box that contains the JVM . 

## Dynamic Memory Allocation

- This is nothing but the memory is allocated at the run time

```Java
ArrayList ls = new ArrayList();
```

The left side of the "=" is happening at the compile time and the right side is done in the run time.

The ls is first stored in the stack memory and while in the run time, after memory allocation the reference variable is pointed to the object.