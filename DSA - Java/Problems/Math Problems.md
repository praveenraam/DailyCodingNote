
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

### [Swap the last ans First number in digit]()
```Java
import java.util.*;
class HelloWorld {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int inp = in.nextInt();
        System.out.println(swapper(inp));
    }
    public static int swapper(int inp){
        if(inp < 10) return inp;
        int temp = inp;
        int ans = 0;
        int first = - 1, last = inp%10;
        while(inp>0){
            first = inp%10;
            inp/=10;
        }
        inp = temp;
        ans+=last;
        inp = inp / 10;
        int reverse = 0;
        while(inp>10){
            reverse = (reverse*10)+(inp%10);
            inp = inp / 10;
        }
        while(reverse > 0){
            ans = (ans*10)+(reverse%10);
            reverse/=10;
        }
        ans = (ans*10)+(first);
        return ans;
    }
}
```

```C
#include <stdio.h>

int main(){
    int inp;
    scanf("%d",&inp);
    
    int dup = inp;
    int Fno;
    int Lno = inp%10;
    dup/=10;
    int rev = 0;
    
    while(dup>0){
        Fno = dup%10;
        dup/=10;
        rev = (rev*10)+Fno;
    }
    int result = 0;
    result = Lno;
    /
    dup = rev;
    rev/=10;
    while(rev>0){
        int rem = rev%10;
        result = (result*10)+rem;

        rev/=10;
    }
    
    result = (result*10)+Fno;
    
    printf("%d",result);
    
}
```

### [Sum of prime divisors]()
```Java
public static void main(String[] args) {
    Scanner in = new Scanner(System.in);
    int inp = in.nextInt();
    System.out.println(Sum(inp));
}
public static int Sum(int n){
    if( n < 2) return 0;
    int sum = 0,div=2;
    while(n>div){
        if(n%div == 0){
            boolean flag = isPrime(div);
            if(flag) sum+=div;
        }
        div++;
    }
    return sum;
}
public static boolean isPrime(int n){
    int div = 2;
    while(n>div){
        if(n%div == 0) return false;
        div++;
    }
    return true;
}
```

```Java
public static void main(String[] args) {
    Scanner in = new Scanner(System.in);
    int No = in.nextInt();
    int times = in.nextInt();
    System.out.println(Sum(No,times));
}
public static int Sum(int no,int times){
    int sum = no;
    for(int i=1;i<times;i++){
        int value = no;
        for(int j=0;j<i;j++){
            value = (value*10)+no;
        }
        System.out.println(value);
        sum+=value;
    }
    return sum;
}
```

### Vowels or consonant

```C
#include <stdio.h>
#include<string.h>
#include<math.h>
#include<stdlib.h>

int main(){
    
    char ch;
    scanf("%c",&ch);
    
    int chV = ch;
    
    if(ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' || ch == 'A'|| ch == 'E'|| ch == 'I'|| ch == 'O'|| ch == 'U'){
        printf("Vowel");
    }else if((97 <= ch && ch <= 122) || (65 <= ch && ch <= 90)){
        printf("Consonant");
    }else{
        printf("Invalid");
    }

}
```

### Decimal to Octal and HexaDecimal

```C
#include <stdio.h>

int main() {
    int number;
    scanf("%d", &number);
    if (number < 0){
        printf("Error: Please enter a positive integer");
        return 0;
    }
    printf("%x\n", number);
    printf("%o\n", number);

    return 0;
}
```

### Area of Circle, Rectange and Triangle

```C
#include <stdio.h>
#include<string.h>

int main(){
    int sh;
    scanf("%d",&sh);
    
    if(sh == 1){
        float r;
        scanf("%f",&r);
        float ans = (22.0/7.0)*r*r;
        printf("%.2f",ans);
    }else if(sh == 2){
        float l,b;
        scanf("%f %f",&l,&b);
        float ans = l*b;
        printf("%.2f",ans);
    }else if(sh == 3){
        float l,b;
        scanf("%f %f",&l,&b);
        float ans = 0.5*(l*b);
        printf("%.2f",ans);
    }else {
        printf("Invalid");
    }
    
}
```


### Palindrome of a single number

```C
#include <stdio.h>

int main(){
    int n;
    scanf("%d",&n);
    int dup = n;
    int rev = 0;
    while(dup>0){
        int rem = dup%10;
        rev = (rev*10)+rem;
        dup= dup/10;
    }
    
    if(rev == n) printf("%d",1);
    else printf("%d",0);
    
}
```

