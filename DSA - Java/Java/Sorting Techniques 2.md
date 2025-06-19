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

```Java
import java.util.Arrays;  
  
public class MergeSort {  
  
    public static void main(String[] args) {  
        int[] arr = {1,5,3,66,4,3,6,7,266,34,6,677,8,898,4553};  
  
        System.out.println("Before Merge sort : "+ Arrays.toString(arr));  
        mergeSort(arr,0,arr.length-1);  
        System.out.println("After Merge sort : "+ Arrays.toString(arr));  
  
    }  
  
    private static void mergeSort(int[] arr,int l,int r){  
        if(l<r){  
            int mid = l+(r-l)/2;  
  
            mergeSort(arr,l,mid);  
            mergeSort(arr,mid+1,r);  
  
            mergeSortedArrays(arr,l,mid,r);  
        }  
    }  
  
    public static void mergeSortedArrays(int[] arr,int l,int mid,int r){  
  
        int n1 = mid-l+1;  
        int n2 = r-mid;  
  
        int[] L = new int[n1];  
        int[] R = new int[n2];  
  
        for(int iter=0;iter<n1;iter++){  
            L[iter] = arr[l+iter];  
        }  
  
        for(int iter=0;iter<n2;iter++){  
            R[iter] = arr[mid+1+iter];  
        }  
  
        int i = 0, j = 0;  
        int iter = l;  
        while(i<L.length && j<R.length){  
  
            if(L[i] <= R[j]){  
                arr[iter] = L[i++];  
            }  
            else arr[iter] = R[j++];  
  
            iter++;  
        }  
  
        while(i<L.length){  
            arr[iter++] = L[i++];  
        }  
        while(j<R.length){  
            arr[iter++] = R[j++];  
        }  
  
    }  
  
}
```
#### Time and Space
**Time Complexity** : O(N * log(N))
**Space Complexity** : O(N)

## Quick Sort
