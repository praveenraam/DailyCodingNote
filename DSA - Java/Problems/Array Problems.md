#### [1929. Concatenation of Array](https://leetcode.com/problems/concatenation-of-array/)

```Java
class Solution {
    public int[] getConcatenation(int[] nums) {
        int length = nums.length;
        int[] NewArray = new int[length*2];
        for(int i=0;i<length;i++){
            NewArray[i] = nums[i];
        } int i =0;
        for(int j=length;j<(length*2);j++){
            NewArray[j] = nums[i];
            i++;
        }
        return NewArray;
    }
}
```

#### [1920. Build Array from Permutation](https://leetcode.com/problems/build-array-from-permutation/)

```Java
class Solution {
    public int[] buildArray(int[] nums) {
        int ans[] = new int[nums.length];
        for(int i=0;i<nums.length;i++){
            ans[i] = nums[nums[i]];
        }
        return ans;
    }
}
```

#### [1480. Running sum of 1D Array](https://leetcode.com/problems/running-sum-of-1d-array/submissions/)

```Java
class Solution {
    public int[] runningSum(int[] nums) {
        int total = 0;
        for(int i=0;i<nums.length;i++){
            total+=nums[i];
            nums[i] = total;
        }
        return nums;
    }
}
```

#### [Richest Customer wealth](https://leetcode.com/problems/richest-customer-wealth/submissions/)

```Java
class Solution {
    public int maximumWealth(int[][] accounts) {
        int max=0;
        for(int i=0;i<accounts.length;i++){
            int total = 0;
            for(int j=0;j<accounts[i].length;j++){
                total+=accounts[i][j];
                if(total > max){
                    max = total;
                }
            }
        }
        return max;
    }
}
```

#### [Shuffle the Array](https://leetcode.com/problems/shuffle-the-array/)

```Java
class Solution {
    public int[] shuffle(int[] nums, int n) {
        int[] Answer = new int[n*2];
        int count=0;
        for(int i=0;i<nums.length;i++){
            Answer[i] = nums[i-count];
            Answer[i+1] = nums[n];
            n++;
            i++;
            count++;
        }
        return Answer;
    }
}
```

#### [1431. Kids With the Greatest Number of Candies](https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/)

```Java
class Solution {
    public List<Boolean> kidsWithCandies(int[] candies, int extraCandies) {
        List<Boolean> li=new ArrayList<>();
        int total;
        int Largest = LargestNum(candies);
        for(int i=0;i<candies.length;i++){
            total = candies[i] + extraCandies;
            if(Largest <= total){
                li.add(true);
            }else{
                li.add(false);
            }
        }
        return li;
    }
    public int LargestNum(int[] ArrayInp){
        int max = ArrayInp[0];
        for(int i=1;i<ArrayInp.length;i++){
            if(max < ArrayInp[i]){
                max = ArrayInp[i];
            }
        }
        return max;
    }
}
```
##### Coded without reading algorithm
```Java
class Solution {
    public List<Boolean> kidsWithCandies(int[] candies, int extraCandies) {
        List<Boolean> li=new ArrayList<>();
        int total;
        for(int i=0;i<candies.length;i++){
            total = candies[i]+extraCandies;
            for(int j=0;j<candies.length;j++){
                if(total < candies[j]){
                    li.add(false);
                    break;
                }else{
                    if(j==candies.length -1 ){
                        li.add(true);
                    }
                }
            }
        }
        return li;
    }
}
```

#### [1512. Number of Good Pairs](https://leetcode.com/problems/number-of-good-pairs/)

```Java
class Solution {
    public int numIdenticalPairs(int[] nums) {
        int Count=0;
        for(int i=0;i<nums.length;i++){
            for(int j=i+1;j<nums.length;j++){
                if(nums[i] == nums[j]){
                    Count++;
                }
            }
        }
        return Count;
    }
}
```

