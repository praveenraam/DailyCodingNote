

### [21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/description/)

```Java
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        final ListNode root = new ListNode();

        ListNode prev = root;

        while(list1 != null && list2 != null){
            if(list1.val < list2.val){
                prev.next = list1;
                list1 = list1.next;
            }else{
                prev.next = list2;
                list2 = list2.next;
            }
            prev = prev.next;
        }
        prev.next = list1 != null ? list1 : list2;
        return root.next;

    }
}
```

### [206. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/description/)

```Java
class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode current = head;
        ListNode prev = null;
        ListNode next = null;

        while(current != null){
            next = current.next;
            current.next = prev;
            prev = current
            current = next;
        }

        return prev;

    }
}
```

### [876. Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)
```Java
class Solution {
    public ListNode middleNode(ListNode head) {
        int count = 0;
        ListNode dp = head;

        while(dp != null){
            count++;
            dp = dp.next;
        }
        
        count/=2;
        int i=0;

        while(i<count){
            head = head.next;
            i++;
        }
        return head;

    }
}
```

### [83. Remove Duplicates from Sorted List](leetcode.com/problems/remove-duplicates-from-sorted-list/)
```Java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        if(head == null){
            return head;
        }
        ListNode dup = head;

        while(dup.next != null){
            if(dup.val == dup.next.val){
                dup.next = dup.next.next;
            }
            else{
                dup = dup.next;
            }
        }

        return head;
    }
}
```

### [203. Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements)
```Java
class Solution {
    public ListNode removeElements(ListNode head, int val) {
        if(head == null){
            return head;
        }

        while(head!= null && head.val == val){
            head = head.next;
            if(head == null){
                return null;
            }
        }

        ListNode dup = head;
        while(dup.next != null){
            if(dup.next.val == val){
                dup.next = dup.next.next;
            } else{
                dup = dup.next;
            }
        }

        return head;
    }
}
```

### [2130. Maximum Twin Sum of a Linked List](https://leetcode.com/problems/maximum-twin-sum-of-a-linked-list/)

**Fast and Slow pointer method**

```Java
class Solution {
    public int pairSum(ListNode head) {
        ListNode slow = head;
        ListNode fast = head.next;

        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
        }

        ListNode curr = slow.next;
        ListNode prev = null;

        while(curr != null){
            ListNode temp = curr.next;
            curr.next = prev;
            prev = curr;
            curr = temp;
        }

        int max = Integer.MIN_VALUE;
        ListNode half = prev;

        while(half != null){
            int sum = (half.val + head.val);
            half = half.next;
            head = head.next;
            if(sum>max) max = sum;
        }

        return max;
    }
}
```

### [143. Reorder List](https://leetcode.com/problems/reorder-list/description/)

```Java
class Solution {
    public void reorderList(ListNode head) {
        ListNode slow = head;
        ListNode fast = head.next;

        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
        }


        ListNode second = slow.next;
        ListNode prev = slow.next = null;

        while(second != null){
            ListNode temp = second.next;
            second.next = prev;
            prev = second;
            second = temp;
        }

        ListNode first = head;
        second = prev;

        while(second != null){
            ListNode temp1 = first.next;
            ListNode temp2 = second.next;
            first.next = second;
            second.next = temp1;
            first = temp1;
            second = temp2;
        }

    }
}
```

### [1721. Swapping Nodes in a Linked List](https://leetcode.com/problems/swapping-nodes-in-a-linked-list/)

```Java
class Solution {

    public ListNode swapNodes(ListNode head, int k) {
    
        ListNode getFirst = head;
        int count = 0;

        while(count < k-1){
            getFirst = getFirst.next;
            count++;
        }  

        ListNode temp = getFirst;
        ListNode getLast = head;

        while(temp.next != null){
            temp = temp.next;
            getLast = getLast.next;
        }

        int swap = getLast.val;
        getLast.val = getFirst.val;
        getFirst.val = swap;

        return head;  

    }
}
```

### [19. Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

```Java
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {

        if (head == null || head.next == null) return null;
        ListNode temp = new ListNode(0);
        temp.next = head;
        ListNode p1 = temp;
        ListNode p2 = temp;

        while(n >0){
            p2 = p2.next;
            n--;
        }

        while(p2.next != null){
            p1 = p1.next;
            p2 = p2.next;
        }
        p1.next = p1.next.next;
        return temp.next;  
    }
}
```

