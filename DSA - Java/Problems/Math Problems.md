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