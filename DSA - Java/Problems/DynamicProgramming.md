
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

### [746. Min Cost Climbing Stairs](https://leetcode.com/problems/min-cost-climbing-stairs/description/)

```Java
class Solution {
    HashMap<Integer,Integer> mp = new HashMap<>();
    public int minCostClimbingStairs(int[] c) {
        int one = func(c,0);
        int two = func(c,1);
        return Math.min(one,two);        
    }
    public int func(int[] c,int i){

        if(i >= c.length) return 0;

        int one;
        if(!mp.containsKey(i+1)){
            one = func(c,i+1)+c[i];
        }else 
            one = mp.get(i+1)+c[i];

        int two;
        if(!mp.containsKey(i+2)){
            two = func(c,i+2)+c[i];
        }
        else two = mp.get(i+2)+c[i];

        mp.put(i,Math.min(one,two));
        return mp.get(i);
    } 
}
```

### [5. Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/description/)

```Java
class Solution {
    public String longestPalindrome(String s) {
        StringBuilder sb = new StringBuilder();
        sb.append(s.charAt(0));
        for(int i=0;i<s.length();i++){
            String od = func(s,i,i);
            String ev = func(s,i,i+1);

            if(od.length() > sb.length()) sb = new StringBuilder(od);
            if(ev.length() > sb.length()) sb = new StringBuilder(ev);
        }
        return sb.toString();
    }   
    public String func(String s,int left,int right){
        while(left>=0 && right <s.length() && s.charAt(left) == s.charAt(right)){
            left--; right++;
        }
        return s.substring(left+1,right);
    }
}
```

### [55. Jump Game](https://leetcode.com/problems/jump-game/description/)

```Java
class Solution {
    public boolean canJump(int[] nums) {
        int i=0;
        int max = 0;

        while(i<nums.length-1){
            if(max<i) return false; 
            int val = i+nums[i++];
            max = Math.max(val,max);
        }
        return max>=nums.length-1;
    }
}
```