### Find the sum of digits of a number and print only if the sum is less than 10,else sum again example(932=9+3+2 = 14(greater than 10),so 1+4=5(lesser than 10),thus 5 will be the output

```C
#include <stdio.h>
#include <string.h>

int main(){
    int n;
    scanf("%d",&n);
    
    int dup = n;
    int sum = 0;
    while(1){
        if(dup<=0){
            if(sum<10) break; 
            dup = sum;
            sum = 0;
        }
        int rem = dup%10;
        sum+=rem;
        dup/=10;
    }
    
    printf("%d",sum);
    
}


```

### LCM 

```C
#include <stdio.h>
#include <string.h>

int main(){
    int a,b;
    scanf("%d %d",&a,&b);
    
    int min = a>b ? b : a;
    
    while(1){
        if(min%a == 0 && min%b == 0){
            printf("%d",min);
            return 0;
        }
        min++;
    }
}
```

### GCD 
```C
#include <stdio.h>
#include <string.h>

int main(){
    int a,b;
    scanf("%d %d",&a,&b);
    
    int max = a>b ? a : b;
    
    while(1){
        if(a%max == 0 && b%max == 0){
            printf("%d",max);
            return 0;
        }
        max--;
    }
    
}
```

### Increment every digit by 1

```C
#include <stdio.h>

int main() {
    int n;
    scanf("%d",&n);
    
    int dup = n;
    int rev=0;
    
    while(dup>0){
        int rem = dup%10; rem++;
        rev = (rev*10)+rem;
        dup/=10;
    }
    
    dup = rev;
    int inc = 0;
    
    while(dup>0){
        int rem = dup%10;
        inc = (inc*10)+rem;
        dup/=10;
    }
    
    printf("%d",inc);
    
}
```

### Abundant number

```C
#include<stdio.h>

int main(){
    int n;
    scanf("%d",&n);
    
    int divi = 1;
    int sum = 0;
    
    while(n>divi){
        if(n%divi == 0){
            sum+=divi;
        }
        divi++;
    }
    if(sum>n) printf("Yes");
    else printf("No");
    
}
```

### Roman to Integer 

```C
#include<stdio.h>
#include<string.h>
int rtoi(char* roman){
    int Values[26];
    Values['I'-'A'] = 1;
    Values['V'-'A'] = 5;
    Values['X'-'A'] = 10;
    Values['L'-'A'] = 50;
    Values['C'-'A'] = 100;
    Values['D'-'A'] = 500;
    Values['M'-'A'] = 1000;
    
    int result = 0;
    int prev = 0;
    int length = strlen(roman);
    for(int i=length-1;i>=0;i--){
        int current = Values[roman[i]-'A'];
        if(current>=prev){
            result += current;
        }else{
            result -= current;
        }
    }
    return result;
}
int main(){
    char n[200];
    scanf("%s",&n);
    
    printf("%d",rtoi(n));
    
}
```

### Integer to Roman

```C
#include<stdio.h>
#include<string.h>

void itor(int num){
    int values[] = {1000,900,500,400,100,90,50,40,10,9,5,4,1};
    char *symbol[] = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
    
    char result[100];
    result[0] = '\0';
    
    for(int i=0;i<13;i++){
        while(num>=values[i]){
            strcat(result,symbol[i]);
            num-=values[i];
        }
    }
    printf("%s",result);
}
int main(){
    int n;
    scanf("%d",&n);
    
    itor(n);
    return 0;
}
```

### Sum of Factors

Ex : 12/2 -> 6/2 -> 3/3 -> 1 So , 2+2+3 -> 7

```C
#include <stdio.h>

int main() {
    int in;
    scanf("%d",&in);
    int sum=0;
    
    int dup = in;
    
    while(dup != 1){
        if(dup%2 == 0){
            sum+=2;
            dup/=2;
        }
        else{
            sum+=dup;
            return
        }
        
    }
    printf("%d",sum);
}
```

### [1822. Sign of the Product of an Array](https://leetcode.com/problems/sign-of-the-product-of-an-array/)

```Java
class Solution {
    public int arraySign(int[] nums) {
        int counter = 0;

        for(int i=0;i<nums.length;i++){
            if(nums[i] == 0) return 0;
            else if(nums[i] < 0) counter++;
        }

        if(counter%2 == 0) return 1;
        else return -1;

    }
}
```

###  [69. Sqrt(x)](https://leetcode.com/problems/sqrtx/)

