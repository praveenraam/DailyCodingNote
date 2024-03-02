
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

#### [Rotate Array by K](https://www.codingninjas.com/studio/problems/rotate-array_1230543?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=DISCUSS)

```Java
import java.util.ArrayList;
public class Solution {
    public static ArrayList<Integer> rotateArray(ArrayList<Integer> arr, int k) {
        ArrayList<Integer> Result = new ArrayList<>();
        int[] temp = new int[k];
        int index = 0;
        for(Integer i : arr){
            if(index == k) break;
            temp[index] = i; index++;
        }
        for(index = index;index<arr.size();index++){
            Result.add(arr.get(index));
        }
        for(index=0;index<temp.length;index++){
            Result.add(temp[index]);
        }
        return Result;
    }
}
```

#### [ Missing Number from 1-N](https://www.codingninjas.com/studio/problems/missing-number_6680467?utm_source=striver&utm_medium=website&utm_campaign=codestudio_a_zcourse&leftPanelTabValue=PROBLEM)

```Java
public class Solution {
    public static int missingNumber(int[] a, int N) {
        int Sum = Summation(a.length);
        int total = 0;
        for(int i=0;i<a.length;i++){
            total += a[i];
        }
        return (Sum-total);
    }
    public static int Summation(int n){
        if(n==0) return 0;
        return n+Summation(n-1);
    }
}
```

#### [485. Max Consecutive Ones](https://leetcode.com/problems/max-consecutive-ones/)

```Java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int max = 0;
        int counter = 0;
        for(int i=0;i<nums.length;i++){
            if(nums[i] != 1) counter = 0;
            else {
                counter++;
                if(max < counter) max = counter;
            }
        }
        return max;
    }
}
```

#### [136. Single Number](https://leetcode.com/problems/single-number/)
```Java
class Solution {
    public int singleNumber(int[] nums) {
        HashMap <Integer,Integer> temp = new HashMap<>();
        for(int i=0;i<nums.length;i++){
            if(temp.get(nums[i]) != null) temp.put(nums[i],temp.get(nums[i])+1);
            else temp.put(nums[i],1);
        }
        for(int i=0;i<nums.length;i++){
            int value = temp.get(nums[i]);
            if(value == 1) return nums[i];
        }
        return -1;
    }
}
```
#### [Two Sum](https://www.codingninjas.com/studio/problems/reading_6845742?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)
```Java
import java.util.*;
public class Solution {
    public static String read(int n, int[] book, int target){
        HashMap<Integer,Integer> temp = new HashMap<>();
        for(int i=0;i<book.length;i++){
            if(temp.get(book[i]) != null) temp.put(book[i],temp.get(book[i])+1);
            else temp.put(book[i],1);
        }
        for(int i=0;i<book.length;i++){
            int rValue = target - book[i];
            if(temp.get(rValue) != null) return "YES";
        }
        return "NO";
    } 
     public static String read(int n, int[] book, int target){
         int P1 = 0;
         int P2 = book.length-1;
         Arrays.sort(book);
         while(P1<P2){
            int sum = book[P1]+book[P2];
            if(sum == target) return "YES";
            else if(sum > target) P2--;
            else P1++;
         }
         return "NO";
     }
}
```
#### [Alternate Numbers](https://www.codingninjas.com/studio/problems/alternate-numbers_6783445?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
```Java
public class Solution {
    public static int[] alternateNumbers(int []a) {
        int[] arr = new int[a.length];
        int p1 = 0;
        int p2 = 1;
        for(int i=0;i<a.length;i++){
            if(a[i]<0) {
                arr[p2] = a[i];
                p2+=2;
            }else {
                arr[p1] = a[i];
                p1+=2;
            }
        }
        return arr;
    }
}
```

#### [Best time to buy and sell stock](https://www.codingninjas.com/studio/problems/best-time-to-buy-and-sell-stock_6194560?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)
```Java
public class Solution {
    public static int bestTimeToBuyAndSellStock(int []prices) {
        int min = Integer.MAX_VALUE;
        int maxProfit = 0;
        for(int i=0;i<prices.length;i++){
            if(min > prices[i]) min = prices[i];
            int profit = prices[i] - min;
            if(maxProfit < profit) maxProfit = profit;
        }
        return maxProfit;
    }
}
```

