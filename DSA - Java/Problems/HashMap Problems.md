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

### [705. Design HashSet](https://leetcode.com/problems/design-hashset/description/)

```Java
class MyHashSet {
    Map<Integer,Boolean> mp;
    public MyHashSet() {
        mp = new HashMap<>();
    }
    
    public void add(int key) {
        mp.put(key,true);
    }
    
    public void remove(int key) {
        mp.remove(key);
    }
    
    public boolean contains(int key) {
        return mp.containsKey(key);
    }
}

/**
 * Your MyHashSet object will be instantiated and called as such:
 * MyHashSet obj = new MyHashSet();
 * obj.add(key);
 * obj.remove(key);
 * boolean param_3 = obj.contains(key);
 */
```

### [706. Design HashMap](https://leetcode.com/problems/design-hashmap/description/)

```Java
class MyHashMap {

    int[] ar;

    public MyHashMap() {
        ar = new int[1000001];
        for(int i=0;i<ar.length;i++) ar[i] = -1;
    }
    

    public void put(int key, int value) {
        ar[key] = value;
    }
    
    public int get(int key) {
        return ar[key] == -1 ? -1 : ar[key];
    }
    
    public void remove(int key) {
        ar[key] = -1;
    }
}

/**
 * Your MyHashMap object will be instantiated and called as such:
 * MyHashMap obj = new MyHashMap();
 * obj.put(key,value);
 * int param_2 = obj.get(key);
 * obj.remove(key);
 */
```

### [1603. Design Parking System](https://leetcode.com/problems/design-parking-system/description/)

```Java
class ParkingSystem {
    int[] ar = new int[3];

    public ParkingSystem(int big, int medium, int small) {
        ar[0] = big;
        ar[1] = medium;
        ar[2] = small;
    }
    
    public boolean addCar(int carType) {
        
        if(ar[carType-1] == 0) return false;
        ar[carType-1] -= 1;
        return true;
    }
}

/**
 * Your ParkingSystem object will be instantiated and called as such:
 * ParkingSystem obj = new ParkingSystem(big, medium, small);
 * boolean param_1 = obj.addCar(carType);
 */
```