### [707. Design Linked List](https://leetcode.com/problems/design-linked-list/)

```Java
class MyLinkedList {
    ListNode head;
    int size;

    public class ListNode{
        int val;
        ListNode next;

        ListNode(int val){
            this.val = val;
        }
    }

    public MyLinkedList() {
        this.head = null;
        this.size = 0;
    }
    
    public int get(int index) {
        if(index < 0 || index >= this.size) return -1;
        
        ListNode curr = this.head;
        while(index-- > 0){
            curr = curr.next;
        }
        return curr.val;
    }
    
    public void addAtHead(int val) {
        ListNode newHead = new ListNode(val);
        newHead.next = head;
        head = newHead;
        size++;
    }
    
    public void addAtTail(int val) {
        if(head == null) {
        	addAtHead(val);
            return;
        }
        ListNode traverse = head;
        while(traverse.next != null){
            traverse = traverse.next;
        }

        ListNode newNode = new ListNode(val);
        traverse.next = newNode;
        size++;

    }
    
    public void addAtIndex(int index, int val) {
        if(index > size){
            return;
        }
        else if(index == 0){

            ListNode newHead = new ListNode(val);
            newHead.next = head;
            head = newHead;
            size++;
            return;

        }else if(size == index){

            ListNode traverse = head;
            while(traverse.next != null){
                traverse = traverse.next;
            }

            ListNode newNode = new ListNode(val);
            traverse.next = newNode;
            size++;
            return;

        }else{

            int count = 1;
            ListNode prev = null;
            ListNode cur = head;
            size++;

            while(count <= index){
                prev = cur;
                cur = cur.next;
                count++;
            }
            ListNode newNode = new ListNode(val);
            prev.next = newNode;
            newNode.next =  cur;
            size++;
            return;
        }
    }
    
    public void deleteAtIndex(int index) {

        if(index>=size){
            return;
        }
        
        if(index == 0){
            head = head.next;
            size--;
        }else{
            int count = 1;
            ListNode prev = null;
            ListNode cur = head;

            while(count <= index){
                prev = cur;
                cur = cur.next;
                count++;
            }

            prev.next = cur.next;
            size--;
        }
    }
}
```

### [141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)

```Java
public class Solution {
    public boolean hasCycle(ListNode head) {
        Set<ListNode> st = new HashSet<>();

        while(head != null){
            
            if(st.contains(head)) return true;
            st.add(head);

            head = head.next;

        }

        return false;

    }
}
```

### [Sort List](https://leetcode.com/problems/sort-list/)
```Java
class Solution {
    public ListNode sortList(ListNode head) {
        int count = 0;
        ListNode temp = head;

        while(temp != null){
            count++; temp = temp.next;
        }

        int[] arr = new int[count];
        temp = head;

        for(int i=0;i<count;i++){
            arr[i] = temp.val;
            temp = temp.next;
        }

        Arrays.sort(arr);
        temp = head;
        for(int i=0;i<count;i++){
            temp.val = arr[i];
            temp = temp.next;
        }

        return head;

    }
}
```

### [Rotate List](https://leetcode.com/problems/rotate-list/)

```Java
class Solution {
    public ListNode rotateRight(ListNode head, int k) {

        if(head == null) return null;
        

        int len = 0;
        ListNode forCount = head;

        while(forCount != null){
            len++;  forCount = forCount.next;
        }

        if(len == k) return head;

        k = k%len;
        int diff = (len - k)+1;

        int count = 0;
        forCount = head;

        ListNode res = new ListNode(0);
        ListNode dupPoint = res;

        while(forCount != null){
            count++;

            if(count>=diff){
                ListNode newNode = new ListNode(forCount.val);
                dupPoint.next = newNode;
                dupPoint = dupPoint.next; 
            }

            forCount = forCount.next;
        }
        
        count=1;
        forCount = head;
        while(count<diff){
            ListNode newNode = new ListNode(forCount.val);
            dupPoint.next = newNode;

            dupPoint = dupPoint.next;
            forCount = forCount.next;

            count++;
        }

        return res.next;
    }
}
```