#### [Majority Element](https://www.codingninjas.com/studio/problems/majority-element_6783241?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
```Java
import java.util.*;
public class Solution {
    public static int majorityElement(int []v) {
        HashMap<Integer,Integer> temp = new HashMap<>();
        for(int i=0;i<v.length;i++){
            if(temp.get(v[i]) == null) temp.put(v[i],1);
            else temp.put(v[i],temp.get(v[i])+1);            
        }
        for(int i=0;i<v.length;i++){
            int value = temp.get(v[i]);
            if(value >= v.length/2) return v[i];
        }
        return -1;
    }
}
```

#### [Sort Colors](https://leetcode.com/problems/sort-colors/)
```Java
public static void sort012(int[] nums){  
    int[] temp = new int[nums.length];  
    int midCounter = 0;  
    for(int i=0;i<nums.length;i++) if(nums[i] == 0) midCounter++;  
    int low = 0,high = nums.length-1;  
    for(int i=0;i<nums.length;i++){  
        if(nums[i] == 0) {  
            temp[low] = nums[i];  
            low++;  
        }else if(nums[i] == 1) {  
            temp[midCounter] = nums[i];  
            midCounter++;  
        }else{  
            temp[high] = nums[i];  
            high--;  
        }  
    }  
    for(int i=0;i<nums.length;i++) nums[i] = temp[i];  
}   
  
public static void sort012(int[] nums){  
    int low=0,mid = 0,high=nums.length-1;  
    while(mid<=high){  
        if(nums[mid] == 0) {  
            swap(nums,mid,low);  
            low++; mid++;  
        }else if(nums[mid] == 1){  
            mid++;  
        }else if(nums[mid] == 2){  
            swap(nums,mid,high);  
            high--;  
        }  
    }  
}
```

#### [Longest Successive Elements](https://www.codingninjas.com/studio/problems/longest-successive-elements_6811740?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)
```Java
public static int longestSuccessiveElements(int []a) {  
    int maxCount = 0;  
    Arrays.sort(a);  
    int counter = 1;  
  
    for(int i =0;i<a.length-1;i++){  
        if(a[i] != a[i+1]-1 && a[i] != a[i+1]) counter = 1;  
        else if (a[i] == a[i+1]-1) counter++;  
        if(maxCount<counter) maxCount = counter;  
    }  
    return maxCount;  
}
```

#### [Superior Elements](https://www.codingninjas.com/studio/problems/superior-elements_6783446?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
```Java
public static List< Integer > superiorElements(int []a) {
        List<Integer> result = new ArrayList<Integer>();
        int max = a[a.length-1];
        result.add(a[a.length-1]);
        for(int i=a.length-1;i>=0;i--){
            if(a[i] > max){
                result.add(a[i]);
                max = a[i];
            }
        }
        Collections.sort(result);
        return result;
    }
```

#### [Maximum Subarray Sum](https://www.codingninjas.com/studio/problems/630526?topList=striver-sde-sheet-problems&utm_source=striver&utm_medium=website&leftPanelTabValue=SUBMISSION)
```Java
import java.util.* ;
import java.io.*; 
public class Solution {
    public static long maxSubarraySum(int[] arr, int n) {
        long max = 0L;
        int sum = 0;
        for(int i=0;i<arr.length;i++){
            if(sum<0) sum = arr[i];
            else sum+=arr[i];
            if(max < sum) max =sum;
        }
        return max;
    }
}
```

### [Zero Matrix]()
```Java
import java.util.* ;
import java.io.*; 
public class Solution {
public static ArrayList<ArrayList<Integer>> zeroMatrix (ArrayList<ArrayList<Integer>> matrix, Integer n, Integer m) {
        int[] arrN = new int[n];
        int[] arrM = new int[m];

        for(int i=0;i<matrix.size();i++){
            for(int j=0;j<m;j++){
                if(matrix.get(i).get(j) == 0) {
                    arrN[i] = 1;
                    arrM[j] = 1;
                }
            }
        }
  
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(arrN[i] == 1 || arrM[j] == 1){
                    matrix.get(i).set(j,0);
                }
            }
        }
        return matrix;
    }
}
```

### [Rotate the matrix](https://www.codingninjas.com/studio/problems/rotate-the-matrix_6825090?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)
```Java
import java.util.*;
public class Solution {
    public static void rotateMatrix(int[][] mat){
        int[][] arr = new int[mat.length][mat[0].length];
        int counter = mat.length-1;
        for(int i=0;i<mat.length;i++){
            for(int j=0;j<mat[0].length;j++){
                arr[j][counter]= mat[i][j]  ;
            }
            counter--;
        }
        for(int i=0;i<arr.length;i++){
            for (int j = 0; j < arr[i].length; j++) {
                mat[i][j] = arr[i][j];
            }
        }
    }
}
```

