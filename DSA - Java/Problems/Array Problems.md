


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

### [Pascal's Triangle](https://leetcode.com/problems/pascals-triangle)
```Java
import java.util.*;
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> res = new ArrayList<>();
        
        res.add(new ArrayList<>());
        res.get(0).add(1);

        if(numRows == 1) {
            return res;
        }

        res.add(new ArrayList<>());
        res.get(1).add(1);
        res.get(1).add(1);

        if(numRows == 2){
            return res;
        }

        int counter = 3;
        while(counter<=numRows){

            res.add(new ArrayList<>());

            for(int i=0;i<counter-1;i++){
                if(i == 0) res.get(counter-1).add(1);
                else {
                    int sum = res.get(counter-2).get(i-1);
                    sum += res.get(counter-2).get(i);
                    res.get(counter-1).add(sum);
                }
            }
            res.get(counter-1).add(1);
            counter++;
        }
        return res;
    }
}
```
### [Pascal's Triangle II](https://leetcode.com/problems/pascals-triangle-ii)
```Java
class Solution {
    public List<Integer> getRow(int rowIndex) {
        List<List<Integer>> res = new ArrayList<>();
        
        res.add(new ArrayList<>());
        res.get(0).add(1);

        if(rowIndex == 0) {
            return res.get(0);
        }

        res.add(new ArrayList<>());
        res.get(1).add(1);
        res.get(1).add(1);

        if(rowIndex == 1){
            return res.get(1);
        }

        int counter = 3;
        while(counter<=(rowIndex+1)){

            res.add(new ArrayList<>());

            for(int i=0;i<counter-1;i++){
                if(i == 0) res.get(counter-1).add(1);
                else {
                    int sum = res.get(counter-2).get(i-1);
                    sum += res.get(counter-2).get(i);
                    res.get(counter-1).add(sum);
                }
            }
            res.get(counter-1).add(1);
            counter++;
        }
        return res.get(rowIndex);
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

### [Minimum Common Value](https://leetcode.com/problems/minimum-common-value/)

```Java
class Solution {
    public int getCommon(int[] nums1, int[] nums2) {
        int p1=0,p2=0;
        while(p1<nums1.length && p2<nums2.length){
            if(nums1[p1] == nums2[p2]) return nums1[p1];
            if(nums1[p1]>nums2[p2]){
                p2++;
            }else if(nums1[p1]<nums2[p2]){
                p1++;
            }
        }
        return -1;
    }
}
```

### [Flipping an Image](https://leetcode.com/problems/flipping-an-image/)
```Java
class Solution {
    public int[][] flipAndInvertImage(int[][] image) {
        for(int i=0;i<image.length;i++){
            int start = 0, end=image[i].length-1;
            while(start<=end){
                swap(image,start,end,i,true);
                swap(image,start,end,i,false);
                start++;end--;
            }
        }
        return image;
    }
    public static void swap(int[][] arr,int start,int end,int index,boolean flag){
        if(flag){
            int temp = arr[index][start];
            arr[index][start] = arr[index][end];
            arr[index][end] = temp;
        }else if(!flag){
            if(arr[index][start] == 0) arr[index][start] = 1;
            else if(arr[index][start] == 1) arr[index][start] =0;
            if(start != end){
                if(arr[index][end] == 0) arr[index][end] = 1;
                else if(arr[index][end] == 1) arr[index][end] =0;
            }
        }
    }
}
```

### [1299. Replace Elements with Greatest Element on Right Side](https://leetcode.com/problems/replace-elements-with-greatest-element-on-right-side/)
```Java
class Solution {
    public int[] replaceElements(int[] arr) {
        int max  = -1;
        for(int i=arr.length-1;i>=0;i--){
            int temp = max;
            if(max < arr[i]) max = arr[i];
            arr[i] = temp;   
        }
        return arr;
    }
}
```

### [27. Remove Element](https://leetcode.com/problems/remove-element/)

```Java
class Solution {
    public int removeElement(int[] nums, int val) {
        int counter = 0;
        int index = 0;
        for(int i=0;i<nums.length;i++){
            if(nums[i] != val ){
                counter++;
                nums[index] = nums[i]; index++;
            }
        }
        return counter;
    }
}
```

### [217. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

```Java
import java.util.*;