#### [1512. Number of Good Pairs](https://leetcode.com/problems/number-of-good-pairs/)

```Java
class Solution {
    public int[] smallerNumbersThanCurrent(int[] nums) {
        int[] ResultArr = new int[nums.length];
        for(int i=0;i<nums.length;i++){
            int count = 0;
            for(int j=0;j<nums.length;j++){
                if(nums[i] > nums[j]){
                    count++;
                }
            }
            ResultArr[i] = count;
        }
        return ResultArr;
    }
}
```

#### [268. Missing Number](https://leetcode.com/problems/missing-number/solutions/)

```Java
class Solution {  
    static int missingNumber(int[] nums) {  
        int i=0;  
        while(i<nums.length){  
            int correct = nums[i];  
            if(nums[i] < nums.length && nums[i] != nums[correct]){  
                int temp = nums[i];  
                nums[i] = nums[correct];  
                nums[correct] = temp;  
            }else i++;  
        }  
        for(i=0;i<nums.length;i++){  
            if(nums[i] != i){  
                return i;  
            }  
        }  
        return nums.length;  
    }  
}
```

#### [Check if two arrays are equal or not](https://www.geeksforgeeks.org/problems/check-if-two-arrays-are-equal-or-not3847/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=bottom_sticky_on_article)

```Java
public static boolean check(long A[],long B[],int N)
    {
	    Arrays.sort(A);
        Arrays.sort(B);
        for(int i=0;i<N;i++){
            if(A[i] != B[i]){
                return false;
            }
        }
        return true;
    }
```

#### [Rotate the array by 1](https://www.geeksforgeeks.org/problems/cyclically-rotate-an-array-by-one2614/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=bottom_sticky_on_article)

```Java
public void rotate(int arr[], int n){   
	for(int i=0;i<n-1;i++){
		int temp = arr[0];
		arr[0] = arr[i+1];
		arr[i+1] = temp;
	}
}
```

#### [Array Subset of another array](https://www.geeksforgeeks.org/problems/array-subset-of-another-array2317/1)

```Java
public String isSubset( long a1[], long a2[], long n, long m) {
        Arrays.sort(a1);
        Arrays.sort(a2);
        for(int i=0;i<m;i++){
            boolean exist = false;
            for(int j=0;j<n;j++){
                if(a2[i] == a1[j]){
                    a1[j] = 0;
                    exist = true;
                    break;
                }
            }
            if(!exist) return "No";
        }
        return "Yes";
    }
```

#### [Frequencies of Limited Range Array Elements](https://www.geeksforgeeks.org/problems/frequency-of-array-elements-1587115620/1)

```Java
public static void frequencyCount(int arr[], int N, int P)
    {
        int[] Hashed = new int[N];
        
        for(int i=0;i<N;i++){
            if(N>=arr[i]) Hashed[arr[i]-1] = Hashed[arr[i]-1] + 1;
        }
        
        for(int i=0;i<N;i++){
            arr[i] = Hashed[i];
        }
    }
```


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

##### Find :
Return the third largest number in the given array
##### Algorithm :
- On the first if statement , we check whether the given array size is 3 , if not return -1 as we can't find the third largest number
- if the size is 3 , the minimum number of the given array must be the 3rd largest number of array
- The First loop find the Largest Element in the Array
- The Second loop find the 2nd Largest Element in the Array
- The Third loop find the 3rd Largest Element of the Array , which is the Answer
##### Code :
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

#### [Missing Number in the Array](https://practice.geeksforgeeks.org/problems/missing-number-in-array1416/1)

##### Find :
Find the missing Element in the given array
##### Algorithm : 
- We create an Array named 'Hash' in size of N+1 and init every number with zero
- The size is n+1 because we are ignoring the index 0 
- On the first loop , we get the element of Input Array , and make the Hash Array's element position increment by 1
- On the Second Loop , we check the Elements of Hash array , incase if the element is 0 that would be the Missing element
##### Code :
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

