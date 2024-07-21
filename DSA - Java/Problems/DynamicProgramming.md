
### [509. Fibonacci Number](https://leetcode.com/problems/fibonacci-number/description/)

```Java
class Solution {
    HashMap<Integer,Integer> memo;

    public int fib(int n) {
        memo = new HashMap<>();
        return help(n);
    }
    public int help(int n){

        if(n == 1 || n == 0) return n;

        if(memo.containsKey(n)) return memo.get(n);
        memo.put(n,help(n-1)+help(n-2));
        return memo.get(n);
    }
}
```

### [70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/description/)

```Java
class Solution {
    HashMap<Integer,Integer> mp = new HashMap<>();

    public int climbStairs(int n) {
        return help(n);
    }
    public int help(int n){
        if(n == 0 || n == 1) return 1;

        if(!mp.containsKey(n-1)) mp.put(n-1,help(n-1));
        if(!mp.containsKey(n-2)) mp.put(n-2,help(n-2)); 

        return mp.get(n-1)+mp.get(n-2);
    }
}
```

### [198. House Robber](https://leetcode.com/problems/house-robber/)

```Java
class Solution {
    HashMap<Integer,Integer> mp = new HashMap<>();

    public int rob(int[] nums) {
        int n1 = help(0,nums.length,nums);
        int n2 = help(1,nums.length,nums);
        return Math.max(n1,n2);
    }

    public int help(int i,int n,int[] nums){
        if(i>=n) return 0;

        if(!mp.containsKey(i+2)) mp.put(i+2,help(i+2,n,nums));
        if(!mp.containsKey(i+3)) mp.put(i+3,help(i+3,n,nums));

        int n1 = mp.get(i+2)+(nums[i]);
        int n2 = mp.get(i+3)+(nums[i]);

        return Math.max(n1,n2);
    }
}
```