class Solution {
    public boolean containsDuplicate(int[] nums) {
        Map<Integer,Integer> map = new HashMap<>();
        
        for(int i=0;i<nums.length;i++){
            if(map.containsKey(nums[i])) map.put(nums[i],map.get(nums[i])+1);
            else map.put(nums[i],1);
            
            if(map.get(nums[i]) > 1) return true;
        }
        return false;
    }
}
```

### [169. Majority Element](https://leetcode.com/problems/majority-element/)

```Java
class Solution {
    public int majorityElement(int[] nums) {
        Map<Integer,Integer> mp = new HashMap<>();

        for(int i=0;i<nums.length;i++){
            int n = nums[i];
            if(mp.containsKey(n)) mp.put(n,mp.get(n)+1);
            else mp.put(n,1);

            if(mp.get(n) > (nums.length)/2) return n;
        }
        return -1;

    }
}
```

### [605. Can Place Flowers](https://leetcode.com/problems/can-place-flowers/)

```Java
class Solution {
    public boolean canPlaceFlowers(int[] flowerbed, int n) {
        int counter = n;
        if(flowerbed.length < 2) {
            if(flowerbed[0] == 0) counter--;

            if(counter > 0) return false;
            return true;
        }
        if(flowerbed[0] == 0 && flowerbed[1] == 0){
            counter--;
            flowerbed[0] = 1;
        }
        if(flowerbed[flowerbed.length-1] == 0 && flowerbed[flowerbed.length-2] == 0){
            counter--;
            flowerbed[flowerbed.length-1] = 1;
        }

        for(int i=1;i<flowerbed.length-1;i++){
            if(flowerbed[i-1] == 0 && flowerbed[i+1] == 0 && flowerbed[i] == 0){
                counter--;
                flowerbed[i] = 1;
            }
        }
        
        if(counter > 0) return false;
        return true;
    }
}
```

### [Find Pivot Index](https://leetcode.com/problems/find-pivot-index/description/)

```Java
class Solution {
    public int pivotIndex(int[] nums) {
        int totalSum  = 0;
        for(int i=0;i<nums.length;i++){
            totalSum+=nums[i];
        }
        int sum2 = 0;
        for(int i=0;i<nums.length;i++){
            sum2 += nums[i];
            if(sum2 == totalSum) return i;
            totalSum -= nums[i];
        }

        return -1;
    }
}
```

### [Next Greater Element I](https://leetcode.com/problems/next-greater-element-i/)

```Java
class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
        Map<Integer,Integer> mp = new HashMap<>();
        int max = -1;
        for(int i=nums2.length - 1;i>0;i--){
            mp.put(nums2[i],max);
            if(nums2[i-1] < nums2[i]) max = nums2[i];
        }
        mp.put(nums2[0],max);
        mp.put(nums2[nums2.length-1],-1);
        for(int i=0;i<nums1.length;i++){
            if(mp.get(nums1[i]) > nums1[i]){
                nums1[i] = mp.get(nums1[i]);
            }else nums1[i] = -1;
        }
        return nums1;
    }
}
```

### [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)

```Java
import java.util.*;

class Solution {
    public int[] topKFrequent(int[] nums, int k) {

        Map<Integer,Integer> Map = new HashMap<>();
        List<Integer>[] ListArr = new List[nums.length+1];

        for(int i=0;i<nums.length;i++){
            Map.put(nums[i],Map.getOrDefault(nums[i],0)+1);
        }

        for(int key : Map.keySet()){
            int freq = Map.get(key);
            if(ListArr[freq] == null){
                ListArr[freq] = new ArrayList<>();
            }
            ListArr[freq].add(key);
        }

        int[] result = new int[k];
        int counter = 0;

        for(int i=ListArr.length-1;i>=0 && counter < k;i--){
            if(ListArr[i] != null){
                for(int j=0; j<ListArr[i].size() && counter < k;j++){
                    result[counter] = ListArr[i].get(j);
                    counter++;
                }
            }
        }
        return result;
    }
}
```

### [238. Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)

```Java
class Solution {
    public int[] productExceptSelf(int[] nums) {

        int result[] = new int[nums.length];
        result[0] = 1;
        int left = 1;

        for(int i=0;i<result.length;i++){
            result[i] = left;
            left*=nums[i];
        }

        int right = 1;
        for(int i=result.length-2;i>=0;i--){
            int temp = right*nums[i+1];
            result[i] = result[i]*temp;
            right = right*nums[i+1];
        }
        return result;
    }
}
```

### [535. Encode and Decode TinyURL](https://leetcode.com/problems/encode-and-decode-tinyurl/)

```Java
public class Codec {
    Map<String,String> map = new HashMap<>();
    // Encodes a URL to a shortened URL.
    public String encode(String longUrl) {
        String key = "number4";
        map.put(key,longUrl);
        return key;
    }

    // Decodes a shortened URL to its original URL.
    public String decode(String shortUrl) {
        return map.get(shortUrl);
    }
}
```

### [128. Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)

```Java
import java.util.*;
class Solution {
    public int longestConsecutive(int[] nums) {
        
        Set<Integer> set = new HashSet<>();
        
        if(nums.length < 1) return 0;

        for(int i=0;i<nums.length;i++){
            set.add(nums[i]);
        }

        int counter = 1;
        for(int i=0;i<nums.length;i++){
            if(!set.contains(nums[i]-1)){
                int temp=1;
                while(true){
                    if(set.contains(nums[i]+1)) temp++;
                    else break;
                    nums[i]++;
                }
                if(temp>counter) counter = temp;
            }
        }
        return counter;

    }
}
```

### [554. Brick Wall](https://leetcode.com/problems/brick-wall/)

```Java
class Solution {
    public int leastBricks(List<List<Integer>> wall) {
        Map<Integer,Integer> map = new HashMap<>();

        int edgeTotal = 0;
        int total = 0;

        for(int i=0;i<wall.get(0).size();i++){
            total += wall.get(0).get(i);
        }
        
        for(int i=0;i<wall.size();i++){
            for(int j=0;j<wall.get(i).size();j++){
                int sum = wall.get(i).get(j);
                edgeTotal += sum;
            
                map.put(edgeTotal,map.getOrDefault(edgeTotal,0)+1);
            }
            edgeTotal = 0;
        }

        int Max = 0;
        for(Map.Entry<Integer,Integer> entry : map.entrySet()){
           int current = entry.getValue();
           if(entry.getKey() == total) continue;
           if(current > Max) {
                Max = current;
           }
        }

        return (wall.size() - Max); 
        
    }
}
```

### [1963. Minimum Number of Swaps to Make the String Balanced](https://leetcode.com/problems/minimum-number-of-swaps-to-make-the-string-balanced/)

```Java
import java.util.*;

