Video [Link](https://youtu.be/FPu9Uld7W-E?si=2izuf9OOfW-Uq8Zk)
Next Topic : [[Basic Math]]

You code will be judged on using the time and complexity result
These are not the time and space taken by your program while running in seconds or bytes

==Use Big O Notation to represent it==
## What is Time complexity
- The rate at which time taken increases with respect to the input is time complexity

#### Steps :
- Always calculate time complexity for the worst case scenarios 
- Avoid constants 
- Avoid Lower values
#### Cases
- Best Case
- Worst Case
- Average Case ( Median of best and worst )

#### Log and time
- If the loop is based on the division , then the time complexity will be based on the Log
- Incase the loop is of divide by 2 , then O(log2(N)) or Divide by 10 - O(log10(N))
## What is Space complexity
- The amount of space increases with respect tot the input is space complexity

#### 2 Spaces
- Auxiliary Space : The space that is taken to solve the problem
- Input Space : The space that is taken to store the problem
Ex :
```Java
function add(a,b){
	int x = a+b; // a and b are the Input space
	return x; // X is the variable used to solve the problem , so Auxiliary
}
```