#### [Search Element in 2D Array( M x N)](https://leetcode.com/problems/search-a-2d-matrix/submissions/)
##### Find :
Return True if target element is found otherwise false
##### Algorithm :
We used a Binary Search to find the element [[Binary Search#2D Arrays (Matrix)]]
##### Code :
```Java
public boolean searchMatrix(int[][] matrix, int target) {
        int row = 0;
        int column = matrix[0].length-1;
        
        while(row < matrix.length && column >= 0)
            if(matrix[row][column] == target){
                return true;
            }else if(matrix[row][column] > target){
                column--;
            }else{
                row++;
            }
        }
        return false;
    }
```

#### [448. Find All Numbers Disappeared in an Array](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/)
##### Used Cyclic sort method to solve the problem [[Sorting Techniques#Cyclic Sort]]

```Java
class Solution {
    public List<Integer> findDisappearedNumbers(int[] nums) 
        ArrayList<Integer> Result = new ArrayList<>();
        int i=0;
        while(i<nums.length){
            int correct = nums[i]-1;
            if( i < nums.length && nums[i] != nums[correct]){
                int temp = nums[i];
                nums[i] = nums[correct]
                nums[correct] = temp;
            } else i++;
        }
        for(i=0;i<nums.length;i++){
            if(nums[i] != i+1){
                Result.add(i+1);
            }
        }
        return Result;
    }
}
```

#### [Missing number in array](https://www.geeksforgeeks.org/problems/missing-number-in-array1416/1)

##### Used Cyclic sort method to solve the problem [[Sorting Techniques#Cyclic Sort]]

```Java
class Solution {
    int missingNumber(int array[], int n) {
        int i=0; int size=(n-1);
        while(i<size){
            int correct = array[i] - 1;
            if( array[i] < size-1 &&  array[i] != array[correct]){
                int temp = array[i];
                array[i] = array[correct];
                array[correct] = temp;
            }else i++;
        } 
        for(i=0;i<size;i++){
            if(array[i] != (i+1)){
                return (i+1);
            }
        }
        return n;
    }
}
```

#### [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)

##### Used Cyclic sort method to solve the problem [[Sorting Techniques#Cyclic Sort]]

```Java
public static int findDuplicate(int[] nums) {  
    int i=0;  
    while(i<nums.length){  
        int correct = nums[i] -1;  
        if(nums[i] != nums[correct]) swap(nums,i,correct);  
        else i++;  
    }  
    for(i=0;i<nums.length;i++){  // Check for the element that is not equal to index after sorting of array
        if(nums[i] != (i+1)){  
            return nums[i];  
        }  
    }  
    return nums.length;  
}  
public static void swap(int[] array , int from, int to){  
    int temp = array[from];  
    array[from] = array[to];  
    array[to] = temp;  
}
```

Rewrote the condition 
```Java
public int findDuplicate(int[] nums) {
        int i=0;
        while(i<nums.length){
            int correct = nums[i] -1;
            if(nums[i] != (i+1)){
                if(nums[i] != nums[correct]) swap(nums,i,correct); // If the checking element is already present in the correct position , then the element is repeated
                else return nums[i];
            }else i++;
        }
        return nums.length;
    }
    public static void swap(int[] array , int from, int to){
        int temp = array[from];
        array[from] = array[to];
        array[to] = temp;
    }
```

#### [442. Find All Duplicates in an Array](https://leetcode.com/problems/find-all-duplicates-in-an-array/)

##### Used Cyclic sort method to solve the problem [[Sorting Techniques#Cyclic Sort]]

```Java
public List<Integer> findDuplicates(int[] nums) {
        ArrayList<Integer> Result = new ArrayList<>();
        int i=0;
        while(i<nums.length){
            int correct = nums[i]-1;
            if(nums[i] != nums[correct]) swap(nums,i,correct);
            else i++;
        }
        for(i=0;i<nums.length;i++){
            if(nums[i] != i+1){
                Result.add(nums[i]);
            }
        }
        return Result;
    }
     public static void swap(int[] array , int from, int to){
            int temp = array[from];
            array[from] = array[to];
            array[to] = temp;
    }
```


#### [645. Set Mismatch](https://leetcode.com/problems/set-mismatch/)

```Java
    public int[] findErrorNums(int[] nums) {
        int i=0;
        while(i<nums.length){
            int correct = nums[i]-1;
            if(nums[i] != nums[correct]) swap(nums,correct,i);
            else i++;
        }
        for(i=0;i<nums.length;i++)
            if(nums[i] != i+1){
                return new int[] {nums[i],(i+1)};
            }
        }
        return new int[]{-1,-1};
    }
    public static void swap(int[] array , int from, int to){
        int temp = array[from];
        array[from] = array[to];
        array[to] = temp;
    }
```

#### [41. First Missing Positive](https://leetcode.com/problems/first-missing-positive/)

```Java
public int firstMissingPositive(int[] nums) {
        int i=0;
        while(i < nums.length){
            int correct = nums[i]-1;
            if(nums[i] > 0 && nums[i] < nums.length && nums[i] != nums[correct] ) swap(nums,i,correct);
            else i++;
        }
        for(i=0;i<nums.length;i++){
            if(nums[i] != (i+1)){
                return i+1;
            }
        }
        return nums.length+1;
    }
```

#### [Segregation of 0's and 1's](https://www.geeksforgeeks.org/problems/segregate-0s-and-1s5106/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=bottom_sticky_on_article)

```Java
void segregate0and1(int[] arr, int n) {
        int i=0,low = 0;
        while(i<n){
            if(arr[i]==0){
                if(arr[i] == arr[low]) {
                    low++;
                    i++;
                }
                else {
                    swap(arr,i,low); low++;
                }
            }else i++;
        }
    }
    public static void swap(int[] a,int fr,int to){
        int temp = a[fr];
        a[fr] = a[to];
        a[to] = temp;
    }
```

#### [Find pair with given sum](https://www.geeksforgeeks.org/problems/key-pair5616/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=bottom_sticky_on_article)

```Java
boolean hasArrayTwoCandidates(int arr[], int n, int x) {
        
        Arrays.sort(arr);
        int F=0 , L = n-1;
        
        while(L>F){
            if(arr[F]+arr[L] == x) return true;
            else if(arr[F]+arr[L] > x ) L--;
            else F++;
        }
        return false;
    }
```


#### [ 1 to N Without Loop](https://www.codingninjas.com/codestudio/problems/print-1-to-n_628290?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
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

#### [Remove Duplicates from Sorted Array](https://www.codingninjas.com/studio/problems/remove-duplicates-from-sorted-array_1102307?utm_source=striver&utm_medium=website&utm_campaign=codestudio_a_zcourse&leftPanelTabValue=PROBLEM)

```Java
public class Solution {
    public static int removeDuplicates(int[] arr,int n) {
        int counter = 1;
        for(int i=1;i<arr.length;i++){
            if(arr[i-1] < arr[i] ) counter++;
        }
        return counter;
    }
}
```

#### [ Move Zero's to End](https://www.codingninjas.com/studio/problems/ninja-and-the-zero-s_6581958?utm_source=striver&utm_medium=website&utm_campaign=codestudio_a_zcourse&leftPanelTabValue=SUBMISSION)

```Java
public class Solution {
    public static int[] moveZeros(int n, int[] a) {
        int zCounter = 0;
        int nCounter = 0;
        int[] result = new int[a.length];
        for(int i=0;i<a.length;i++){
            if(a[i] == 0) {
                result[a.length - 1 - zCounter] = a[i];
                zCounter++;
            }
            else {
                result[nCounter] = a[i];
                nCounter++;
            }
        }
        return result;
    }
}
```