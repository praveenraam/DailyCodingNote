Video [Link](https://youtu.be/ogjf7ORKfd8?si=7lV15PsqbVDPTZpo)
## Merge sort 

#### Why merge sort 
- While already read sorting techniques are taking O(n^2) , this has less time complexity than the other 

**Merge sort means divide and merge**

#### Algorithm 

- Divide the given array into two array 
- Further , divide those arrays
- Incase if there are odd number of elements , follow dividing 1st array have greater element and second having less element till the completion else vice versa
- Divide until making every element single number 
- ![[Pasted image 20240131085426.png]]

- Start merging them in the sorted way
- ![[Pasted image 20240131085936.png]]
#### Code
```Java
public static void BubbleSort(int[] arr,int low,int high){  
    if(low>=high) return;  
    int mid = (low+high)/2;  
  
    BubbleSort(arr,low,mid);  
    BubbleSort(arr,mid+1,high);  
  
    MergeFunc(arr,low,mid,high);  
  
}  
public static void MergeFunc(int[] arr,int low,int mid,int high){  
    int[] temp = new int[high-low+1];  
    int counter = 0;  
    int left = low;  
    int right = mid+1;  
    while(left<=mid && right<=high){  
        if(arr[left] <= arr[right]){  
            temp[counter] = arr[left];  
            left++;  
        }else {  
            temp[counter] = arr[right];  
            right++; 
        }  counter++;
    }  
    while(left<=mid){  
        temp[counter] = arr[left];  
        left++; counter++;  
    }  
    while(right<=high){  
        temp[counter] = arr[right];  
        right++; counter++;  
    }  
    for(int i=low;i<=high;i++){  
        arr[i] = temp[i-low];  
    }  
}
```

#### Time and Space
**Time Complexity** : O(N * log(N))
**Space Complexity** : O(N)


## Quick Sort