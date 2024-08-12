

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