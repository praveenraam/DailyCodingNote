

### [215. Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/description/)

```Java
class Solution {
    public int findKthLargest(int[] nums, int k) {
        PriorityQueue<Integer> heap = new PriorityQueue<>(Collections.reverseOrder());

        for(int i : nums){
            heap.offer(i);
        }
        
        for(int i=k-1;i>0;i--){
            heap.poll();
        }
        return heap.peek();
    }
}
```

### [Last Stone Weight](https://leetcode.com/problems/last-stone-weight/description/)

```Java
class Solution {
    public int lastStoneWeight(int[] stones) {
        PriorityQueue<Integer> heap = new PriorityQueue<>(Collections.reverseOrder());
        
        for(int n : stones){
            heap.offer(n);
        }

        while(heap.size() != 1 && heap.size() != 0){

            int v1 = heap.poll();
            int v2 = heap.poll();

            if(v1 == v2) continue;
            
            int val = Math.abs(v1-v2);
            heap.offer(val);

        }
        return heap.size() == 1 ? heap.peek() : 0;
    }
}
```

### [K Closest Points to Origin](https://leetcode.com/problems/last-stone-weight/description/)

```Java
class Solution {
    public int[][] kClosest(int[][] points, int k) {
        PriorityQueue<int[]> heap = new PriorityQueue<>((a,b) -> Integer.compare(a[0]*a[0]+a[1]*a[1],b[0]*b[0]+b[1]*b[1]));
    
        for(int[] n : points){
            heap.add(n);
        }

        int[][] res = new int[k][2];
        for(int i=0;i<k;i++){
            res[i] = heap.poll();
        }

        return res;
    }
}
```

### [Least Number of Unique Integers after K Removals](https://leetcode.com/problems/least-number-of-unique-integers-after-k-removals/description/)

```Java
class Solution {
    public int findLeastNumOfUniqueInts(int[] arr, int k) {
        HashMap<Integer,Integer> mp = new HashMap<>();

        for(int i : arr){
            mp.put(i,mp.getOrDefault(i,0)+1);
        }

        PriorityQueue<Integer> heap = new PriorityQueue<>((a,b)->Integer.compare(mp.get(a),mp.get(b)));
        
        for(int i : mp.keySet()){
            heap.offer(i);
        }

        while(!heap.isEmpty() && k>0){
            int val = mp.get(heap.peek());
            if(k < val) break;
            k-=val;
            heap.poll();
        }

        return heap.size();
    }
}
```

### [703. Kth Largest Element in a Stream](https://leetcode.com/problems/kth-largest-element-in-a-stream/)

```Java
class KthLargest {
    PriorityQueue<Integer> hp;
    int d;
    public KthLargest(int k, int[] nums) {
        d = k;
        hp = new PriorityQueue<>();
        for(int i:nums){
            
            hp.offer(i);
            if(hp.size() > k){
                hp.poll();
            }
        }
    }
    
    public int add(int val) {
        hp.add(val);
        if(hp.size() > d) hp.poll();  
        return hp.peek();
    }
}
```

### [1642. Furthest Building You Can Reach](https://leetcode.com/problems/furthest-building-you-can-reach/)

```Java
class Solution {
    public int furthestBuilding(int[] a, int bricks, int ladders) {
        int i=0;
        Queue<Integer> hp = new PriorityQueue<>(Collections.reverseOrder());

        for(i=0;i<a.length-1;i++){

            if(a[i] >= a[i+1]) continue;

            int diff = a[i+1]-a[i];

            if(diff <= bricks){
                bricks-=diff;
                hp.offer(diff);
            }
            else if(ladders > 0){
                
                if(!hp.isEmpty() && hp.peek() > diff){
                    bricks+=(hp.remove()-diff);
                    hp.offer(diff);
                }
                ladders--;
                
            }else break;
        }
        return i;
    }
}
```

### [621. Task Scheduler](https://leetcode.com/problems/task-scheduler/)

