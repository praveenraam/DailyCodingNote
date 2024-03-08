Video [Link](https://youtu.be/W9QJ8HaRvJQ?si=R_fkcRuJBWlZGVC_)

### Problem 1 : Ceiling of a Number

##### Find : 
You need to return the target value index or if target doesn't found return the next greatest number index of the target value

The solution is very similar to the Binary Search coding , where you will return the ==Start value== instead of -1 incase if you fail to find the exact target value in the Array

##### Solution :
```Java
public class CeilingNumber {  
    public static void main(String[] args) {  
        int[] Array = {10,13,17,18,20,25,45};  
        System.out.println(Solution(Array,19));  
    }  
    static int Solution(int[] Array,int target){  
         int start = 0;  
         int end = Array.length-1;  
         int Mid = (start+end) /2;  
         
         while(start <= end){  
             Mid = (start+end)/2;  
             if(Array[Mid] == target){  
                 return Mid;  
             }else if(Array[Mid] > target){  
                 end = Mid-1;  
             }else if(Array[Mid] < target){  
                 start = Mid+1;  
             }  
         }  
         return start;  
    }  
} // Out = 4
```

### Problem 2 : Floor of a Number
##### Find : 
You need to return the target value index or if target doesn't found return the next smaller number index of the target value

This solution is also similar to the Binary Search Coding , where you will return the ==End Value== instead of -1 incase if you fail to find the exact target value in the Array

##### Solution : 
```Java
public class FloorNumber {  
    public static void main(String[] args) {  
        int[] Array = {10,13,17,28,20,25,45};  
        System.out.println(Solution(Array,20));  
    }  
    static int Solution(int[] Array,int target){  
        int start = 0;  
        int end = Array.length -1;  
        int mid = (start+end)/2;  
  
        while(start<=end){  
            mid = (start+end)/2;  
            if(Array[mid] == target){  
                return mid;  
            }else if (Array[mid] > target){  
                end = mid-1;  
            }else if (Array[mid] < target){  
                start = mid +1;  
            }  
        }  
        return end;  
    }  
} // Out = 2
```

### Problem 3 :  Smallest Letter 

##### Find : 
You need to return the smallest larger value than the given target value but the value are alphabets

##### Solution :
```Java
public class SmallLetter {  
    public static void main(String[] args) {  
        char[] Array = {'c','j','m','o'};  
        System.out.println(Solution(Array,'o'));  
    }  
    static char Solution(char[] Array,char target){  
        int start = 0;  
        int end = Array.length -1;  
        int mid;  
        while(start <= end){  
            mid = (start+end)/2;  
            if(Array[mid] > target){  
                end = mid-1;  
            }else {  
                start = mid+1;  
            }  
        }  
        if(start == Array.length) {  
            return Array[0];  
        }  
        return Array[start];  
    }  
} // Out = 7
```

### Problem 4 : 
##### Find :
You need to the return the start and end index of the target value in the given sorted array


### Problem 5 :

##### Find :
Find the index of the target element in a infinity sorted Array

```Java
import java.util.Arrays;  
  
public class InfiniteArray {  
    public static void main(String[] args){  
        int[] InpArray = {9,12,14,16,18,19,23,26,28,31,35,38,39,40,45,48,50,67,69,78};  
        System.out.println(Solution(InpArray,45));  
    }  
    static int Solution(int[] Array,int target){  
        int Start = 0;  
        int End = 1;  
        while(target > Array[End]){  
            int temp = End + 1;  
            End = End + (End - Start + 1)*2;  
            Start = temp;  
        }  
        return Searcher(Start, End ,Array, target);  
    }  
    static int Searcher(int start,int end , int[] array, int target){  
        while(start <= end){  
            int MiddleElement = (start +end)/2;  
            if(array[MiddleElement] == target){  
                return MiddleElement;  
            }else if(target < array[MiddleElement]){  
                end = MiddleElement-1;  
            }else if(array[MiddleElement] < target){  
                start = MiddleElement+1;  
            }  
        }  
        return -1;  
    }  
}
```

### [Implement Lower Bound](https://takeuforward.org/arrays/implement-lower-bound-bs-2/)

```Java
public class Solution {
    public static int lowerBound(int []arr, int n, int x) {
        int start = 0;
        int end = n-1;
        int ans=0;
        while(start <= end){
            int mid = (start+end)/2;
            if(arr[mid] >= x ) {
                ans = mid;
                end=mid-1;
            }else start = mid+1;
        }
        if(x>=n && ans==0) ans=x;
        return ans;
    }
}
```

### [Implement Upper Bound](https://takeuforward.org/arrays/implement-upper-bound/)

```Java
public class Solution {
    public static int upperBound(int []arr, int x, int n){
        int start =0;
        int end = n-1;
        int ans =0;
        while(start<=end){
            int mid = (start+end)/2;
            if(arr[mid] == x) {
                ans= mid+1;
                start = mid+1; 
            }
            else if(arr[mid] < x) start=mid+1;
            else{
                ans = mid;
                end = mid-1;
            }
        }
        return ans;
    }
}
```

### [Search Insert Position](https://www.codingninjas.com/studio/problems/algorithm-to-find-best-insert-position-in-sorted-array_839813?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)

```Java
public class Solution {
    public static int searchInsert(int [] arr, int m){
        if(arr.length == 0) return 0;
        if (m>arr[arr.length-1]) return arr.length;
        else if(m<arr[0]) return 0;
        int start = 0,end=arr.length-1;
        while(start<=end){
            int mid = (start+end)/2;
            if(arr[mid] == m) return mid;
            if(arr[mid] > m && arr[mid-1] < m ) return mid;
            else if(arr[mid] > m) {
                end = mid-1;
            }
            else if(arr[mid] < m) {
                start=mid+1;
            }
        }
        return -1;
    }
}
```

### [Ceil The Floor](https://www.codingninjas.com/studio/problems/ceiling-in-a-sorted-array_1825401?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)
```Java
import java.util.* ;
import java.io.*; 
public class Solution {
    public static int[] getFloorAndCeil(int[] a, int n, int x) {
        int floor = -1;
        int ceiling = -1;
        int start = 0,end = n-1;
        while(start<=end){
            int mid = start+(end-start)/2;
            if(a[mid] == x) return new int[] {x,x};
            else if(a[mid] < x){
                start = mid+1;
                floor = a[mid];
            }else if(a[mid] > x){
                end = mid-1;
                ceiling = a[mid];
            }
        }
        return new int[] {floor,ceiling};
    }
}
```

### [Number of Ocuurance in an sorted array](https://www.codingninjas.com/studio/problems/occurrence-of-x-in-a-sorted-array_630456?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
```Java
public class Solution {
    public static int count(int arr[], int n, int x) {
        int Last = Last(arr,n,x);
        int first = First(arr,n,x);
        if(first == -1) return 0;
        return Last-first;
    }
    public static int First(int arr[],int n,int x){
        int start =0,end=n-1,ans=-1;
        while(start<=end){
            int mid = start+(end-start)/2;
            if(arr[mid] == x){
                ans = mid;
                end = mid-1;
            }else if(arr[mid] < x){
                start = mid+1;
            }else if(arr[mid] > x){
                end = mid-1;
            }
        }
        return ans;
    }
    public static int Last(int arr[],int n,int x){
        int start=0,end=n-1,ans=n;
        while(start<=end){
            int mid = start+(end-start)/2;
                if(arr[mid] == x){
                    start = mid+1;
                }else if(arr[mid] > x){
                    end = mid-1;
                    ans = mid; 
                }else if(arr[mid] < x){
                    start = mid+1;
                }
        }
        return ans;
    }
}
```

### [First and Last Position of an Element In Sorted Array](https://www.codingninjas.com/studio/problems/first-and-last-position-of-an-element-in-sorted-array_1082549?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)

```Java
import java.util.* ;
import java.io.*; 
public class Solution {

    public static int[] firstAndLastPosition(ArrayList<Integer> arr, int n, int k) {
        int first = First(arr,n,k);
        int last = Last(arr,n,k);
        return new int[] {first,last};
    }
    public static int First(ArrayList<Integer> arr,int n,int k){
        int start = 0,end=n-1,ans=-1;
        while(start<=end){
            int mid = start+(end-start)/2;
            if(arr.get(mid) == k){
                ans = mid;
                end = mid-1;
            }else if(arr.get(mid) > k){
                end = mid-1;
            }else if(arr.get(mid) < k){
                start = mid+1;
            }
        }
        return ans;
    }
    public static int Last(ArrayList<Integer> arr,int n,int k){
        int start=0,end=n-1,ans=-1;
        while(start<=end){
            int mid = start+(end-start)/2;
            if(arr.get(mid) == k){
                ans = mid;
                start=mid+1;
            }else if(arr.get(mid) > k){
                end = mid-1;
            }else if (arr.get(mid) < k){
                start = mid+1;
            }
        }
        return ans;
    }
}
```
