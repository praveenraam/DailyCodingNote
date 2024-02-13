[VideoLink](https://youtu.be/nqB3qAtDLKU?si=_2tOKEdxbDwZEFjl&t=9480)
Next Topic [[File Handling]]
### An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions

- To continue the flow of the program we need to handle exception , we can use the try catch block to do it
### Using Try Catch 
- The try block is the place where you need to place the code that may give you exception during the execution
- The catch block is the block where we place the code that should be executed when exception is raised
### Handling zero division by error
```Java
class Main{
	public static void main(String[] args){
		int a = 10;
		int b = 0;
		try{
			int c = a/b;
			System.out.println(c);
		}catch(ArithmeticException E){
			System.out.println("B is zero , division can't be done");
		}
	}
}
```

### Finally block 
- This block will be executed every time the code runs , even the exception raises and the catch block handled it , finally is executed and if no exception raised , also then finally is executed
```Java
class Main{
	public static void main(String[] args){
		int a = 10;
		int b = 0;
		try{
			int c = a/b;
			System.out.println(c);
		}catch(ArithmeticException E){
			System.out.println("B is zero , division can't be done");
		}finally{
			System.out.println("");
		}
	}
}
```

### Catch block
- You can use multiple catch block for the same try block
- You can also run the code without the catch block 
```Java
class Main{
	public static void main(String[] args){
		int a = 10;
		int b = 0;
		try{
			int c = a/b;
			System.out.println(c);
		}finally{
			System.out.println("");
		}
	}
}
```

### Throw keyword
- When you need to throw an Exception , you can use it 

```Java
class Main(){
	static void Check(int age){
		if(age<18) throw new ArithmeticException("AgeInvalid");
	}
	public static void main(String[] args){
		int age = 12;
		try(
			check(age);
		)
		catch(ArithmeticException E){
			System..out.println(E);
		}
	}
}
```

### User Define Exceptions
- User can also define some exceptions 
- All the Predefined Exceptions are class , so we need to create a class for creating our exception
- Our class must extends the 'Exception' class that is predefined

```Java
Class UserDefine extends Exception{
	UserDefine(String Str){
		super(Str);
	}
}
```

##### Example
```Java
Class UserDefine extends Exception{
	UserDefine(String Str){
		super(Str);
	}
}
class Main(){
	static void Check(int age) throws UserDefine { // we mark as throws UserDefine because it is used for finding the correct catch block, can also give multiple Exception types
		if(age<18) throw new UserDefine("AgeInvalid");
	}
	public static void main(String[] args){
		int age = 12;
		try(
			check(age);
		)
		catch(UserDefine E){
			System..out.println(E);
		}
	}
}
```