class Solution {
    public int minSwaps(String s) {
        Stack<Character> st = new Stack<>();
        
        for(int i=0;i<s.length();i++){
            char ch = s.charAt(i);
  
            if(ch == '['){
                st.push('[');
            }else{
                if(!st.isEmpty()){
                    st.pop();
                }
            }
        }
        return ((st.size()+1)/2);
    }
}
```

### [2001. Number of Pairs of Interchangeable Rectangles](https://leetcode.com/problems/number-of-pairs-of-interchangeable-rectangles/)

```Java
class Solution {
    public long interchangeableRectangles(int[][] rectangles) {

        long counter = 0;
        Map<Double,Long> mp = new HashMap<>();

        for(int i=0;i<rectangles.length;i++){
            double val = (double)rectangles[i][0]/(double)rectangles[i][1];

            if(mp.containsKey(val)){
                counter += mp.get(val);
            }
            mp.put(val,mp.getOrDefault(val,0L)+1);
        }
  
        return counter;
    }
}
```

### [Rotate Matrix K times](https://www.naukri.com/code360/problems/moderate_7544412?leftPanelTabValue=PROBLEM)

```Java
import java.util.* ;
import java.io.*; 
import java.util.ArrayList;

public class Solution {
    public static ArrayList<ArrayList<Integer>> solve(ArrayList<ArrayList<Integer>> arr, int k) {
        for(int i=0;i<arr.size();i++){
            swapper(arr.get(i),k);
        }
        return arr;
    }

    public static void swapper( ArrayList<Integer> arr,int k){
        int len = arr.size();
        for(int i=0;i<k;i++){
            int last = arr.get(len-1);
            for(int j=len-1;j>0;j--){
                arr.set(j,arr.get(j-1));
            }
            arr.set(0,last);
        }
    }
}
```

### [665. Non-decreasing Array](https://leetcode.com/problems/non-decreasing-array/)
```Java
class Solution {
    public boolean checkPossibility(int[] nums) {

        int counter=0;

        for(int i=1;i<nums.length;i++){
            if(nums[i] < nums[i-1]){
                counter++;
                if (i - 2 < 0 || nums[i - 2] <= nums[i]) nums[i - 1] = nums[i]; 
                else nums[i] = nums[i - 1];
            } 
            if(counter == 2) return false;
        }

        return true;
    }
}
```

### [2215. Find the Difference of Two Arrays](https://leetcode.com/problems/find-the-difference-of-two-arrays/)
```Java
class Solution {
    public List<List<Integer>> findDifference(int[] nums1, int[] nums2) {
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> set2 = new HashSet<>();

        for(int i=0;i<nums1.length;i++){
            set1.add(nums1[i]);
        }
        for(int i=0;i<nums2.length;i++){
            set2.add(nums2[i]);
        }

        List<List<Integer>> res = new ArrayList<>();
        res.add(new ArrayList<>()); 
        res.add(new ArrayList<>());

        for(int i=0;i<nums2.length;i++){
            if(!(set1.contains(nums2[i]))){
                set1.add(nums2[i]);
                res.get(1).add(nums2[i]);
            } 
            
        }
        for(int i=0;i<nums1.length;i++){
            if(!(set2.contains(nums1[i]))){
                set2.add(nums1[i]);
                res.get(0).add(nums1[i]);
            }
        }

        return res;

    }
}
```

### [11. Container With Most Water](https://leetcode.com/problems/container-with-most-water/)
```Java
class Solution {
    public int maxArea(int[] height) {
        int p1 = 0;
        int p2 = height.length-1;
        int ans = 0;

        while(p1<p2){
            int s = height[p1];
            int e = height[p2];
            int temp = 0;
            int dif = p2-p1;

            if(s > e){
                temp = e*dif;
                p2--;
            }
            else {
                temp = s*dif;
                p1++;
            }

            if(temp > ans) ans = temp;

        }

        return ans;
    }
}
```

### [179. Largest Number](https://leetcode.com/problems/largest-number/)

```Java
class Solution {
    public String largestNumber(int[] nums) {
        String[] arr = new String[nums.length];

        for(int i=0;i<nums.length;i++){
            arr[i] = String.valueOf(nums[i]);
        }

        Arrays.sort(arr,new Comparator<String>(){
            @Override
            public int compare(String n1,String n2){
                String s1=n1+n2,s2 = n2+n1;
                return n2.compareTo(n1);
            }
        });

        if(arr[0].equals("0")) return "0";

        StringBuilder sb = new StringBuilder();
        
        for(String s : arr){
            sb.append(s);
        }

        return sb.toString();
        

    }
}
```

### [2441. Largest Positive Integer That Exists With Its Negative](https://leetcode.com/problems/largest-positive-integer-that-exists-with-its-negative/)

```Java
class Solution {
    public int findMaxK(int[] nums) {
        Set<Integer> st= new HashSet<>();
        int max = -1;

        for(int num : nums){
            st.add(num);
        }

        for(int num : nums){
            int tempMax = 0;
            if(num < 0) continue;

            if(st.contains(num*-1)){
                if(num > max) max = num;
            }

        }

        return max;

    }
}
```

### [2348. Number of Zero-Filled Subarrays](https://leetcode.com/problems/number-of-zero-filled-subarrays/)

```Java
class Solution {
    public long zeroFilledSubarray(int[] nums) {
        int occurrence = 0;
        long result = 0;

        for(int i=0;i<nums.length;i++){
            if(nums[i] == 0) occurrence++;
            else if(occurrence != 0 ){
                result+=(summation(occurrence));
                occurrence = 0;
            }

            if((i+1) == nums.length && nums[i] == 0){
                result+=(summation(occurrence));
                occurrence = 0;
            }
        }

        return result;
    }

