
[Link of Video](https://youtu.be/Fo2Qnw5pMGo?si=OwriWFEJK-57QRKB)

#algorithm

==Next Topic : [[Arrays and Objects]]== 
## What is an analysis

#### There are multiple ways to solve a problem then , How can we know which is best 

- We got the solution by measuring the Performance and the efficiency of the code 
-  Measuring the performance of the algorithm is not same as we used in day today life 
- It depends on the number of factors
## Factors Algorithms depend on

- Programming language used
- The computer the program runs on
- OS quality used 
- Other program running on the same time



## Two Types of complexity

 #TypeOfComplexity

### Time 
- Amount of time taken by the algorithm to run , as of input 

If you have little memory to work with , you should be picking the slower so uses less space.

### Space 
- Amount of space taken by the algorithm to run , as of input 
 
 If your App need to be fast it has to be work with plenty of space ,  You no need to worry about your Space complexity.

## Representation of complexity 

#### There are mathematical tool to represent time and space complexity : Asymptotic Notation  

- Big-O notation : Worst Case #bigOnotation
- Omega notation : Best Case  #omegaNotation
- Thete notation : Average Case #theteNotation


## Big-O Notation

#bigOnotation 

### This is represented using the Input 


### Time Complexity

```JS 
function Summation(n){
	let sum = 0;
	for(let i=0;i<=n;i++){
		sum += i;
	}
	return sum;
}
```

In the above code there are three statements , The statement at line 2 and 6 runs only once and the statement at line 4 runs as per the input N 

So the Complexity is ==n+2== 
As input increases time complexity increases

==O(n) - Linear complexity== 

#### Constant complexity
```js
function summation(0){
	return (n*(n+1)/2);
}
```
Only one loop and statement run only once then ==O(1) - constant== complexity 
```js
for(let i=0;i<=n;i++){
		for(let j=0;j<=n;j++){
		// code here
	}
}
```
If there are two nested loops then ==O(n2) - Quadratic==
In case of three nested loops then ==O(n3) - Cubic==
In case of size reduced by half every iteration then ==O(logn) - Logarithmic==

### Space complexity

==O(1)== doesn't need an extra space for the execution

==O(n)== extra space requires as the input size grows

==O(logN)== extra space require grow not in an uniform rate


==Different algorithm works well under different constraints==


### Big O notation Guide 

O(1) : Not depend on input size
O(n) : 1 Loop
O(n^2)  : 2 Loop
O(logn) : Half of Input size

### Chart 
	![[Pasted image 20231002120746.png]]






