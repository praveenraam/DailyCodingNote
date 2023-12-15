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
