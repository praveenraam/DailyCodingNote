#Problems 

Know this before : [[Sorting Algorithms]]
Next Topic :

## Cartesian Product 

##### ==Problem== :
Given two finite non-empty sets, find their Cartesian Product.
In mathematics, specifically set theory, the Cartesian product of two sets A and B, denoted AxB,
is the set of all ordered pairs (a, b) where a is in A and b is in B

Ex :
const A = [1, 2]
const B = [3, 4]
AxB = [ [1, 3], [1, 4], [2, 3], [2, 4] ]

const C = [1, 2]
const D = [3, 4, 5]
CxD = = [ [1, 3], [1, 4], [1, 5], [2, 3], [2, 4], [2, 5]]


##### Solution : 
```Js
function cartesianProduct(arr1,arr2){
    let Product = []
    for(let i=0;i<arr1.length;i++){
        for(let j=0;j<arr2.length;j++){
            Product.push([arr1[i],arr2[j]]);
        }
    }
    return Product;
}
console.log(cartesianProduct([2,3],[3,4])); 
/*
 [ [ 2, 3 ], [ 2, 4 ],
  [ 2, 5 ], [ 2, 6 ],
  [ 3, 3 ], [ 3, 4 ],
  [ 3, 5 ], [ 3, 6 ] ]
*/
```

Big O Notation : O(nm)


## Climbing Stair Case


##### ==Problem== 
Given a staircase of 'n' steps, count the number of distinct ways to climb to the top.

You can either climb 1 step or 2 steps at a time.

n=1, climbing Staircase(1) = 1 |(1)
n=2, climbing Staircase (2) = 2 |(1, 1) and (2)
n=3, climbing Staircase(3) = 3 | (1,1,1) (1, 2) and (2, 1)
n=4, climbing Staircase(4) = 5 |(1,1,1,1) (1,1,2) (1,2,1) (2,1,1) and (2,2)

##### Idea : 

At any given time, you can climb either 1 step or 2 steps
If you have to climb to step 'n', we can only climb from step 'n-1' or 'n-2'

Calculate the ways we can climb to 'n-1' and 'n-2' steps and add the two

climbing Staircase (n) = climbing Staircase (n-1) + climbing Staircase (n-2)


##### Solution : 
```Js
function ClimbingStairCase(n){
    let result=0;
    for(i=2;i<n;i++){
        result += (i-1)+(i-2);
    }           
    return result-1
}

console.log(ClimbingStairCase(5)) //8
```




## Tower of Henoi

#####  Problem 