```Java
class Solution {
    public int mySqrt(int x) {
        int ans = 1;
        int start=1,end=x;

        if(x == 0) return 0;
        
        while(start<=end){
            int mid = start+(end-start)/2;
            if(start == end){
                if(mid*mid > x) return mid-1;
            }
            if(mid*mid == x) return mid;
            if(mid*mid > x){
                ans = mid;
                end = mid-1;
            }
            if(mid*mid < x){
                ans = mid;
                start = start+1;
            }
        }
        return ans;

    }
}
```

### [168. Excel Sheet Column Title](https://leetcode.com/problems/excel-sheet-column-title/)

```Java
class Solution {
    public String convertToTitle(int n) {
        String s = "";

        while(n > 0){
            char ch = (char)((n-1)%26 + 65);

            n = (n-1) / 26;
            s = ch + s;
        }

        return s;
        
    }
}
```

### [412. Fizz Buzz](https://leetcode.com/problems/fizz-buzz)

```Java
class Solution {
    public List<String> fizzBuzz(int n) {
        
        List<String> ls = new ArrayList<>();
        for(int i=1;i<=n;i++){
            
            if(i%3 == 0 && i%5 == 0){   
                ls.add("FizzBuzz");
            }else if(i%3 == 0){
                ls.add("Fizz");
            }else if(i%5 == 0){
                ls.add("Buzz");
            }else{
                ls.add(Integer.toString(i));
            }
        }
        return ls;

    }
}
```

### [258. Add Digits](https://leetcode.com/problems/add-digits)

```Java
class Solution {
    public int addDigits(int num) {
        
        while(num>=10){
            int sum = 0;

            while(num>0){
                int rem = num%10;
                sum += rem;
                num/=10;
            }
            num = sum;
        }
        return num;
    }
}
```

### [202. Happy Number](https://leetcode.com/problems/happy-number/)

```Java
class Solution {
    public boolean isHappy(int n) {
        Set<Integer> st = new HashSet<>();

        while(n != 1){
            int sum = 0;
            while(n>0){
                int rem = n%10; rem*=rem;
                sum += rem;
                n/=10;
            }
            if(st.contains(sum)) return false;
            st.add(sum);
            n = sum;
        }
        return true;
    }
}
```

### [367. Valid Perfect Square](https://leetcode.com/problems/valid-perfect-square/)

```Java
class Solution {
    public boolean isPerfectSquare(int num) {
        int p2 = num,p1=1;

        while(p1<=p2){
            long mid = p1+(p2-p1)/2;
            long check = mid*mid;

            if(check == num) return true;
            else if(check > num){
                p2 = (int)mid-1;
            }else{
                p1 = (int)mid+1;
            }
        }
        return false;
    }
}
```

### [1716. Calculate Money in Leetcode Bank](https://leetcode.com/problems/calculate-money-in-leetcode-bank/)

```Java
	xclass Solution {
    public int totalMoney(int n) {
        
        int baseStart = 1;
        int res = 0;
        int count=0;
        for(int i=0;count<n;i++){
            int adder = baseStart;
            for(int j=0;j<7 && count<n;j++){
                res += adder;
                adder++; count++;
            }
            baseStart++;
        }
        return res;
    }
}
```

### [12. Integer to Roman](https://leetcode.com/problems/integer-to-roman/)

```Java
class Solution {
    public String intToRoman(int num) {
        
        StringBuilder sb = new StringBuilder();
        int[] no = {1000,900,500,400,100,90,50,40,10,9,5,4,1};
        String[] ch = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};

        for(int i=0;i<no.length;i++){
            while(num>=no[i]){
                sb.append(ch[i]);
                num -= no[i];
            }
        }
        return sb.toString();
    }
}
```

### [Geometric Problem : 1041. Robot Bounded In Circle](https://leetcode.com/problems/robot-bounded-in-circle/)

```Java
class Solution {
    public boolean isRobotBounded(String i) {
        int x = 0,y = 0;
        char[] chAr = {'N','S','E','W'};
        int p = 0;

        for(char ch : i.toCharArray()){

            if(ch == 'G'){
                if(chAr[p] == 'N') y+=1;
                else if(chAr[p] == 'S') y-=1;
                else if(chAr[p] == 'E') x+=1;
                else if(chAr[p] == 'W') x-=1;
            }else if(ch == 'L'){
                if(p == 0) p = 3;
                else if(p == 1) p = 2;
                else if(p == 2) p = 0;
                else if(p == 3) p = 1;
            }else if(ch == 'R'){
                if(p == 0) p = 2;
                else if(p == 1) p = 3;
                else if(p == 2) p = 1;
                else if(p == 3) p = 0;
            }
        }
        if(x == 0 && y == 0) return true;
        if(p == 0) return false;
        return true;
    }
}
```

