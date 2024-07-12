

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

### 