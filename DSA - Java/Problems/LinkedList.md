

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