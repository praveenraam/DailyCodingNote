
#### Learnt Things 

##### Splitting Multiple Numbers

- Braking a multiple digit number to single number to do operation , that can be achieved by dividing the number with 10 and getting the remainder 
```Java
int remainder = GnInp % 10 ;
```
- This statement get the last number of the multiple digit number
##### Conversion of String to Int

```Java
int ConvertedValue = Integer.parseInt(StringValue);
```

#### [Last Digit of the Powered Number](https://www.geeksforgeeks.org/problems/find-last-digit-of-ab-for-large-numbers1936/1)

##### Find : 
You are given two int numbers, the base a and the index b. You have to find the last digit of ab.
```Java
class Solution {  
    public static void main(String[] args) {  
        System.out.println(getLastDigit("8","10"));  
    }  
    static int getLastDigit(String a, String b) {  
        int Buttom = Integer.parseInt(a);  
        int Top = Integer.parseInt(b);  
        int resultValue = 1;  
        for(int i=1;i<=Top;i++){  
            resultValue = resultValue*Buttom;  
        }  
        return resultValue%10;  
    }  
}
```

#### [Count Digits](https://practice.geeksforgeeks.org/problems/count-digits5716/1)

##### Find : 
Given a number **N**. Count the number of digits in N which evenly divides N.
```Java
class Solution {  
    public static void main(String[] args) {  
        System.out.println(evenlyDivides(5050));  
    }  
	static int evenlyDivides(int N){  
		int Temp = N;  
		int count = 0;  
		while(Temp > 0){  
			int remainder = Temp%10;  
			if(remainder != 0) {  
				if (N % remainder == 0) count++;  
			}
			Temp/=10;  
		}  
		return count;  
	}
}
```

#### [Reverse Number](https://www.geeksforgeeks.org/problems/reverse-digit0316/1)

##### Find :
Reverse the given number
```Java
class Solution
{
    public long reverse_digit(long n)
    {
        long result = 0;
        while(n>0){
            long remainder = n%10;
            result*=10;
            result+=remainder;
            n/=10;
        }
        return result;
    }
}
```

#### [GCD](https://practice.geeksforgeeks.org/problems/gcd-of-two-numbers3459/1)

##### Find:
GCD of given two numbers
```Java
class Solution
{
    public int gcd(int A , int B) 
    { 
        int min = Math.min(A,B);
        int result = 0;
        int index=1;
        while(index <= min){
            if(A%index == 0 && B%index == 0){
                result = index;
            }
            index++;
        }
        return result;
    }
}
```

After reading the Algorithm
```Java
public static int Largest_GCD(int A,int B){  
    if(A==B){  
        return A;  
    }else if(A>B){  
        return Largest_GCD(A-B,B);  
    }else {  
        return Largest_GCD(A,B-A);  
    }  
}
```

#### [Divisor of the Number](https://www.codingninjas.com/studio/problems/print-all-divisors-of-a-number_1164188)
##### Find:
Return the Divisors of Input number 
```Java
public static List<Integer> Result_printDivisors(int n) {  
    List<Integer> Result = new ArrayList<>();  
    int Divisor = 1;  
    while(Divisor <= n){  
		    
        if(n%Divisor == 0){  
            Result.add(Divisor);  
        }  
        Divisor++;  
    }  
    return Result;  
}
```

#### [Prime Number](https://practice.geeksforgeeks.org/problems/prime-number2314/1)

##### Find:
Given number prime number or not
```Java
static boolean isPrime(int N){  
    if (N == 1) {  
        return false;  
    }  
    int Divisor = 1;  
    int Count = 0;  
    while (Divisor < N) {  
        if (N % Divisor == 0) {  
            Count++;  
        }  
        Divisor++;  
    }  
    return (Count == 1);  
}
```

#### [Amstrong Number](https://www.geeksforgeeks.org/problems/armstrong-numbers2727/1)

##### Find:
Check whether the given number is Armstrong Number or not

```Java
static String armstrongNumber(int n){
        int result = 0;
        int temp = n;
        while(n>0){
            int remainder = n%10;
            remainder *= (remainder*remainder);
            result += remainder;
            n/=10;
        }
        if(result == temp){
            return "Yes";
        }
        return "No";
    }
```

#### [Palindrome](https://practice.geeksforgeeks.org/problems/palindrome0746/1)

##### Find:
Return Yes or No if Given number is palindrome

```Java
public String is_palindrome(int n){
        int result = 0;
        int temp = n;
        
        while(n>0){
            int remainder = n%10 ;
            result *= 10 ;
            result+=remainder;
            n/=10;
        }
        
        if(temp == result){
            return "Yes";
        }else{
            return "No";
        }
    }
```

#### [Perfect Number](https://practice.geeksforgeeks.org/problems/perfect-numbers3207/1)

##### Find:
Check if the Given number is Perfect or Not
```Java
static int isPerfectNumber(long N) {
        int result = 1;
        long index;
        
        for(index=2;index<N;index++){
            
            if(N%index == 0){
                result += index;
            }
        }
        
        if(result == N){
            return 1;
        }
        return 0;
    }
```

#### [Square Root of a number](https://www.geeksforgeeks.org/problems/square-root/1)

#### Find :
return the nearly square root value of the given value
```Java 
long floorSqrt(long x)
	{
	    long ans = 1;
	    for(long i=1;i<x;i++){
	        
	        if(i*i <= x){ /* Here we use the i*i because we can reduce the time                                 complexity */
	            ans = i;
	        }
	        else{
	            break;
	        }
	    }
	    return ans;
	}
```
We use the i* i to get the nearby perfect square number to get the square root of the nearly number

#### [7. Reverse Integer](https://leetcode.com/problems/reverse-integer/)

```Java
class Solution {
    public int reverse(int x) {
        long result = 0;
        while(x!=0){
            int remainder = x%10;
            result= (result*10)+remainder;
            if(result > Integer.MAX_VALUE) return 0;
            if(result < Integer.MIN_VALUE) return 0;
            x/=10;
        }
        if(result >= Integer.MIN_VALUE && result <= Integer.MAX_VALUE) return (int)result;
        else return 0;
    }
}
```

