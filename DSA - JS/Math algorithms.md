know this before [[Arrays and Objects]]   #algorithm/math 
Next Topic [[Recursion and problem]]
## Fibonacci sequence 

##### ==Problem statement== : Give a number 'n' , find the first 'n' elements of  Fibonacci series
##### What is Fibonacci : It is a sequence in which each number is the sum of the two preceding ones

Ex : 
- Fibonacci(2) - (0,1)
- Fibonacci(4) - (0,1,1,2)
- Fibonacci(7) - (0,1,1,2,3,5,8)

##### Solution :
```js
function fibonocci(n) {
    const arr = [0,1];
    for(let i=2;i<n;i++){
        arr[i] = arr[i-1]+arr[i-2];
    }
    return arr;
}
console.log(fibonocci(5)) // [ 0, 1, 1, 2, 3 ]
console.log(fibonocci(10)) // [ 0, 1,  1,  2,  3, 5, 8, 13, 21, 34 ]
```

![[Algorithm Analysis#Big O notation Guide]]
**Use this for the further topic in this File**

==Big - O notation : O(n) Linear==

## Factorial of number

##### ==Problem== : Given an integer 'n' , find the factorial of the integer

##### What is Factorial : It is denoted as n! , it is product of all the numbers less and equal to n

Ex : 
- Factorial(4) - 24
- Factorial(3) - 6
- Factorial(10) - 3628800

##### Solution

```js
function Factorial(n){
    let result = 1;
    for(let i=2;i<=n;i++){
        result = result * i;
    }
    return result
}
console.log(Factorial(5)) // 120
console.log(Factorial(10)) // 3628800
```

==Big O Notation : O(n) - Linear==


## Prime Number

##### Problem : Give a natural number , determine whether prime or not'

##### What is Prime Number : this is not a product of two numbers
Ex:
- IsPrime(4) : (1 * 4 , 2 * 2 ) : False
- IsPrime(5) : (1 * 5) : True
- IsPrime(10) : (5 * 2 , 1 * 10 ) : False

##### Solution : 
```js
function isPrime(n){
    if(n<2){
        return false
    }
    for(let i=2;i<Math.sqrt(n);i++){
        if(n%i === 0){
            return false
        }
    }
    return true
}
console.log(isPrime(10)); // False
console.log(isPrime(3)); // True
```

Big O Notation : **O(sqrt(n))** : Linear



## Power of two

##### ==Problem== : check whether given 'n' is power of two or not

Ex :
- isPowerOfTwo(512) : True
- isPowerOfTwo(510) : False


##### Solution

 ``` PseudoCode
n=8

8/2 = 4 (0 remainder)
4/2 = 2 (0 remainder)
2/2 = 1 (0 remainder)

- if remainder not 0 in nay step , not power of two
- if remainder is 0 and n come down to 1 eventually , n is power of two

```

```js 
function isPowerOfTwo(n){
    if(n<1){
        return false
    }
    while(n>1){
        if(n%2 !== 0){
            return false
        }
        n = n/2;
    }
    return true
}
console.log(isPowerOfTwo(510)) // False
console.log(isPowerOfTwo(512)) // True
```

==Big O Notation : 0(logn) - Logrithmic== 

