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
