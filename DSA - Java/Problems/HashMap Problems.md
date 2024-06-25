### [Highest / Lowest Frequency Elements](https://www.codingninjas.com/studio/problems/k-most-occurrent-numbers_625382?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)
```Java
import java.util.*;
public class Solution {
    public static int[] getFrequencies(int[] v) {
        HashMap<Integer,Integer> Result = new HashMap<>();
        Arrays.sort(v);
        for(int i=0;i<v.length;i++){
            if(Result.get(v[i]) != null) Result.put(v[i],Result.get(v[i])+1);
            else Result.put(v[i],1);
        }
        int Max = Integer.MIN_VALUE;
        int MaxIndex = -1;
        int Min = Integer.MAX_VALUE;
        int MinIndex = -1;
        for(int i=0;i<v.length;i++){
            int number = Result.get(v[i]);
            if(Max < number) {
                Max = number; MaxIndex = v[i];
            }
            if(Min > number) {
                Min = number; MinIndex=v[i];
            }
        }
        return new int[]{MaxIndex,MinIndex};
    }
}
```

### [Highest / Lowest Frequency Elements](https://www.codingninjas.com/studio/problems/k-most-occurrent-numbers_625382?utm_source=striver&utm_medium=website&utm_campaign=a_zcoursetuf)

```Java
import java.util.*;
public class Solution {
    public static int[] getFrequencies(int[] v) {
        HashMap<Integer,Integer> Result = new HashMap<>();
        Arrays.sort(v);
        for(int i=0;i<v.length;i++){
            if(Result.get(v[i]) != null) Result.put(v[i],Result.get(v[i])+1);
            else Result.put(v[i],1);
        }
        int Max = Integer.MIN_VALUE;
        int MaxIndex = -1;
        int Min = Integer.MAX_VALUE;
        int MinIndex = -1;
        for(int i=0;i<v.length;i++){
            int number = Result.get(v[i]);
            if(Max < number) {
                Max = number; MaxIndex = v[i];
            }
            if(Min > number) {
                Min = number; MinIndex=v[i];
            }
        }
        return new int[]{MaxIndex,MinIndex};
    }
}
```

### [380. Insert Delete GetRandom O(1)](https://leetcode.com/problems/insert-delete-getrandom-o1/)

```Java
class RandomizedSet {

    private ArrayList<Integer> ls;
    private Map<Integer,Integer> mp;

    public RandomizedSet() {
        ls = new ArrayList<>();
        mp = new HashMap<>();
    }
    
    public boolean insert(int val) {
        if(mp.containsKey(val)) return false;

        ls.add(val);
        mp.put(val,ls.size()-1);
        return true;
    }
    
    public boolean remove(int val) {
        if(!mp.containsKey(val)) return false;

        int index = mp.get(val);
        ls.set(index,ls.get(ls.size()-1));
        mp.put(ls.get(index),index);
        ls.remove(ls.size()-1);
        mp.remove(val);

        return true;
    }
    
    public int getRandom() {
        Random rand = new Random();
        return ls.get(rand.nextInt(ls.size()));  
    }
}
```