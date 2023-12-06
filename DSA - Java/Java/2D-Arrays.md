Video [Link](https://youtu.be/n60Dn0UsbEk?si=pHObnTqNPKbPtJzR&t=2559)
Topic No 11
Next Topic [[ArrayList]]

2D arrays are the start of the multi dimensional array

#### The Element of the Array is itself an array which is 2D Array (Array of Arrays)

Example : 2D 
```Java
{{2,3,4},{5,6,7},{8,9,0},{1,2,3}}

{ {2,3,4} , 
  {5,6,7} , 
  {8,9,0} , 
  {1,2,3} }
```
This is How 2D Arrays are stored

##### Syntax 
```Java
data_type[][] array_name = new data_type[size][size(not_mandatory)];
// or directly
data_type[][] array_name = {
	{data,data,data}, 
	{data,data.data}
}
```
Mentioning the size of the row is mandatory


### Internal working of 2D array

![[Pasted image 20231206113220.png]]

- The size of the row are no need to mention ( not mandatory ) because they can vary their size
- They can have different size for each row also


### 2D Inputs

Input for the 2D array can be get by the Nested Loop

```Java
import java.util.Scanner;  
import java.util.Arrays;  
  
public class Arr {  
    public static void main(String[] args) {  
    
        Scanner Inp = new Scanner(System.in);  
        int[][] Arr2D = new int[3][2];  
        
        for (int row=0;row< Arr2D.length;row++){  
            for(int col=0;col<Arr2D[row].length;col++){  
                Arr2D[row][col] = Inp.nextInt();  
            }  
        }  
        System.out.println(Arrays.toString(Arr2D[0]) + "  " + Arrays.toString(Arr2D[1]) + "  " + Arrays.toString(Arr2D[2]));  
    }  
}
```

### 2D Output

Output for the 2D array also can be get by the Nested Loop

```Java
import java.util.Scanner;  
import java.util.Arrays;  
  
public class Arr {  
    public static void main(String[] args) {  
    
        Scanner Inp = new Scanner(System.in);  
        int[][] Arr2D = new int[3][2];  
        
        for (int row=0;row< Arr2D.length;row++){  
            for(int col=0;col<Arr2D[row].length;col++){  
                System.out.print("  "+Arr2D[row][column]); 
            }
            System.out.println("");  
        }   
	    // OR 
	    for(int row = 0;row < Arr2D.length ; row++){
		    System.out.print(Arrays.toString(Arr2D[row]));
	    }
	    //OR
	    for(int[] a : Arr2D){
		    System.out.print(Arrays.toString(a));  
	    }
    }  
}

```


## ArrayList

They are dynamic form of array , they can handle any number of array without specifying the input size of the Array

## Syntax

```Java
ArrayList<generic_type> arr_name = new ArrayList<>(initial_capacity_in_no(optional));
```
generic type is Integer , String like these things
#### Ex :
```Java
ArrayList<Integer> IntArr = new ArrayList<>(10);
ArrayList<String> StrArr = new ArrayList<>();
```

### Array Execution

```Java
import java.util.ArrayList;  
import java.util.Scanner;  
import java.util.Arrays;  
  
public class Arr {  
    public static void main(String[] args) {  
        ArrayList<Integer> ArrList = new ArrayList<>(10);  
        
        ArrList.add(90990);  
        ArrList.add(654);  
        ArrList.add(564);  
        ArrList.add(54);  
        ArrList.add(897);  
        ArrList.add(90990);  
        ArrList.add(654);  
        ArrList.add(564);  
        ArrList.add(54);  
        ArrList.add(897);  
        ArrList.add(90990);  
        ArrList.add(654);  
        ArrList.add(564);  
        ArrList.add(54);  
        ArrList.add(897);  
        System.out.println(ArrList.contains(897)); // true
        System.out.println(ArrList); // prints all the elements inside it
        ArrList.set(2,3232); // Value of 3rd element is updated
        System.out.println(ArrList[2]); // 3232
        ArrList.remove(3) // Element in the index position 3 is removed (54)
        System.out.println(ArrList[3]);//897-All elements are moved right one position
    }  
}
```
- In print statement you no need to add .toString method because the ArrayList class have the method to call it while print statement 

```Output
true
[90990, 654, 564, 54, 897, 90990, 654, 564, 54, 897, 90990, 654, 564, 54, 897]
3232
```

- There are lot of methods are there for Array List Object 

### Array List Inputs 

```Java
import java.util.ArrayList;  
import java.util.Scanner;  
import java.util.Arrays;  
  
public class Arr {  
    public static void main(String[] args) {  
    
        Scanner Inp = new Scanner(System.in);  
        ArrayList<Integer> ListValue = new ArrayList<>();  
        
        int count=0;  
        while(count<=5){  
            ListValue.add(Inp.nextInt());  
            count++;  
        }  
        System.out.println(ListValue);  
    }  
}
```

