Video [Link](https://youtu.be/n60Dn0UsbEk?si=GogqE5HHSXcz5Qk7)
Topic No : 10
Next Topic [[]]

## Syntax

```Java
Data_type[] variable_name = new data_type[size];
//or Directly
Data_type[] Variable_name = {data,data,data,....};
```

#### Example : Storing 5 Roll Numbers

```Java
int Rollnumbers = new int[5];
// Or directly
int Rollnumbers = {23,24,25,26,27};
```

- The datatype at first represent the type of data going to be stored in the Array
- We can't include an another datatype inside that array other than the mentioned one

## How arrays works

```Java
int[] ros; // Declaration of array. Ros are defined in the stack
ros = new int[5]; // Init of Array. now the object is created in the memory Heap
```

#### Dynamic Memory Allocation

This is nothing but the memory allocations are done in the Run Time of the program
![[Pasted image 20231205204424.png]]

#### Internal representation of Array

For array , Memory allocation should be done continuously

- As we know that objects are created in Heap memory
- But , in Heap object are not continuous
- Dynamic Memory allocation
Hence , coming to the conclusion Arrays in Java may not be store continuously (Depends on JVM)