```Java
class Solution {
    public int leastInterval(char[] tasks, int n) {
        if(n == 0) return tasks.length;

        PriorityQueue<Integer> hp = new PriorityQueue<>(Collections.reverseOrder());
        
        int[] ar = new int[26];
        for(int i=0;i<tasks.length;i++){
            ar[(int)tasks[i]-'A']+=1;
        }

        for(int i=0;i<26;i++){
            if(ar[i] == 0) continue;
            hp.offer(ar[i]);
        }


        Queue<Pair<Integer,Integer>> q = new LinkedList<>();

        int i = 0;
        while(!hp.isEmpty() || !q.isEmpty()){
            i++;
            if(!hp.isEmpty()){
                int val = hp.poll();
                val--;
                if(val > 0) q.add(new Pair(val,i+n));
            }
            if(!q.isEmpty() && q.peek().getValue() == i){
                hp.add(q.poll().getKey());
            }
        }
        return i;
    }
}
```
### [Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/description/)

```Java
class Solution {
    public ListNode mergeKLists(ListNode[] lists) {
        Queue<Integer> hp = new PriorityQueue<>();

        for(ListNode res : lists){
            while(res != null){
                hp.offer(res.val);
                res = res.next;
            }
        }

        ListNode res = new ListNode();
        ListNode dup = res;
        while(!hp.isEmpty()){
            ListNode newOne = new ListNode(hp.poll());
            res.next = newOne;
            res = res.next;
        }

        return dup.next;
    }
}
```

### [Minimum Number Game](https://leetcode.com/problems/minimum-number-game/description/)

```Java
class Solution {
    public int[] numberGame(int[] nums) {
        Queue<Integer> hp = new PriorityQueue<>();
        int[] ar = new int[nums.length];

        for(int i=0;i<nums.length;i++) hp.offer(nums[i]);

        int i = 0;
        while(!hp.isEmpty()){
            int v1 = hp.poll();
            int v2 = hp.poll();

            ar[i++] = v2;
            ar[i++] = v1;
        }

        return ar;
    }
}
```

### [Seat Reservation Manager](https://leetcode.com/problems/seat-reservation-manager/)

```Java
class SeatManager {
    Queue<Integer> hp = new PriorityQueue<>();

    public SeatManager(int n) {
        for(int i=1;i<=n;i++){
            hp.offer(i);
        }
    }
    
    public int reserve() {
        return hp.poll();    
    }
    
    public void unreserve(int seatNumber) {
        hp.offer(seatNumber);
    }
}
```

### [Smallest Number in Infinite Set](https://leetcode.com/problems/smallest-number-in-infinite-set/)

```Java
class SmallestInfiniteSet {
    Queue<Integer> hp = new PriorityQueue<>();

    public SmallestInfiniteSet() {
        for(int i=1;i<=1000;i++){
            hp.offer(i);
        }
    }
    
    public int popSmallest() {
        return hp.poll();
    }
    
    public void addBack(int num) {
        if(hp.contains(num)) return;
        hp.offer(num);
    }
}
```

### [Single-Threaded CPU](https://leetcode.com/problems/single-threaded-cpu/description/)

```Java
class Solution {
    public int[] getOrder(int[][] tasks) {
        int[] res = new int[tasks.length];

        Queue<int[]> hp = new PriorityQueue<>((a,b)->Integer.compare(a[0],b[0]));
        
        int i = 0;
        for(int[] n: tasks){
            hp.offer(new int[] {n[0],n[1],i});
            i++;
        }

        Queue<int[]> q = new PriorityQueue<>((a, b) -> a[1] == b[1] ? a[2] - b[2] : a[1] - b[1]);

        int time = 0;
        i = 0;
        while(!hp.isEmpty() || !q.isEmpty()){
            
            if(q.isEmpty() && time < hp.peek()[0]){
                time = hp.peek()[0];
            }

            while(!hp.isEmpty() && hp.peek()[0] <= time){
                q.offer(hp.poll());
            }

            int[] val = q.poll();
            time+=val[1];
            res[i++] = val[2];
        }

        return res;
    }
}
```

### [Maximum Product of Two Elements in an Array](https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/)

```Java
class Solution {
    public int maxProduct(int[] nums) {
        Queue<Integer> hp = new PriorityQueue<>(Collections.reverseOrder());

        for(int i=0;i<nums.length;i++) hp.offer(nums[i]);

        return (hp.poll()-1)*(hp.peek()-1);

    }
}
```