### [171. Excel Sheet Column Number](https://leetcode.com/problems/excel-sheet-column-number/description/)

```Java
class Solution {
    public int titleToNumber(String columnTitle) {
        int i = 0;
        int ans = 0;
        for(int j=columnTitle.length()-1;j>=0;j--){
            int ch1 = (int)columnTitle.charAt(j)-'A';
            ans+=((int) Math.pow(26,i)*(ch1+1));
            i++;
        }
        return ans;
    }
}
```

### [2413. Smallest Even Multiple](https://leetcode.com/problems/smallest-even-multiple/description/)

```Java
class Solution {
    public int smallestEvenMultiple(int n) {
        return n%2 == 1 ? n*2 : n;
    }
}
```

### [1137. N-th Tribonacci Number](https://leetcode.com/problems/n-th-tribonacci-number/description/)

```Java
class Solution {
    public int tribonacci(int n) {
        if(n == 0) return 0;
        if(n == 1) return 1;
        if(n == 2) return 1;
        return func(n,0,1,1,3);
    }
    public int func(int n,int prevO,int prevT,int cur,int count){

        if(count == n) return prevO+prevT+cur;

        return func(n,prevT,cur,prevO+prevT+cur,count+1);
    }
}
```

### [Power of Two](https://leetcode.com/problems/power-of-two/description/)

```Java
class Solution {
    public boolean isPowerOfTwo(int n) {
        int p1 = 0,p2 = n;

        while(p1<=p2){
            int mid = (p1+p2)/2;
            double val = Math.pow(2,mid);

            if(val == n) return true;
            if(val < n) p1 = mid+1;
            else p2 = mid-1;
        }
        return false;
    }
}
```

### [3099. Harshad Number](https://leetcode.com/problems/harshad-number/description/)

```Java
class Solution {
    public int sumOfTheDigitsOfHarshadNumber(int x) {
        int dup = x;
        int val = 0;
        while(dup>0){
            int ld = dup%10; dup/=10;
            val += ld;
        }
        return x%val == 0 ? val : -1;
    }
}
```

### [Pow(x, n)](https://leetcode.com/problems/powx-n/)

```Java
class Solution {
    public double myPow(double x, int n) {
        return func(x,(long) n);
    }
    public double func(double x,long n){
        if(n == 0) return 1.00;
        if(n < 0){
            return 1.0/func(x,-n);
        }
        else{
            if(n%2 == 1){
                return x*func(x*x,(n-1)/2);
            }else{
                return func(x*x,n/2);
            }
        }
    }
}
```


### [Egg Drop With 2 Eggs and N Floors](https://leetcode.com/problems/egg-drop-with-2-eggs-and-n-floors/description/)

```Java
class Solution {
    public int twoEggDrop(int n) {
        int s = 0;
        for(int i=1;i<=n;i++){
            s+=i;
            if(s>=n) return i;
        }
        return -1;
    }
}
```

### [2523. Closest Prime Numbers in Range](https://leetcode.com/problems/closest-prime-numbers-in-range/description/)

```Java
class Solution {
    public int[] closestPrimes(int left, int right) {
        int no = -1;
        int min = Integer.MAX_VALUE;
        int[] ar = new int[2];

        for(int i=left;i<=right;i++){
            boolean prime = isPrime(i);

            if(prime && no == -1) no = i;
            else if(prime){
                int diff = i-no;
                if(diff<min){
                    min = diff;
                    ar[0] = no;
                    ar[1] = i;
                }
                no = i;
            }
        }
        return ar[0] == 0 && ar[1] == 0 ? new int[] {-1,-1} : ar;
    }
    public boolean isPrime(int n){
        
        if(n <= 1) return false;
        if(n == 2) return true;

        int i=2;
        for(i=i;i*i<=n;i++){
            if(n%i == 0) return false;
        }
        return true;
    }
}
```

### [650. 2 Keys Keyboard](https://leetcode.com/problems/2-keys-keyboard/description/)

```Java
class Solution {
    public int minSteps(int n) {
        if(isPrime(n)) {
            return n;
        }
        int res = 0;
        for(int i=2;n>1;i++){
            if(n%i == 0) {
                res+=i;
                n/=i;
                i=1;
            }
        }
        return res;
    }
    public boolean isPrime(int n){
        if(n <= 1) return false;
        int i;
        for(i=2;i*i<=n;i++){
            if(n%i == 0) return false;
        }
        return true;
    }
}
```

