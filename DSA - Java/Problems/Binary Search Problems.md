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