### [K-th Smallest Prime Fraction](https://leetcode.com/problems/k-th-smallest-prime-fraction/description/)

```Java
class Solution {
    public int[] kthSmallestPrimeFraction(int[] arr, int k) {
        Queue<double[]> hp = new PriorityQueue<>((a,b)->Double.compare(a[0],b[0]));

        for(int i=0;i<arr.length;i++){
            for(int j=i+1;j<arr.length;j++){
                double dif = (double) (arr[i])/(arr[j]);
                hp.offer(new double[] {dif,(double)arr[i],(double)arr[j]});
            }
        }

        for(int i=1;i<k;i++) hp.poll();

        double[] res = hp.peek();

        return new int[] {(int)res[1],(int)res[2]};
    }
}
```

### [1561. Maximum Number of Coins You Can Get](https://leetcode.com/problems/maximum-number-of-coins-you-can-get/description/)

```Java
class Solution {
    public int maxCoins(int[] piles) {
        Queue<Integer> hp = new PriorityQueue<>(Collections.reverseOrder());

        for(int i : piles) hp.offer(i);

        int sum = 0;
        int count = 0;
        while(!hp.isEmpty()){
            if(count == hp.size()) return sum;
            hp.poll();
            sum+=hp.poll(); 
            count++;
        }
        return sum;
    }
}
```

### [Maximum Ice Cream Bars](https://leetcode.com/problems/maximum-ice-cream-bars/description/)

```Java
class Solution {
    public int maxIceCream(int[] costs, int coins) {
        PriorityQueue<Integer> hp = new PriorityQueue<>();

        for(int i : costs) hp.offer(i);
        int res = 0;
        while(!hp.isEmpty()){
            if(hp.peek() > coins) return res;
            coins-=hp.poll(); res++;
        }
        return res;
    }
}
```

### [The kth Factor of n](https://leetcode.com/problems/the-kth-factor-of-n/description/)

```Java
class Solution {
    public int kthFactor(int n, int k) {
        int res = 0;
        for(int i=1;i<=n;i++){
            if(n%i == 0) res++;
            if(res == k) return i;
        }
        return -1;
    }
}
```

### [Sort Vowels in a String](https://leetcode.com/problems/sort-vowels-in-a-string/description/)

```Java
class Solution {
    
    HashSet<Character> st = new HashSet<>();

    public String sortVowels(String s) {
        addData();
        PriorityQueue<Character> hp = new PriorityQueue<>((a,b)->Character.compare(b,a));

        for(int i=0;i<s.length();i++){
            if(isVowel(s.charAt(i))) hp.offer(s.charAt(i));
        }
        StringBuilder sb = new StringBuilder(s);  
        for(int i=s.length()-1;i>=0;i--){  
            if(isVowel(sb.charAt(i))){  
                sb.setCharAt(i, hp.poll());  
            }  
        } 
        return sb.toString();
    }
    public boolean isVowel(char ch){
        return st.contains(ch);
    }
    public void addData(){
        st.add('A'); st.add('a');
        st.add('E'); st.add('e');
        st.add('I'); st.add('i');
        st.add('O'); st.add('o');
        st.add('U'); st.add('u');
    }
}
```

### [Find the Kth Largest Integer in the Array](https://leetcode.com/problems/find-the-kth-largest-integer-in-the-array/description/)

```Java
import java.math.BigInteger;
import java.util.PriorityQueue;

class Solution {
    public String kthLargestNumber(String[] nums, int k) {
        PriorityQueue<BigInteger> hp = new PriorityQueue<>((a,b)->b.compareTo(a));

        for(int i=0;i<nums.length;i++){
            BigInteger no = new BigInteger(nums[i]);
            hp.offer(no);
        }
        for(int i=0;i<k-1;i++) hp.poll();

        return String.valueOf(hp.peek());
    }
}
```

### [912. Sort an Array](https://leetcode.com/problems/sort-an-array/description/)

```Java
class Solution {
    public int[] sortArray(int[] nums) {
        PriorityQueue<Integer> hp = new PriorityQueue<>();
        for(int i=0;i<nums.length;i++) hp.offer(nums[i]);
        for(int i=0;i<nums.length;i++) nums[i] = hp.poll();
        return nums;
    }
}
```