### [Partition List](https://leetcode.com/problems/partition-list/)
```Java
class Solution {
    public ListNode partition(ListNode head, int x) {
        ListNode res = new ListNode(0);
        ListNode resDup = res;
        ListNode temp = head;

        while(temp != null){
            if(temp.val < x){
                ListNode newOne = new ListNode(temp.val);
                resDup.next = newOne;
                resDup = resDup.next;
            }
            temp = temp.next;
        }

        temp = head;

        while(temp != null){
            if(temp.val >= x){
                ListNode newOne = new ListNode(temp.val);
                resDup.next = newOne;
                resDup = resDup.next;
            }
            temp = temp.next;
        }
        
        return res.next;
    }
}
```

### [147. Insertion Sort List](https://leetcode.com/problems/insertion-sort-list/)
```Java
class Solution {
    public ListNode insertionSortList(ListNode head) {
        
        ListNode temp = head;
        int count = 0;

        while(temp.next != null){
            count++;
            temp = temp.next;
        }

        temp = head;
        int n = count;
        while(count>0){
            
            temp = head;
            ListNode cur = temp.next;

            while(cur != null && n>){
                
                int fr = temp.val;
                int sc = cur.val;

                if(fr>sc){
                    int intTemp = temp.val;
                    temp.val = cur.val;
                    cur.val = intTemp;
                }

                temp = temp.next;
                cur = cur.next;

            }
            n--;
            count--;
        }

        return head;
    }
}
```

### [2. Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)

```Java
import java.util.*;

class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {

        ListNode rs = new ListNode(0);
        ListNode temp = rs;
        int bal = 0;
        ListNode t1 = l1,t2 = l2;

        while(t1 != null && t2 != null){

            int v1 = t1.val , v2 = t2.val;
            int sum = v1+v2+bal;

            if(sum >= 10){
                ListNode newOne = new ListNode(sum%10);
                temp.next = newOne;
                temp = temp.next;

                bal = 1;
            }else{

                ListNode newOne = new ListNode(sum);
                temp.next = newOne;
                temp = temp.next;

                bal = 0;
            }

            t1 = t1.next; t2 = t2.next;
        } 

        while(t1 != null){
            int v1 = t1.val;

            int sum = v1 + bal;

            if(sum >= 10){

                ListNode newOne = new ListNode(sum%10);
                temp.next = newOne;
                temp = temp.next;

                bal = 1;
            }else{

                ListNode newOne = new ListNode(sum);
                temp.next = newOne;
                temp = temp.next;

                bal = 0;
            }
            t1 = t1.next;
        }

        while(t2 != null){
            int v1 = t2.val;

            int sum = v1 + bal;

            if(sum >= 10){

                ListNode newOne = new ListNode(sum%10);
                temp.next = newOne;
                temp = temp.next;

                bal = 1;
            }else{

                ListNode newOne = new ListNode(sum);
                temp.next = newOne;
                temp = temp.next;

                bal = 0;
            }
            t2 = t2.next;
        }

        if(bal == 1){

            ListNode newOne = new ListNode(bal);
            temp.next = newOne;
            temp = temp.next;

        }
        return rs.next;
    }
}
```

### [1669. Merge In Between Linked Lists](https://leetcode.com/problems/merge-in-between-linked-lists)

```Java
class Solution {
    public ListNode mergeInBetween(ListNode list1, int a, int b, ListNode list2) {
        int count = 1;
        ListNode temp = list1;

        ListNode conn = null;
        ListNode address = null;

        while(temp != null){
            if(count == a){
                conn = temp;
            }
            if((count-1) == b){
                address = temp.next;
            }
            count++;
            temp = temp.next;
        }

        conn.next = list2;
        temp = list2;

        while(temp.next != null){
            temp = temp.next;
        }

        temp.next = address;

        return list1;
    }
}
```

### [2487. Remove Nodes From Linked List](https://leetcode.com/problems/remove-nodes-from-linked-list/)

```Java
class Solution {
    public ListNode removeNodes(ListNode head) {
        Stack<ListNode> st = new Stack<>();
        ListNode dup = head;

        while(dup!= null){
            while(!st.isEmpty() && st.peek().val < dup.val){
                st.pop();
            }
            st.push(dup);
            dup = dup.next;
        }   

        ListNode res = null;
        ListNode next = null;

        while(!st.isEmpty()){
            res = st.pop();
            res.next = next;
            next = res;
        }
        return res;
    }
}
```