### [Missing and repeating numbers](https://www.codingninjas.com/studio/problems/missing-and-repeating-numbers_873366?leftPanelTabValue=PROBLEM)
```Java
import java.util.* ;
import java.io.*; 
import java.util.ArrayList;
import java.util.*;
  
public class Solution {
    public static int[] missingAndRepeating(ArrayList<Integer> arr, int n) {
        int[] Hash = new int[n+1];
        for(int i=0;i<arr.size();i++){
            Hash[arr.get(i)]+=1;
        }
        int repeating = -1,missing = -1;
        for(int i=1;i<Hash.length;i++){
            if(Hash[i] == 0) missing = i;
            if(Hash[i] == 2) repeating = i;
        }
        return new int[] {missing,repeating};
    }
}
```

### [Spiral of Array](https://www.codingninjas.com/studio/problems/spiral-matrix_6922069?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION)
```Java
import java.util.*;
public class Solution {
    public static int[] spiralMatrix(int [][]MATRIX) {
        int n = MATRIX.length;
        int m = MATRIX[0].length;
        int[] arr = new int[n*m];
        int top = 0,buttom = n-1,left = 0,right = m-1;
        int i=0;
        while(top <= buttom && left<=right ){
            for(int j=left;j<=right;j++){
                arr[i] = MATRIX[top][j];
                i++;
            }
            top++;
            if(i>=(n*m)) break;
            for(int j=top;j<=buttom;j++){
                arr[i] = MATRIX[j][right];
                i++;
            }
            right--;
            if(i>=(n*m)) break;
            for(int j=right;j>=left;j--){
                arr[i] = MATRIX[buttom][j];
                i++;
            }
            buttom--;
            if(i>=(n*m)) break;
            for(int j=buttom;j>=top;j--){
                arr[i] = MATRIX[j][left];
                i++;
            }
            left++;
        }
        return arr;
    }
}
```

### [Non Repeating element](https://www.geeksforgeeks.org/problems/non-repeating-element3958/1)
```Java
class Check{
    
    public int firstNonRepeating(int arr[], int n) 
    { 
        HashMap<Integer,Integer> Hash = new HashMap();
        
        for(int i=0;i<n;i++){
            if(Hash.get(arr[i]) == null) Hash.put(arr[i],1);
            else Hash.put(arr[i] , Hash.get(arr[i])+1);
        }
        
        for(int i=0;i<n;i++){
            if(Hash.get(arr[i]) == 1) return arr[i];
        }
        return 0;
    }  
    
}
```

### [Pascal's Triangle](https://www.codingninjas.com/studio/problems/print-pascal-s-triangle_6917910?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=SUBMISSION)
```Java
import java.util.*;
public class Solution {
    public static int[][] pascalTriangle(int N) {
        int[][] arr = new int[N][];
        for(int i=0;i<N;i++){
            arr[i] = new int[i+1];
            arr[i][0] = 1;
            if(i==0) continue;
            arr[i][i] = 1;
            for(int j=1;j<=i-1;j++){
                arr[i][j] = arr[i-1][j-1]+arr[i-1][j];
            }
        }
        return arr;
    }
}
```
### [Majority Element](https://www.codingninjas.com/studio/problems/majority-element_6915220?utm_source=striver&utm_medium=website&utm_campaign=codestudio_a_zcourse&leftPanelTabValue=PROBLEM)
```Java
import java.util.*;
public class Solution {
    public static List< Integer > majorityElement(int []v) {
        List<Integer> arr = new ArrayList<>();
        HashMap<Integer,Integer> Hash = new HashMap<>();
        for(int i=0;i<v.length;i++){
            if(Hash.get(v[i]) == null) Hash.put(v[i],1);
            else Hash.put(v[i],Hash.get(v[i])+1);
        }
        for(Map.Entry<Integer,Integer> entry : Hash.entrySet()){
            if(entry.getValue() > (v.length/3)) arr.add(entry.getKey());
        }
        return arr;
    }
}
```

### Sum of others in Array
Write a program to accept the element into an array and replace every element in the array with the sum of its every other element

**Input format :**
Number of elements followed by array as input elements

**Output format :**
Array elements after modification

**Sample test cases:**
Input 1:
7
1 2 3 4 5 6 7
Output 1:
27 25 22 18 13 7 0

