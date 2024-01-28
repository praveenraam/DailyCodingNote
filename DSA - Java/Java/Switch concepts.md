Video [Link](https://youtu.be/mA23x39DjbI?si=CTZ9zNSmtQMSn9Ac)
Topic No : 7
Next Topic [[Function (Methods)]]

Difference between ' == ' and '.equal' function

In case if you are comparing two variables with == symbol , it give true only if the variables in stack are pointing same value in the heap 

![[Pasted image 20231204193934.png]]
In this condition , it gives us true

![[Pasted image 20231204193955.png]]
But in this condition , it gives us false 

##### ==In the case of .equal operation , it gives us true in both the cases== 




## Switch Statement

![[Pasted image 20231204200705.png]]

## Enhanced switch

This make the code more simple and easily readable 
![[Pasted image 20231204204525.png]]
- Here break keyword is not necessary
- This is simple and reduce the no of lines the code written


### Problem in switch

Finding weekday or weekend
```Java
switch (day)
	case 1 : 
	case 2 :
	case 3 :
	case 4 :
	case 5 :
		System.out.println("Weekday");
		break;
	case 6 :
	case 7 :
		System.out.println("Weekend");
		break;
	
```

```Java
// Enhanced switch
switch(day)
	case 1,2,3,4,5 -> System.out.println("Weekday");
	case 6,7 -> System.out.println("Weekend");
```
Finding Day of the week

```Java
String dayWord;
switch (day)
	case 1 -> dayWord = "Monday";
	case 2 -> dayWord = "Tuesday";
	case 3 -> dayWord = "Wednesday";
	case 4 -> dayWord = "Thursday";
	case 5 -> dayWord = "Friday";
	case 6 -> dayWord = "Saturday";
	case 7 -> dayWord = "Sunday";
	default -> System.out.println("Enter a valid number");
```

## Nested switch

Syntax for Nested switch
```Java
switch (Expression) {
	case Value1 :
		switch (Expression)
			case Value1(1) :
				// Body
				break;
			case Value1(2) :
				// Body
				break;
			case Value1(3) :
				// Body
				break;
			default :
				// Body
		break;
	case Value2 :
		switch (Expression)
			case Value1(1) :
				// Body
				break;
			case Value1(2) :
				// Body
				break;
			case Value1(3) :
				// Body
				break;
			default :
				// Body
		break;
	default :
		//Body
	}
```