### [234. Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/)

```Java
class Solution {
    public boolean isPalindrome(ListNode head) {
        List<Integer> ls = new ArrayList<>();
        ListNode temp = head;

        while(temp != null){
            ls.add(temp.val);
            temp = temp.next;
        }

        int p1 = 0,p2 = ls.size()-1;

        while(p1<=p2){
            if(ls.get(p1) != ls.get(p2)) return false;
            p1++; p2--;
        }
        return true;
    }
}
```

### [725. Split Linked List in Parts](https://leetcode.com/problems/split-linked-list-in-parts/)

```Java
class Solution {
    public ListNode[] splitListToParts(ListNode head, int k) {
        
        int count = countNo(head);
        
        int lenPerIndex = count/k;
        int extra = count%k;
        ListNode[]  ar = new ListNode[k];
        ListNode curr = head;

        for(int i=0;i<k;i++){

            ListNode temp = new ListNode(0); ListNode tempHead = temp;
            
            for(int j=0;j<lenPerIndex + (i<extra ? 1:0);j++){
                tempHead.next = new ListNode(curr.val);
                tempHead = tempHead.next;
                if(curr != null) curr = curr.next;
            }
            ar[i] = temp.next;
        }
        return ar;
    }

    public static int countNo(ListNode Head){
        int no = 0;
        while(Head != null){
            no++;
            Head = Head.next;
        }
        return no;
    }
}
```

### [1472. Design Browser History](https://leetcode.com/problems/design-browser-history/)

```Java
class ListNode{
    ListNode back;
    String url;
    ListNode forward;

    public ListNode(String url){
        this.url = url;
        back = forward;
        forward = null;
    }
}

class BrowserHistory {

    ListNode head;
    ListNode current;

    public BrowserHistory(String homepage) {
        head = new ListNode(homepage);
        current = head;
    }
    
    public void visit(String url) {
        current.forward = new ListNode(url);
        current.forward.back = current;
        current = current.forward;
    }
    
    public String back(int steps) {
        while(steps>0 && current.back != null){
            current = current.back;
            steps--;
        }
        return current.url;
    }
    
    public String forward(int steps) {
        while(steps>0 && current.forward != null){
            current = current.forward;
            steps--;
        }
        return current.url;
    }
}
```

### [25. Reverse Nodes in k-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/description/)

```Java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode reverseKGroup(ListNode head, int k) {
        ListNode dup = head;

        while(dup != null){
            reverse(dup,k);
            int i=0;
            while(i<k && dup != null){
                dup = dup.next;
                i++;
            }
        }
        return head;
    }
    public void reverse(ListNode head,int k){
        
        ListNode dup = head;
        Stack<Integer> st = new Stack<>();

        for(int i=0;i<k;i++){
            if(dup == null) return;
            st.push(dup.val);

            dup = dup.next;
        }

        dup = head;
        for(int i=0;i<k;i++){
            if(dup == null) return;
            dup.val = st.pop();
            dup = dup.next;
        }
    }
}
```


### [2181. Merge Nodes in Between Zeros](https://leetcode.com/problems/merge-nodes-in-between-zeros/description/)

```Java
class Solution {
    public ListNode mergeNodes(ListNode head) {
        if(head.next == null) return null;

        ListNode res = new ListNode();
        ListNode dup = res;
        int sum = 0;
        head = head.next;

        while(head.next != null){
            if(head.val == 0){
                ListNode newOne = new ListNode(sum);
                sum = 0;
                dup.next = newOne;
                dup = dup.next;
            } 
            else{
                sum+=head.val;
            }

            head = head.next;
        }
        ListNode newOne = new ListNode(sum);
        sum = 0;
        dup.next = newOne;
        return res.next;
    }
}
```

### [3217. Delete Nodes From Linked List Present in Array](https://leetcode.com/problems/delete-nodes-from-linked-list-present-in-array/description/)

```Java
class Solution {
    public ListNode modifiedList(int[] nums, ListNode head) {
        HashSet<Integer> st = new HashSet<>();

        for(int i=0;i<nums.length;i++){
            st.add(nums[i]);
        }

        ListNode dup = new ListNode();
        while(st.contains(head.val)){
            head = head.next;
        }
        dup = head;

        while(dup != null && dup.next != null){
            if(dup.next != null && st.contains(dup.next.val)){
                dup.next = dup.next.next;
                continue;
            }
            dup = dup.next;
        }

        return head;
    }
}
```