### [3Sum Closest](https://leetcode.com/problems/3sum-closest/description/)

```Java
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);

        int closeOne = Integer.MAX_VALUE;
        int res = 0;

        for(int i=0;i<nums.length-2;i++){
            int l = i+1,r= nums.length-1;
            while(l<r){

                int val = nums[i]+nums[l]+nums[r];
                if(Math.abs(val-target)<closeOne) {
                    closeOne = Math.abs(val-target);
                    res = val;
                }
                if(val > target) r--;
                else l++;
            }
        }
        return res;
    }
}class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);

        int closeOne = Integer.MAX_VALUE;
        int res = 0;

        for(int i=0;i<nums.length-2;i++){
            int l = i+1,r= nums.length-1;
            while(l<r){

                int val = nums[i]+nums[l]+nums[r];
                if(Math.abs(val-target)<closeOne) {
                    closeOne = Math.abs(val-target);
                    res = val;
                }
                if(val > target) r--;
                else l++;
            }
        }
        return res;
    }
}
```

### [4Sum](https://leetcode.com/problems/4sum/description/)

```Java
class Solution {
    public List<List<Integer>> fourSum(int[] nums, int target) {
        
        Arrays.sort(nums);
        List<List<Integer>> ls = new ArrayList<>();
        HashSet<List<Integer>> st = new HashSet<>();

        for(int i=0;i<nums.length-3;i++){
            for(int j=i+1;j<nums.length-2;j++){
                if(i == j) continue;
                int l = j+1,r = nums.length-1;
                while(l<r){
                    if(i == l || i == l) l++;
                    if(i == r || r == i) r--;
                    long val = (long)nums[l]+nums[r]+nums[i]+nums[j];
                    if(val > target){
                        r--;
                    }else if(val < target){
                        l++;
                    }
                    else if(val == target){
                        List<Integer> in = new ArrayList<>();
                        in.add(nums[i]);
                        in.add(nums[j]);
                        in.add(nums[l]);
                        in.add(nums[r]);
                        if(!st.contains(in)){
                            ls.add(in);
                            st.add(in);
                        }
                        st.add(in);
                        l++; r--;
                    }
                }
            }
        }
        return ls;
    }
}
```

### [342. Power of Four](https://leetcode.com/problems/power-of-four/description/)

```Java
class Solution {
    public boolean isPowerOfFour(int n) {
        for(int i=0;i<=n;i++){
            double val = Math.pow(4,i);
            if(val == n) return true;
            if(val > n) return false;
        }
        return false;
    }
}
```

### [1742. Maximum Number of Balls in a Box](https://leetcode.com/problems/maximum-number-of-balls-in-a-box/description/)

```Java
class Solution {
    public int countBalls(int lowLimit, int highLimit) {
        
        HashMap<Integer,Integer> mp = new HashMap<>();
        int max = 0;

        for(int i=lowLimit;i<=highLimit;i++){
            
            String s = String.valueOf(i);

            int val = 0;
            for(char ch : s.toCharArray()){
                val+= (Integer.parseInt(String.valueOf(ch)));
            }
            // System.out.println(i + " " + val);
            mp.put(val,mp.getOrDefault(val,0)+1);
            max = Math.max(max,mp.get(val));
        }

        return max;
    }
}
```

### [Find minimum number of currency notes and values that sum to given amount](https://www.geeksforgeeks.org/find-number-currency-notes-sum-upto-given-amount/)

```Java
import java.util.*;
public class MinimumCurrencyNote {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);

        int[] arr = {2000,500,200,100,50,20,10,5,1};
        int value = in.nextInt();

        for(int i=0;i<arr.length;i++){
            int count = 0;
            while(arr[i]<=value){
                value-=arr[i];
                count++;
            }
            if(count >= 1){
                System.out.println(arr[i]+" : "+count);
            }
        }
    }
}
```

```Java
import java.util.*;
public class MinimumCurrencyNote {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);

        int[] arr = {2000,500,200,100,50,20,10,5,1};
        int value = in.nextInt();

        for(int i=0;i<arr.length;i++){
            int count = 0;
            while(arr[i]<=value){
                value-=arr[i];
                count++;
            }
            if(count >= 1){
                System.out.println(arr[i]+" : "+count);
            }
        }
    }
}
```