
#### [Max Min in Array](https://www.geeksforgeeks.org/problems/find-minimum-and-maximum-element-in-an-array4428/1)

##### Find:
Return the max , min in the given long array
```Java
class Pair  
{  
    long first, second;  
    public Pair(long first, long second)  
    {  
        this.first = first;  
        this.second = second;  
    }  
} 

static Pair getMinMax(long a[], long n)  
    {
        long min = 9223372;
        long max = 0;
        for(int i=0;i<n;i++){
	        // Checks if it is Min Value
            if(min > a[i]){
                min = a[i];
            } // Checks if it is Max Value
            if(max < a[i]){
                max = a[i];
            }
        }
        return new Pair(min,max);
    }
```

#### [Third Largest Number in Array](https://practice.geeksforgeeks.org/problems/third-largest-element/1)

##### Find:
Return the third largest number in the given array
```Java
int thirdLargest(int a[], int n)
    {
        int max = Integer.MIN_VALUE;
        int max2 = Integer.MIN_VALUE;
        int result = Integer.MIN_VALUE;
        
        if(n < 3){
            return -1;
        }
        else if(n == 3){
            int min = 0;
            
            for(int i=0;i<n;i++){
                if(min > a[i]){
                  min = a[i];  
                }
            }
            return min;
        }
        // First Loop
        for(int i=0;i<n;i++){
            
            if(max < a[i]){
                max = a[i];
            }
            
        }
        // Second Loop
        for(int i=0;i<n;i++){
            
            if(max > a[i] && max2 < a[i]){
                max2 = a[i];
            }
            
        }
        // Third Loop
        for(int i=0;i<n;i++){
            
            if(max > a[i] && max2 > a[i] && result < a[i]){
                result = a[i];
            }
            
        }
        return result;
    }
```

- On the first if statement , we check whether the given array size is 3 , if not return -1 as we can't find the third largest number
- if the size is 3 , the minimum number of the given array must be the 3rd largest number of array
- The First loop find the Largest Element in the Array
- The Second loop find the 2nd Largest Element in the Array
- The Third loop find the 3rd Largest Element of the Array , which is the Answer

#### [Missing Number in the Array](https://practice.geeksforgeeks.org/problems/missing-number-in-array1416/1)

##### Find :
Find the missing Element in the given array

```Java
int missingNumber(int array[], int n) {
    
  int[] Hash = new int[n+1];
        
      for(int i=0;i<n-1;i++){
	    Hash[array[i]] = Hash[array[i]]+1;
	  }
        
      for(int i=1;i<=n;i++){
		if(Hash[i] == 0){
			return i;
		}
	  }
        
	  return -1;
}
```

##### Algorithm : 
- We create an Array named 'Hash' in size of N+1 and init every number with zero
- The size is n+1 because we are ignoring the index 0 
- On the first loop , we get the element of Input Array , and make the HashArray's element position increment by 1
- On the Second Loop , we check the Elements of Hash array , incase if the element is 0 that would be the Missing element