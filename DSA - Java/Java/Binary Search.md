Video [Link](https://youtu.be/f6UU7V3szVw?si=PSFFgjbJ5F3FDt8N)
Topic No 13
Next Topic [[]]


The binary search can be implemented only in the sorted array(Ascending or Descending)
Ex : 
``int[] ArrAscending = {2,3,4,5,6,8}
``int[] ArrDescending = {9,8,7,6,5,4}``

### ==Sorted Array , then only Binary Search==
## Algorithm 

For a binary search to work, it is mandatory for the target array to be sorted. We shall learn the process of binary search with a pictorial example. The following is our sorted array and let us assume that we need to search the location of value 31 using binary search.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_0.jpg)

First, we shall determine half of the array by using this formula −

mid = low + (high - low) / 2

Here it is, 0 + (9 - 0 ) / 2 = 4 (integer value of 4.5). So, 4 is the mid of the array.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_1.jpg)

Now we compare the value stored at location 4, with the value being searched, i.e. 31. We find that the value at location 4 is 27, which is not a match. As the value is greater than 27 and we have a sorted array, so we also know that the target value must be in the upper portion of the array.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_2.jpg)

We change our low to mid + 1 and find the new mid value again.

low = mid + 1
mid = low + (high - low) / 2

Our new mid is 7 now. We compare the value stored at location 7 with our target value 31.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_3.jpg)

The value stored at location 7 is not a match, rather it is more than what we are looking for. So, the value must be in the lower part from this location.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_4.jpg)

Hence, we calculate the mid again. This time it is 5.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_5.jpg)

We compare the value stored at location 5 with our target value. We find that it is a match.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_6.jpg)

We conclude that the target value 31 is stored at location 5.

Binary search halves the searchable items and thus reduces the count of comparisons to be made to very less numbers.

## Code 

```Java
public class BinarySearch {  
    public static void main(String[] args) {  
        int[] InpArray = {5000 , 200 , 150 , 20 , 17 , 12 , 10 , 8 , 5};  
        System.out.println(IncDec(InpArray,200));  
    }  
    static int IncDec(int[] Array,int Target){  
        if( Array[0] < Array[Array.length-1] ) {  
            System.out.println("Increasing");  
            return IncSearcher(Array,Target);  
        } else {  
            System.out.println("Decreasing");  
            return DecSearcher(Array,Target);  
        }  
    }  
```

``` Java
    static int IncSearcher(int[] Array,int target){  
        int Start = 0;  
        int End = Array.length-1;  
        int MiddleElement = Start+End/2;  
        while(Start <= End){  
            /* MiddleElement = Start + (End-Start) / 2 : This Should be Executed  
            to avoid at all the cases */            
            MiddleElement = (Start+End)/2;  
            if(Array[MiddleElement] == target ){  
                return MiddleElement; // Answer Found  
            }else if(Array[MiddleElement] > target){  
                End = MiddleElement-1;  
            }else if(Array[MiddleElement] < target){  
                Start = MiddleElement+1;  
            }  
        }  
        return -1;  
    }  
```

``` Java
    static int DecSearcher(int[] Array,int target){  
        int start = 0;  
        int end = Array.length;  
        int MiddleElement = (start+end)/2;  
        while(start <= end){  
            /* MiddleElement = Start + (End-Start) / 2 : This Should be Executed  
            to avoid at all the cases */           
            MiddleElement = (start+end)/2;  
            if(Array[MiddleElement] == target){  
                return MiddleElement;  
            }else if(Array[MiddleElement] > target){  
                start = MiddleElement+1;  
            }else if(Array[MiddleElement] < target){  
                end = MiddleElement-1;  
            }  
        }  
        return -1;  
    }  
}
```


## 2D Arrays (Matrix)

### Video [Link](https://youtu.be/enI_KyGLYPo?si=RSLGaFpdOrtq8nR8)

### Algorithm 
- First we check the last element of the first row , So we declare the row as 0 and column as Length -1 
- If the target is equal to the current element we return it
- Else we check it is greater or lesser then the target element
- Incase current element is greater , we decrease the column by 1
- Incase current element is lesser , we increase the row by 1
- We do this in a loop until we find the target element 
- The condition for the loop is once the row is greater than the Matrix length or Column is less than 1 , it exits
### Code
```Java
static int[] SearchRowCol(int[][] Matrix,int target){  
    int row = 0;  
    int column = Matrix.length-1;  
  
    while(row < Matrix.length && column >=0){  
        if(Matrix[row][column] == target){  
            return new int[]{row,column};  
        }else if(target > Matrix[row][column] ){  
            row++;  
        }else {  
            column--;  
        }  
    }  
    return new int[] {-1,-1};  
}
```
