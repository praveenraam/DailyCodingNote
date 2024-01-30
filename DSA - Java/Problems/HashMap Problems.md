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