### [82. Remove Duplicates from Sorted List II](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/description/)

```Java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        
        ListNode dup = head;
        TreeMap<Integer,Integer> mp = new TreeMap<>();

        while(dup != null){
            mp.put(dup.val,mp.getOrDefault(dup.val,0)+1);
            dup = dup.next;
        }
        
        ListNode res = new ListNode();
        dup = res;

        for(int i : mp.keySet()){
            if(mp.get(i) == 1){
                ListNode newOne = new ListNode(i);
                res.next = newOne;
                res = res.next;
            }
        }

        return dup.next;
    }
}
```

### [1019. Next Greater Node In Linked List](https://leetcode.com/problems/next-greater-node-in-linked-list/description/)

```Java
class Solution {
    public int[] nextLargerNodes(ListNode head) {
        int size = 0;
        ListNode dup = head;

        while(dup != null){
            size++;
            dup = dup.next;
        }

        dup = head;
        int[] ar = new int[size];

        int i = 0;
        while(dup != null){

            int funcRes = findGreater(dup.next,dup.val);
            int val = dup.val >= funcRes ? 0 : funcRes;
            ar[i] = val; i++;
            dup = dup.next;
        }
        return ar;
    }
    public int findGreater(ListNode start,int cur){
        int max = 0;
        while(start != null){
            if(start.val > cur) return start.val;
            start = start.next;
        }
        return max;
    }
}
```

### [328. Odd Even Linked List](https://leetcode.com/problems/odd-even-linked-list/description/)

```Java
lass Solution {
    public ListNode oddEvenList(ListNode head) {
        ListNode dup = head;
        ListNode res = new ListNode();
        ListNode it = res;

        int count = 1;
        while(dup != null){
            if(count%2 == 1){
                ListNode nex = new ListNode(dup.val);
                it.next = nex;
                it = it.next;
            }
            dup = dup.next; count++;
        }

        count = 1;
        dup = head;
        while(dup!=null){
            if(count%2 == 0){
                ListNode nex = new ListNode(dup.val);
                it.next = nex;
                it = it.next;
            }
            dup = dup.next; count++;
        }

        return res.next;
    }
}
```

### [382. Linked List Random Node](https://leetcode.com/problems/linked-list-random-node/description/)

```Java
class Solution {
    List<Integer> ls;
    public Solution(ListNode head) {
        ls = new ArrayList<>();
        while(head != null){
            ls.add(head.val);
            head = head.next;
        }
    }
    
    public int getRandom() {
        int k =  (int)(Math.random()*ls.size());
        return ls.get(k);
    }
}
```

### [Add Two Numbers II](https://leetcode.com/problems/add-two-numbers-ii/description/)

```Java
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {

        if(l1 == null && l2 == null) return l1;

        Stack<Integer> st1 = new Stack<>();
        Stack<Integer> st2 = new Stack<>();

        while(l1 != null){
            st1.push(l1.val); l1 = l1.next;
        }
        while(l2 != null){
            st2.push(l2.val); l2 = l2.next;
        }

        Stack<Integer> res = new Stack<>();
        int carry = 0;
        while(!st1.isEmpty() && !st2.isEmpty()){
            int val = st1.pop()+st2.pop()+carry;
            carry = 0;
            if(val >= 10){
                carry = 1;
                val = val%10;
            }
            res.push(val);
        }
        
        while(!st1.isEmpty()){
            int val = st1.pop();
            if(carry == 1) {
                val+=carry;
                carry = 0;
                if(val>=10){
                    carry = 1;
                    val = val%10;
                }
            }
            res.push(val);
        }
        while(!st2.isEmpty()){
            int val = st2.pop();
            if(carry == 1) {
                val+=carry;
                carry = 0;
                if(val>=10){
                    carry = 1;
                    val = val%10;
                }
            }
            res.push(val);
        }
        if(carry == 1){
            System.out.println("in");
            res.push(1);
            carry = 0;
        }
        ListNode ans = new ListNode(res.pop());
        ListNode dup = ans;
        while(!res.isEmpty()){
            ListNode newOne = new ListNode(res.pop());
            dup.next = newOne; dup = newOne;
        }
        return ans;
    }
}
```