```Java
#include <stdio.h>
int main(){
    int size;
    scanf("%d",&size);
    int arr[size];
    for(int i=0;i<size;i++){
        scanf("%d",&arr[i]);
    }
    int sum=0;
    for(int i=0;i<size;i++){
        sum+=arr[i];
    }
    int counter=0;
    for(int i=0;i<size;i++){
        printf("%d ",sum-arr[i]-counter);
        counter+=arr[i];
    }
}
```

#### Write a program to count the frequency of element in the array
**Input format:**

The first line contains the number of elements.
Second line has the array elements.

**Output format:**
Print the number and Frequency of that number separate them by COLON

**Code constraints:**
1 <= n <= 100
0 <= arr[i] <= 10^18

```Java
import java.util.*

class Solution{
	public static void main(String[] args){
		Scanner reader = new reader(System.in);

		int size = reader.nextInt();
		int[] input = new int[size];

		for(int i=0;i<size;i++){
			input[i] = reader.nextInt();
		}
		HashMap<Integer,Integer> temp = new HashMap<>();
		
		for(int i=0;i<size;i++){
			if(temp.get(nums[i]) != null) temp.put(nums[i],temp.get(nums[i])+1);
            else temp.put(nums[i],1);
		}

		for(int i=0;i<size;i++){
			if(Hash.get(input[i]) != -1){
				System.out.println(input[i]+":"+Hash.get(input[i]));
				Hash.put(input[i],-1);
			}
		}
	
	}
}
```

### Print the Pattern

Ninja is given a pattern. Now he is asked to print the same pattern for any given ‘N’ number of rows.

`There is only one space between the values of each column in a row.  For example, Pattern for ‘N’ = 5 will be. 1 2 3 4 5  11 12 13 14 15  21 22 23 24 25  16 17 18 19 20  6 7 8 9 10`

Detailed explanation ( Input/output format, Notes, Images )
#### Sample Input1 :
`` 5 ``
#### Sample Output2 :
Explain
`1 2 3 4 5  11 12 13 14 15  21 22 23 24 25  16 17 18 19 20  6 7 8 9 10` 
#### Explanation of Sample Input 1

```
For test case 1:
We print the given pattern for the given 5 rows where each row has different values in increasing order with a difference in the value of 1 between each element and 1 space between each column in a row.
```
##### Code 
```Java
public static String[] NumberPattern(int n) {  
  
    int[][] i = new int[n][n];  
    int counter = 1;  
    for (int j = 0; j < i.length; j++) {  
        for (int k = 0; k < i[j].length; k++) {  
            i[j][k] = counter;  
            counter++;  
        }  
    }  
  
    String[] result = new String[n];  
  
    int m=-2; int index=0;  
    int difference = 2;  
    counter=0;  
    while(counter<n){  
        m+=difference;  
        if(m>=i.length){  
            int hello = 2;  
            if(n%2 == 0) {  
                hello=1;  
            }  
            m=i.length -hello;  
            difference=-2;  
        }  
        result[index]="";  
        for (int j = 0; j < i[index].length; j++) {  
            if(j==0) result[index] += i[m][j];  
            else result[index] += " "+i[m][j];  
        }  
        index++;  
        counter++;  
    }  
  
    System.out.println(Arrays.toString(result));  
    return result;  
}
```

### [Merge All Overlapping Intervals](https://www.codingninjas.com/studio/problems/merge-all-overlapping-intervals_6783452?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf&leftPanelTabValue=PROBLEM)

```Java
import java.util.*;
public class Solution {
    public static List< List< Integer > > mergeOverlappingIntervals(int [][]arr){
        int start = arr[0][0]; int end = arr[0][1];
        List<List<Integer>> result = new ArrayList<>();
  
        for(int i=0;i<arr.length;i++){
            if(arr[i][0] > end){
                result.add(Arrays.asList(start,end));
                end = arr[i][0];
                start = arr[i][0];
            }
            if(arr[i][1] > end){
                end = arr[i][1];
            }
        }
        result.add(Arrays.asList(start,end));
        return result;
    }
}
```

### [Team Contest](https://www.codingninjas.com/studio/problems/team-contest_6840309?utm_source=youtube&utm_medium=affiliate&utm_campaign=striver_Arrayproblems&leftPanelTabValue=PROBLEM)
```Java
public class Solution {
    public static int team(int []skill, int n){
        int counter= 0;
        int i=0,j=n-1;
        for(i=0;i<n;i++){
            for(j=i+1;j<n;j++){
                if(skill[i]>(2*skill[j])) counter++;
            }
        }        
        return counter;
    }
}
```