    public static long summation(long n){
        if(n<=1) return 1;
        return n+(summation(n-1));
    }
}
```

### [881. Boats to Save People](https://leetcode.com/problems/boats-to-save-people)

```Java
class Solution {
    public int numRescueBoats(int[] people, int limit) {
        Arrays.sort(people);
        int boat = 0;
        int j=people.length-1;

        for(int i=0;i<=j;i++){
            if(i == j){
                boat++;
                break;
            }
            int sum = people[i]+people[j];
            if(sum <= limit){
                boat++;
                j--;
            }else{
                boat++;
                j--;
                i--;
            }
        }
        return boat;
    }
}
```

### [1968. Array With Elements Not Equal to Average of Neighbors](https://leetcode.com/problems/array-with-elements-not-equal-to-average-of-neighbors/)

```Java
class Solution {
    public int[] rearrangeArray(int[] nums) {
        boolean flag = true;

        while(flag){
            flag = false;
            for(int i =1 ;i<nums.length-1;i++){
                if(nums[i-1]+nums[i+1] == 2*nums[i]){
                    int temp = nums[i];
                    nums[i] = nums[i-1];
                    nums[i-1] = temp;
                    flag = true;
                }
            }
        }

        return nums;
    }
}
```

### [167. Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

```Java
class Solution {
    public int[] twoSum(int[] numbers, int target) {
        int p1=0,p2=numbers.length-1;

        while(p1<=p2){
            int sum = numbers[p1]+numbers[p2];

            if(sum == target) return new int[] {p1+1,p2+1};
            else if(sum > target) p2--;
            else p1++;

        }
        return new int[] {-1,-1};
    }
}
```

### [42. Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/)

```Java
class Solution {
    public int trap(int[] height) {
        int leftMax = height[0];
        int water = 0;
        Stack<Integer> rightMax = new Stack<>();

        rightMax.push(height[height.length-1]);
        for(int i=height.length-2;i>1;i--){
            int temp = Math.max(rightMax.peek(),height[i]);
            rightMax.push(temp);
        }

        for(int i=1;i<height.length-1;i++){
            int min = Math.min(rightMax.peek(),leftMax);
            int temp = min-height[i];
            water += Math.max(0,temp);

            rightMax.pop();
            leftMax = Math.max(leftMax,height[i]);
        }

        return water;

    }
}
```

### [219. Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)

```Java

