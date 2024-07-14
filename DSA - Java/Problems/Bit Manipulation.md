

### Swap Two Numbers

Regularly we use temp variable to swap two numbers,

```C
int main(){
	int a=5,b=6;
	
	int temp = a;
	a = b;
	b = temp;
	
	printf("%d %d",a,b);
}
```

To remove the extra variable and swap we use XOR operator

```Java
class HelloWorld {
    public static void main(String[] args) {
        
        int a = 10;
        int b = 12;
        
        a = a ^ b;
        b = a ^ b;
        a = a ^ b;
        
        System.out.println("a = "+a+", b = " + b);       
    }
}
```

`` Output : a = 12, b = 10`` 

### [K-th Bit is Set or Not](https://www.geeksforgeeks.org/problems/check-whether-k-th-bit-is-set-or-not-1587115620/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=bottom_sticky_on_article)

```Java
class CheckBit {
    // Function to check if Kth bit is set or not.
    static boolean checkKthBit(int n, int k) {
        
        n = n >> k;
        n = n & 1;
        
        return n == 1;
    }
}
```

### [Set kth bit](https://www.geeksforgeeks.org/problems/set-kth-bit3724/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=bottom_sticky_on_article)

```Java
class Solution{
    static int setKthBit(int N,int K){
        return N | (1 << K);
    }
}
```

### [Clear the ith Bit](https://takeuforward.org/bit-manipulation/clear-the-ith-bit)

```Java
class Solution {
    public static int clearSet(int N,int K){
        return N & ~(1 << K);   
    }
}
```

### [191. Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)

```Java
class Solution {
    public int hammingWeight(int n) {
        
        int count=0;
        while(n != 0){
            int no = n & 1;
            if(no == 1) count++;
            n = n >> 1;
        }
        return count;
    }
}
```

### [2859. Sum of Values at Indices With K Set Bits](2859. Sum of Values at Indices With K Set Bits)

```Java
class Solution {
    public int sumIndicesWithKSetBits(List<Integer> nums, int k) {
        
        int res = 0;
        for(int i=0;i<nums.size();i++){

            int n = i;
            int c = 0;
            while(n!=0){
                if((n&1) == 1) c++;
                n>>=1;
            }
            if(c == k) res+=nums.get(i);
        }
        return res;
    }
}
```

### [136. Single Number](https://leetcode.com/problems/single-number/description/)

```Java
class Solution {
    public int singleNumber(int[] nums) {
        int n = nums[0];

        for(int i=1;i<nums.length;i++){
            n^=nums[i];
        }
        return n;
    }
}
```

### [268. Missing Number](https://leetcode.com/problems/missing-number/)

```Java
class Solution {
    public int missingNumber(int[] nums) {
        int n=0,i;
        for(i=0;i<nums.length;i++){
            n = n ^ (nums[i] ^ i);
        }
        return n^i;
    }
}
```