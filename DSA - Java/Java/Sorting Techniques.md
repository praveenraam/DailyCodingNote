Topic No : 14
Next Topic : [[]]

Here we cover the Sorting algorithm that doesn't follows the Recursive algorithm 
## Bubble Sorting 
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

**Repeat the Step 1 to Step 3 once again which gives 
![[Pasted image 20240103114620.png]]
- After Second iteration , the second largest element comes to the second end 

**These Steps are continued till we get the Array Sorted , the Final answer will be sorted**

**Ans :** (1,2,3,4,5) 

##### Code 
```Java
public static int[] BubbleSorting(int[] Array){  
    /* Here I is used as counter of Loop*/  
    for(int i=0;i<Array.length;i++){  
        boolean isSwapped = false;  
        /* J is to iterate the Value and comapre both */  
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