class Solution {
    public boolean containsNearbyDuplicate(int[] nums, int k) {
        Map<Integer,Integer> mp = new HashMap<>();

        for(int i=0;i<nums.length;i++){

            if(!(mp.containsKey(nums[i]))) {
                mp.put(nums[i],i);
            }else{
                int temp = Math.abs(i-mp.get(nums[i]));
                if(temp <= k) return true;
                mp.put(nums[i],i);
            }
        }

        return false;

    }
}
```

### [88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/)

```Java
class Solution {
    public void merge(int[] a, int m, int[] b, int n) {
        int p1 = m-1,p2=n-1,ls=a.length-1;
  
        while(p1>=0 && p2>=0){
            if(a[p1] >= b[p2]){
                a[ls] = a[p1];
                p1--; ls--;
            }else if(a[p1] < b[p2]){
                a[ls] = b[p2];
                p2--; ls--;
            }
        }
  
        while(p1>=0){
            a[ls] = a[p1];
            p1--; ls--;
        }
        while(p2>=0){
            a[ls]= b[p2];
            p2--;ls--;
        }
    }
}
```

### [26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)
```Java
class Solution {
    public int removeDuplicates(int[] n) {
        int p1=0,p2=1;
        while(p2<n.length){
            if(n[p1] == n[p2]) p2++;
            else{
                n[p1+1] = n[p2];
                p1++;p2++;
            }
        }
        return p1+1;
    }

}
```

### [1572. Matrix Diagonal Sum](https://leetcode.com/problems/matrix-diagonal-sum/)

```Java
class Solution {
    public int diagonalSum(int[][] mat) {
        int sum = 0;
        int p1 = 0,p2=0;
        
        while(p1<mat.length && p2<mat[p1].length){
            sum += (mat[p1][p2]);
            mat[p1][p2] = 0;
            p1++;p2++;
        }
        p1=0;p2=mat[0].length-1;

        while(p1<mat.length && p2>=0){
            sum += (mat[p1][p2]);
            p1++;p2--;
        }
        return sum;
    }
}
```

### [Rotate Array](https://leetcode.com/problems/rotate-array/)

```Java
class Solution {
    public void rotate(int[] nums, int k) {
        if(nums.length < k){
            k = k%nums.length;
        }
        int temp[] = new int[k];

        int counter = nums.length-k;
        for(int i=0;i<k;i++){
            temp[i] = nums[counter];
            counter++;
        }

        counter = nums.length-1;
        for(int i=nums.length-k-1;i>=0;i--){
            nums[counter] = nums[i];
            counter--;
        }

        for(int i=0;i<k;i++){
            nums[i] = temp[i];
        }

    }
}
```

```Java
class Solution {
    public void rotate(int[] n, int k) {
        
        if(n.length < k ) k = k%n.length;

        int i=0,j = n.length-1;
        rotateAnArray(n,i,j);
        i=0;j=k-1;
        rotateAnArray(n,i,j);
        i=k;j=n.length-1;
        rotateAnArray(n,i,j);

    }
    public void rotateAnArray(int[] n,int i,int j){
        while(i<j){
            int temp = n[i];
            n[i] = n[j];
            n[j] = temp;

            i++; j--;
        }
    }
}
```

### [Move Zeroes]()

```Java
class Solution {
    public void moveZeroes(int[] n) {
        int i=0,j=1,c=0;

        for(i =0;i<n.length;i++){
            if(n[i] == 0) c++;
        }
        if(c == 0) return;
        i=0;
        while(j<n.length){
            if(n[i] == 0 && n[j] != 0){
                swap(n,i,j);
                i++; j++;
            }else if(n[j] == 0) j++;
            else{
                i++;
            }
        }
    }
    public static void swap(int[] n,int i,int j){
        int temp = n[i];
        n[i] = n[j];
        n[j] = temp;
    }
}
```

### [15. 3Sum](https://leetcode.com/problems/3sum/)

```Java
class Solution {
    public List<List<Integer>> threeSum(int[] n) {
        List<List<Integer>> ls = new ArrayList<>();
        Set<List<Integer>> st = new HashSet<>();

        Arrays.sort(n);

        for(int i=0;i<n.length;i++){
            int p1 = i+1;
            int p2 = n.length-1;

            while(p1<p2){
                int sum =  n[i]+n[p1]+n[p2];
                if(sum == 0){
                    List<Integer> sol = new ArrayList<>();
                    sol.add(n[i]);
                    sol.add(n[p1]);
                    sol.add(n[p2]);
                    if(!st.contains(sol)){
                        ls.add(sol);
                        st.add(sol);
                    }
                    p1++;
                    p2--;

                }else if(sum > 0){
                    p2--;
                }else{
                    p1++;
                }
            }
        }
        return ls;
    }
}
```

### [1984. Minimum Difference Between Highest and Lowest of K Scores](https://leetcode.com/problems/minimum-difference-between-highest-and-lowest-of-k-scores/)

```Java
class Solution {
    public int minimumDifference(int[] n, int k) {
        
        if(n.length < k || n.length == 1) return 0;

        Arrays.sort(n);

        int p1=k-1;
        int p2=0;
        int diff = 0;
        int min = Integer.MAX_VALUE;
        
        while(p1<n.length){ 
            
            diff = n[p1] - n[p2];
            if(diff<min) min = diff;

            p1++; p2++;
        }

        return min;
    }
}
```

### [3115. Maximum Prime Difference](https://leetcode.com/problems/maximum-prime-difference)

```Java
class Solution {
    public int maximumPrimeDifference(int[] nums) {
        
        int first = -1;
        int last = -1;

        for(int i=0;i<nums.length;i++){
            if(first == -1 && isPrime(nums[i])){
                first = i;
            }
            if(first != -1 && isPrime(nums[i])){
                last = i;
            }
        }

        if(first != -1 && last != -1) return last-first;
        return 0;


    }
    public static boolean isPrime(int n){
        if(n < 2){
            return false;
        }
        int i=2;
        while(i <= Math.sqrt(n)){

            if(n%i == 0){
                return false;
            }
            i++;
        }
        return true;
    }
}
```

### [2610. Convert an Array Into a 2D Array With Conditions](https://leetcode.com/problems/convert-an-array-into-a-2d-array-with-conditions/)

```Java
class Solution {
    public List<List<Integer>> findMatrix(int[] n) {
        
        Map<Integer,Integer> mp = new HashMap<>();
        int max = Integer.MIN_VALUE;
        
        for(int i=0;i<n.length;i++){
            mp.put(n[i],mp.getOrDefault(n[i],0)+1);
            if(max < mp.get(n[i])) max = mp.get(n[i]);
        }

        List<List<Integer>> rs = new ArrayList<>();
        int count = 1;

        for(int i=0;i<max;i++){
            List<Integer> ls = new ArrayList<>();
            List<Integer> rem = new ArrayList<>();

            for(Map.Entry<Integer,Integer> entry : mp.entrySet()){
                ls.add(entry.getKey());
                if(entry.getValue() == count){
                    rem.add(entry.getKey());
                }
            }
            for(int j=0;j<rem.size();j++){
                mp.remove(rem.get(j));
            }
            rs.add(ls);
            count++;      
        }
        return rs;
    }
}
```

### [73. Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes)

```Java
class Solution {
    public void setZeroes(int[][] m) {
        int[] c = new int[m.length];
        int[] r = new int[m[0].length];

        for(int i=0;i<m.length;i++){
            for(int j=0;j<m[i].length;j++){
                if(m[i][j] == 0) {
                    r[j] = -1;
                    c[i] = -1; 
                }
            }
        }

        for(int i=0;i<m.length;i++){
            for(int j=0;j<m[i].length;j++){
                if(r[j] == -1 || c[i] == -1){
                    m[i][j] = 0;
                }
            }
        }
    }
}
```

### [54. Spiral Matrix](https://leetcode.com/problems/spiral-matrix/)

```Java
class Solution {
    public List<Integer> spiralOrder(int[][] m) {
        List<Integer> ls = new ArrayList<>();

        int row = 0,rowMax = m.length-1;
        int col = 0,colMax = m[0].length-1;

        while(row<=rowMax && col<=colMax){
            for(int i=col;i<=colMax;i++){
                ls.add(m[row][i]);
            } row++;

            for(int i=row;i<=rowMax;i++){
                ls.add(m[i][colMax]);
            } colMax--;

            if(row<=rowMax){
                for(int i=colMax;i>=col;i--){
                    ls.add(m[rowMax][i]);
                } 
            }rowMax--;
            
            if(col<=colMax){
                for(int i=rowMax;i>=row;i--){
                    ls.add(m[i][col]);
                } 
            } col++;
        }
        return ls;
    }
}
```

### [59. Spiral Matrix II](https://leetcode.com/problems/spiral-matrix-ii/)

```Java
class Solution {
    public int[][] generateMatrix(int n) {
        int ar[][] = new int[n][n];

        int val = 1;

        int row=0,rowMax=n-1;
        int col=0,colMax=n-1;

        while(row<=rowMax && col<=colMax){

            for(int i=col;i<=colMax;i++){
                ar[row][i] = val;
                val++;
            }  row++;

            for(int i=row;i<=rowMax;i++){
                ar[i][colMax] = val;
                val++;
            }  colMax--;

            if(row<=rowMax){
                for(int i=colMax;i>=col;i--){
                    ar[rowMax][i] = val;
                    val++;
                }
            } rowMax--;

            if(col <= colMax){
                for(int i=rowMax;i>=row;i--){
                    ar[i][col] = val;
                    val++;
                }
            }col++;
        }
        return ar;
    }
}
```

### [946. Validate Stack Sequences](https://leetcode.com/problems/validate-stack-sequences/)

```Java
class Solution {
    public boolean validateStackSequences(int[] pu, int[] po) {
        Stack<Integer> st = new Stack<>();

        int p1=0,p2=0;

        while(p1<pu.length || p2<po.length){
            
            if(!st.isEmpty() && st.peek() == po[p2]){
                st.pop();
                p2++;
            }else if(p1<pu.length){
                st.push(pu[p1]);
                p1++;
            }else return false;
            
        }
        return true;
    }
}
```

### [904. Fruit Into Baskets](https://leetcode.com/problems/fruit-into-baskets/)

```Java
class Solution {
    public int totalFruit(int[] fruits) {
        Map<Integer,Integer> mp = new HashMap<>();

        int p1 = 0,p2=0;
        while(p2<fruits.length){
            mp.put(fruits[p2],mp.getOrDefault(fruits[p2],0)+1);

            if(mp.size()>2){
                mp.put(fruits[p1],mp.get(fruits[p1])-1);
                mp.remove(fruits[p1++],0);
            }
            p2++;
        }
        return p2-p1;
    }
}
```

### [735. Asteroid Collision](https://leetcode.com/problems/asteroid-collision/)

```Java
class Solution {
    public int[] asteroidCollision(int[] a) {
        
        Stack<Integer> st = new Stack<>();
        int i=0;

        while(i<a.length){

            if(st.isEmpty()){
                st.push(a[i]);
                i++;
            }else{

                if(st.peek() > 0 && a[i] < 0){

                    if(Math.abs(st.peek()) > Math.abs(a[i])){
                        i++;
                    }else if(Math.abs(st.peek()) < Math.abs(a[i])){
                        st.pop();
                    }else{
                        st.pop();
                        i++;
                    }

                }else{
                    st.push(a[i]);
                    i++;
                }

            }

        }

        int[] ar = new int[st.size()];
        i = ar.length-1;

        while(!st.isEmpty()){

            ar[i] = st.pop();
            i--;
        }
        return ar;
    }
}
```

### [739. Daily Temperatures](https://leetcode.com/problems/daily-temperatures/)

```Java
class Solution {
    public int[] dailyTemperatures(int[] tp) {
        
        Stack<Integer> st = new Stack<>();
        int[] res = new int[tp.length];

        for(int i=0;i<tp.length;i++){

            if(st.isEmpty()){
                st.push(i);
            }
            else{
                while(!st.isEmpty() && tp[st.peek()] < tp[i]){
                    res[st.peek()] = i-st.pop(); 
                }
                st.push(i);
            }
        }
        return res;
    }
}
```

### [209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)

```Java
class Solution {
    public int minSubArrayLen(int target, int[] nums) {
        int p1=0,p2=0;
        int sum = 0;
        int minCount = Integer.MAX_VALUE;

        while(p2<nums.length){
            sum += nums[p2];

            while(sum >= target){
                if(minCount > (p2-p1 + 1)) minCount = p2-p1+1;
                sum -= nums[p1];  p1++;
            }
            p2++;
        }

        if(minCount == Integer.MAX_VALUE) return 0;
        return minCount;
    }
}
```

### [867. Transpose Matrix](https://leetcode.com/problems/transpose-matrix/)

```Java
class Solution {
    public int[][] transpose(int[][] m) {
        int n = m.length;
        int o = m[0].length;

        int[][] ar = new int[o][n];

        for(int i=0;i<n;i++){
            for(int j=0;j<o;j++){
                ar[j][i] = m[i][j];
            }
        }
        System.gc();
        return ar;
    }
}
```

### [905. Sort Array By Parity](https://leetcode.com/problems/sort-array-by-parity/)

```Java
class Solution {
    public int[] sortArrayByParity(int[] nums) {
        int i=0,j=nums.length-1;

        while(i<j){
            while(i < j && nums[i]%2 == 0){
                i++;
            }
            while(i<j && nums[j]%2 == 1){
                j--;
            }

            int temp = nums[i];
            nums[i] = nums[j];
            nums[j] = temp;
        }
        return nums;
    }
}
```

### [2149. Rearrange Array Elements by Sign](https://leetcode.com/problems/rearrange-array-elements-by-sign/)

```Java
class Solution {
    public int[] rearrangeArray(int[] nums) {
        
        int res = 0;
        int[] ar = new int[nums.length];
        int pn = 0,nn = 1;

        for(int i=0;i<nums.length;i++){

            if(nums[i] > 0){
                ar[pn] = nums[i];
                pn+=2;
            }
            else if(nums[i] < 0){
                ar[nn] = nums[i];
                nn+=2;
            }
        }
        return ar;
    }
}
```

### [349. Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/description/)

```Java
class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
        Set<Integer> st1 = new HashSet<>();

        for(int n : nums1){
            st1.add(n);
        }

        Set<Integer> st2 = new HashSet<>();

        for(int n : nums2){
            if(st1.contains(n)) st2.add(n);
        }

        int[] ar = new int[st2.size()];
        int i =0;
        for(int n : st2){
            ar[i] = n;
            i++;
        }

        return ar;
    }
}
```

### [350. Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)

```Java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        Map<Integer,Integer> mp = new HashMap<>();

        for(int n :  nums1){
            mp.put(n,mp.getOrDefault(n,0)+1);
        }

        List<Integer> ls = new ArrayList<>();

        for(int n : nums2){
            if(mp.containsKey(n)){
                ls.add(n);
                mp.put(n,mp.get(n)-1);
                if(mp.get(n) == 0) mp.remove(n);
            }
        }
        
        int[] arr = new int[ls.size()];
        for(int i=0;i<ls.size();i++){
            arr[i] = ls.get(i);
        }
        return arr;
    }
}
```

### [958. Length of Longest Subarray With at Most K Frequency](https://leetcode.com/problems/length-of-longest-subarray-with-at-most-k-frequency/description/)

```Java
class Solution {
    public int maxSubarrayLength(int[] nums, int k) {

       int p1 = 0;
       int p2 = 0;

        Map<Integer,Integer> mp = new HashMap<>();
        int res = 0;

        while(p2<nums.length){
            
            mp.put(nums[p2],mp.getOrDefault(nums[p2],0)+1);

            while(mp.containsKey(nums[p2]) && mp.get(nums[p2]) > k) {
                mp.put(nums[p1], mp.get(nums[p1]) - 1);
                p1++;
            }

            if((p2-p1+1)>res) res = p2-p1+1;
            
            p2++;
        }
        return res;
    }
}
```

### [Find Peak Element](https://leetcode.com/problems/find-peak-element/)
```Java
class Solution {
    public int findPeakElement(int[] nums) {
        
        int l=0,r=nums.length-1;

        while(l<=r){
            int m = l + (r-l)/2;

            int left = m-1 == -1 ? Integer.MIN_VALUE : nums[m-1];
            int right = m+1 == nums.length ? Integer.MIN_VALUE : nums[m+1];

            if(nums[m]>left && right<nums[m]) return m;
            else if(nums[m]<left) r = m-1;
            else l = m+1;
        }

        return 0;
    }
}
```


### [1913. Maximum Product Difference Between Two Pairs](https://leetcode.com/problems/maximum-product-difference-between-two-pairs/description/)
```Java
class Solution {
    public int maxProductDifference(int[] nums) {
        
        Arrays.sort(nums);

        int n = nums.length;
        return (nums[n-1]*nums[n-2])-(nums[0]*nums[1]);
    }
}
```

### [1598. Crawler Log Folder](https://leetcode.com/problems/crawler-log-folder/)

```Java
class Solution {
    public int minOperations(String[] logs) {
        int res = 0;
        for(int i=0;i<logs.length;i++){
            if(logs[i].contains("../")){
                if(res > 0) res--;
            }else if(logs[i].contains("./")) continue;
            else{
                res++;
            }
        }
        return res;
    }
}
```

### [80. Remove Duplicates from Sorted Array II](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/)

```Java
class Solution {
    public int removeDuplicates(int[] n) {
        
        Map<Integer,Integer> mp = new HashMap<>();

        for(int i=0;i<n.length;i++){

            mp.put(n[i],mp.getOrDefault(n[i],0)+1);            
            if(mp.get(n[i]) > 2) mp.put(n[i],2);

        }

        int j=0;
        for(int i=0;i<n.length;i++){
            if(mp.get(n[i]) != null && mp.get(n[i]) <= 2){
                n[j] = n[i]; j++;

                mp.put(n[i],mp.get(n[i])-1);
                if(mp.get(n[i]) == 0) mp.remove(n[i]);
            }
        }
        return j;
    }
}
```

### [658. Find K Closest Elements](https://leetcode.com/problems/find-k-closest-elements/)

```Java
class Solution {
    public List<Integer> findClosestElements(int[] arr, int k, int x) {
        
        int l=0,r=arr.length-1;

        while(r-l >= k){
            
            if(Math.abs(arr[l] - x) > Math.abs(arr[r] - x)){
                l++;
            }else{
                r--;
            }
        }

        List<Integer> ls = new ArrayList<>();
        for(int i=l;i<=r;i++){
            ls.add(arr[i]);
        }
        return ls;
    }
}
```

### [2751. Robot Collisions](https://leetcode.com/problems/robot-collisions/description/)

```Java
class Solution {
    public List<Integer> survivedRobotsHealths(int[] p, int[] h, String d) {
        
        List<Integer> no = new ArrayList<>();
        for(int i=0;i<p.length;i++){
            no.add(i);
        }
        no.sort((a,b) -> Integer.compare(p[a],p[b]));

        Deque<Integer> st = new ArrayDeque<>();

        for(int i : no){
            if(d.charAt(i) == 'R'){
                st.push(i);
                continue;
            }
            while (!st.isEmpty() && h[i] > 0) {
                if (h[st.peek()] < h[i]) {
                    h[st.pop()] = 0;
                    h[i] -= 1;
                }else if(h[st.peek()] > h[i]){
                    h[st.peek()] = h[st.peek()]-1;
                    h[i] = 0;
                }else{
                    h[st.pop()] = 0;
                    h[i] = 0;
                }
            }
        }

        List<Integer> res = new ArrayList<>();
        for(int i : h){
            if(i > 0){
                res.add(i);
            }
        }
        return res;
    }
}
```

### [948. Bag of Tokens](https://leetcode.com/problems/bag-of-tokens/)

```Java
class Solution {
    public int minimumLength(String s) {
        int l = 0,r = s.length()-1;
        // StringBuilder fr = new StringBuilder()

        while(l<r && s.charAt(l) == s.charAt(r)){
           
            char ch = s.charAt(r);
            while(l<=r && s.charAt(l) == ch ){
                l++;
            }
            while(l<=r && s.charAt(r) == ch ){
                r--;
            }
        }
        return r-l+1 > 0 ? r-l+1 : 0;
    }
}
```


### [1750. Minimum Length of String After Deleting Similar Ends](https://leetcode.com/problems/minimum-length-of-string-after-deleting-similar-ends/)

```Java
class Solution {
    public int minimumLength(String s) {
        int l = 0,r = s.length()-1;
        // StringBuilder fr = new StringBuilder()

        while(l<r && s.charAt(l) == s.charAt(r)){
           
            char ch = s.charAt(r);
            while(l<=r && s.charAt(l) == ch ){
                l++;
            }
            while(l<=r && s.charAt(r) == ch ){
                r--;
            }
        }
        return r-l+1 > 0 ? r-l+1 : 0;
    }
}
```

### [1380. Lucky Numbers in a Matrix](https://leetcode.com/problems/lucky-numbers-in-a-matrix/description/)

```Java
class Solution {
    public List<Integer> luckyNumbers (int[][] m) {

        List<Integer> ls = new ArrayList<>();
            
        for(int i=0;i<m.length;i++){

            int minInd = 0;

            for(int j=0;j<m[i].length;j++){

                if(m[i][minInd] > m[i][j]){
                    minInd = j;
                }

            }

            boolean flag = true;
            for(int j=0;j<m.length;j++){

                if(m[i][minInd] < m[j][minInd]){
                    flag = false;
                }

            }
            
            if(flag) ls.add(m[i][minInd]);
        }
        return ls;
    }
}
```