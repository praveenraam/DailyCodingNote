Video [Link](https://youtu.be/TAtrPoaJ7gc?si=y-wfiA1tf6vmBvcr&t=4121)
Topic No : 5
Next Topic : [[Conditions and Loops]]

#### [Order of precedence](https://chatgpt.com/c/67e81db3-3d30-8007-a33e-1afbc3de476f)

#### Type Conversion
```Java
import java.util.Scanner

public class TypeCasting{
	public static void main(String[] args){
		
	}
}
```

- Type conversion only takes place if the data types are comparable
- Float is greater than integer , so it can type conversion
- The greater value should be in left hand side , if not it give us error

``  int num = inputs.nextfloat(); // Error  ``
``  float num = inputs.nextint(); // True   ``  

Required float and you gives int - No error
Required int and you gives float - Error

#### Type casting 

- Compressing the bigger number into smaller 
- Ex : Converting a float number into int number

```Java
int num = 12.234f; //Error
int num = (int)(12.243); // If we print Out = 12
```


#### Example 

```Java
byte b = 0;
char c = 'a';
short s = 1024;
int i = 50000;
float f = 5.67f;
double d = 0.123;
double results  = (f*b) + (i/c) - (d-s)

System.out.println((f*b) + "" + (i/c) + "" (d-s)); // 238.14    515   -1023.8766
System.out.println(results); // 1777.0166146484376
```


#### Temperature conversion Program 

```Java
import Java.util.Scanner

public class TempConversion{
	public static void main(){
		Scanner InpGet = new Scanner(System.in);
		float InpTemp = InpGet.nextfloat();
		float ConvTemp = (InpTemp * 1.8) + 32;
		System.out.println(ConvTemp);
	}
}
```

