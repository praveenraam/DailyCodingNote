
Know This before [[Math algorithms]]
Next Topic [[Search Algorithms]] 

## Recursion

- It is a problem solving technique where the solution depend on the solution to smaller instance of the problem
- The function that call itself is called recursion


## Fibonacci using Recursion

###### Solution
```Js
function ReverseFibonacci(n){
    if(n < 2){
        return n
    }
    return ReverseFibonacci(n-1)+ReverseFibonacci(n-2);
}
console.log(ReverseFibonacci(6))
```

==Big O Notation : O(2^n)== 



## Factorial 

```js
function RecursionFactorial(n){
    if(n===0){
        return n+1
    }
    return n*RecursionFactorial(n-1);
} 
console.log(RecursionFactorial(4)) // 24
console.log(RecursionFactorial(5)) // 120
console.log(RecursionFactorial(10)) // 3628800	
}
```

==Big O Notation : O(n)==


