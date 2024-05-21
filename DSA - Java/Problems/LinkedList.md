

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
