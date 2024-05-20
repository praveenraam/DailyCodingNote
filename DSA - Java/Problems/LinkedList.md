

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