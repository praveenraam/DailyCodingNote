Topic No : 14
Next Topic : [[]]

Here we cover the Sorting algorithm that doesn't follows the Recursive algorithm 
## Bubble Sort 
##### Video [Link](https://youtu.be/F5MZyqRp_IM?si=ZsjYDrYvZIDq11gz)

- This is also called as sinking sort or Exchange sort
##### Algorithm 
- It is comparison sort method
- All the sorting Algorithm is a step by step process
- Different Algorithm has different steps

**Step 1 :** Get the First two elements and compare the both 
**Step 2 :** If they are not sorted , Swap them
**Step 3 :** Then take the next two elements and repeat the Process until no next element found

**After the First iteration the Unsorted array look like this** 
![[Pasted image 20240103114441.png]]
- After this iteration , the larger element come to the end of the Array

**Repeat the Step 1 to Step 3 once again which gives**
![[Pasted image 20240103114620.png]]
- After Second iteration , the second largest element comes to the second end 

**These Steps are continued till we get the Array Sorted , the Final answer will be sorted**

**Ans :** (1,2,3,4,5) 

##### Code 
```Java
public static int[] BubbleSort(int[] Array){  
    /* Here I is used as counter of Loop*/  
    for(int i=0;i<Array.length;i++){  
        boolean isSwapped = false;  
        /* J is to iterate the Value and compare both */  
        for(int j=1;j<Array.length-i;j++){  
            /* The condition is length -i because at end of each iteration of i , last 
            I th element are sorted */  
            if(Array[j-1] > Array[j]){  
                int Temp = Array[j-1];  
                Array[j-1] = Array[j];  
                Array[j] = Temp;  
                isSwapped = true; // Status of Swapping  
            }  
        }  
        /*If there is no Swapping, the array is sorted, So no need to run the Loop */  
        /* The False value remains same if there are no swappings */        
        if(!isSwapped) return Array; /* Not is used to Change the false to true to 
        return the Value */  
    }
    return Array;  
}
```

##### Complexity

**Time Complexity**  : O(n2)
**Space Complexity** : O(1)
**Stable Algorithm**  : Yes

## Selection Sort 
##### Video [Link](https://youtu.be/Nd4SCCIHFWk?si=3fZUt8cl78W3iie6)
- This performs well on the small Arrays 
##### Algorithm 
- Find the Max element in the Array
- Swap the Max element to last index of Array with Max Element's current index
- Ignore the Sorted element's index and repeat it until it is sorted
##### Code 
With Separate functions
```Java
public static int[] SelectionSort(int[] Array){  
    for(int i=0;i<Array.length;i++){  
        /* Finding the Max element in the array */  
        int last = Array.length - i -1 ;  
        int Max = GetMaxIndex(Array,last);  
        /* Swaps the Max element to end */  
        Swapper(Array,Max,last);  
    }  
    return Array;  
}  
static int GetMaxIndex(int[] Array,int LastIndex){  
    int Max = 0;  
    for(int i=1;i<=LastIndex;i++){  
        if(Array[i] > Array[Max]){  
            Max = i;  
        }  
    }  
    return Max;  
}  
static void Swapper(int[] Array, int From , int To){  
    int temp = Array[From];  
    Array[From] = Array[To];  
    Array[To] = temp;  
}
```
Without separate Functions
```Java
static int[] Searcher(int[] arr){  
    for(int i=0;i<arr.length;i++){  
        /* Assuming the Max element's index as 0 */  
        int MaxIndex = 0;  
        /*Finding the Max Element's Index */  
        for(int j=1;j<arr.length-i;j++){  
            if(arr[j] > arr[MaxIndex]){  
                MaxIndex = j;  
            }  
        } /* The sorted element should be ignored */  
        int last = arr.length - i - 1;  
        /* Swapping done through temp Variable */  
        int temp = arr[MaxIndex];  
        arr[MaxIndex] = arr[last];  
        arr[last] = temp;  
    }  
    return arr;  
}
```

##### Complexity

**Time Complexity  :** O(n2)
**Space Complexity :** O(1)
**Stable Algorithm  :** No

## Insertion Sort
##### Video [Link](https://youtu.be/By_5-RRqVeE?si=PTWgbwANfsAp6PAq)
- Takes part in the Hybrid sorting Algorithms
- Used for smaller value of N => work
##### Algorithm
- Take an element , compare with elements in the left side 
- If the element is smaller swap both the element and continue comparing to the next element in the left side 
- else break the loop and pick the next element and repeat the procedure
##### Code 
```Java
static int[] InsertionSort(int[] Array){  
    for(int i=0;i<Array.length-1;i++){  
        for(int j=i+1;j>0;j--){  
            if(Array[j-1] > Array[j]){  
                Swap(Array,j-1,j);  
            }else{  
                break;  
            }  
        }  
    }  
    return Array;  
}
static void Swap(int[] Array, int From , int To){  
    int temp = Array[From];  
    Array[From] = Array[To];  
    Array[To] = temp;  
}
```
##### Complexity 

**Time Complexity**  : O(n2) --> Worst Case , O(n-1) --> Best Case
**Space Complexity** : O(n)
**Stable Algorithm**  : Yes

## Cyclic Sort
##### Video [Link](https://youtu.be/JfinxytTYFQ?si=BFyzULTsQA9XcEhZ)
##### When the given problem is ==1 to N== => We use Cyclic sort

##### Algorithm 
- The numbers are always 1 to N only
- In this case , taking any number between 1 to N , the element M should be placed in the position M-1 , 
- For example , taking 10 that should be placed in the 9th index
##### Code 
```Java
static int[] CyclicSort(int[] Array){  
    int i=0;  
    while (i < Array.length){  
        int correct = Array[i]-1;  
        if(Array[i] != Array[correct]) Swap(Array,i,correct);  
        else i++;  
    }  
    return Array;  
}  
static void Swap(int[] Array, int from , int to){  
    int temp = Array[from];  
    Array[from] = Array[to];  
    Array[to] = temp;  
}
```

##### Complexity

**Time Complexity**  : O(n)
**Space Complexity** : O(1)