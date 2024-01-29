
### [ 1 to N Without Loop](https://www.codingninjas.com/studio/problems/print-1-to-n_628290?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)

```Java
public class Solution {
    public static int[] printNos(int x) {
        int[] array = new int[x];
        Solution(array,x);
        return array;
    }
    public static void Solution(int[] array,int x){
        if(x<1) return;
        array[x-1] = x;
        Solution(array,x-1);
        return;
    }
}
```

### [Print n times](https://www.codingninjas.com/studio/problems/-print-n-times_8380707?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)

```Java
import java.io.*;
import java.util.*;
public class Solution {
    public static List<String> printNtimes(int n){
        ArrayList<String> result = new ArrayList<>();
        printer(n,result);
        return result;
    }
    public static void printer(int n,List<String> result){
        if(n == 0) return;
        printer(n-1,result);
        result.add("Coding Ninjas");
    };
}
```

### [1 to N without loop](https://www.codingninjas.com/studio/problems/print-1-to-n_628290?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)

```Java
public class Solution {
    public static int[] printNos(int x) {
        int[] array = new int[x];
        Solution(array,x);
        return array;
    }
    public static void Solution(int[] array,int x){
        if(x<1) return;
        array[x-1] = x;
        Solution(array,x-1);
        return;
    }
}
```

### [ N to 1 without loop](https://www.codingninjas.com/studio/problems/n-to-1-without-loop_8357243?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)

```Java
public class Solution
{
    public static int[] printNos(int x) {
        int[] arr = new int[x];
        solution(x,arr,0);
        return arr;
    }
    public static void solution(int x,int[] arr,int counter){
        if(x == 0) return;
        arr[counter] = x;
        solution(x-1,arr,counter+1);
    }
}
```

### [ Sum Of First N Numbers](https://www.codingninjas.com/studio/problems/sum-of-first-n-numbers_8876068?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)

```Java
public class Solution {
    public static long sumFirstN(long n) {
        if(n==1) return n;
        return sumFirstN(n-1)+n;
    }
}
```

### [ Reverse an Array](https://www.codingninjas.com/studio/problems/reverse-an-array_8365444?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)

```Java
public class Solution {
    public static int[] reverseArray(int n, int[] arr) {
        Solution(0,arr,n);
        return arr;
    }

    public static void Solution(int counter , int[] arr,int n){
        if(counter >=  n/2) return;
        swap(counter,n-counter-1,arr);
        Solution(counter+1,arr,n);
    }

    public static void swap(int from,int to,int[] arr){
        int temp = arr[from];
        arr[from] = arr[to];
        arr[to] = temp;
    }
}
```

### [Check Palindrome (recursive)](https://www.codingninjas.com/studio/problems/check-palindrome-recursive_624386?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)

```Java
public class Solution {
    public static boolean isPalindrome(String str) {
        for(int i=0;i<str.length()/2;i++){
           if( str.charAt(i) != str.charAt(str.length() - 1- i)) return false;
        }
        return true;
    }
}
```

