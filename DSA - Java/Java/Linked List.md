Topic No : 20
Next Topic : [[Types of Tree]]
Video [Link](https://youtu.be/58YbpRDc4yw?si=feaZgsXsLzZKejEL)
### Why Linked List

- While array are fixed size , we can use the linked list 
- While using the array list , it doubles the size and copying it which makes it difficult to copying and using it
- So we use linked list

### How linked list works

- The linked list are randomly stored in the heap of the java and they are connected each other
- The prev element contains the address of the current element and current element contains the address of the next element 
- They contains the address of the next element and point it
- ![[Pasted image 20240513133638.png]]

### Word representation
- The First element is called as Head
- The last element is called as Tail
- The box that contains the element is called node, which itself a class

### Node
- It is a class that stores the value of the element
- It contains it own value and a variable next that contains the address of the next element

### We can't get the 5 or 6th indexed element directly , instead we iterate one by one, as the elements have no idea of the total element

### They only know about the next element , incase we need 4th element , we run loop 4 times

### Types of linked list

- Single Linked List : It is a one way list
- Double Linked List : It is a two way list , as we an move front and backwards

### Code for implementing single Linked List

```Java
public class LL {  
    private Node head;  
    private Node tail;  
    private int size;  
    
    public LL(){  
        this.size = 0;  
    }  
    
    public void insertFirst(int value){  
        Node node = new Node(value);  
        node.next = head;  
        head = node;  
        
        if(tail == null) tail = head;  
        
        size++;  
    }  
    public void display(){  
        Node temp = head;  
        while(temp != null){  
            System.out.print(temp.value + " -> ");  
            temp = temp.next;  
        }  
    }  
    public void add(int value){  
        if(tail == null){  
            insertFirst(value);  
            return;  
        }  
        Node node = new Node(value);  
        tail.next = node;  
        tail = node;  
        size++;  
    }  
    public void insertPosition(int value,int index){  
        if(index == 0) insertFirst(value);  
        if(index == size) add(value);  
        
        Node temp = head;  
        
        for(int i=1;i<index;i++){  
            temp = temp.next;  
        }  
        
        Node node = new Node(value,temp.next);  
        temp.next = node;  
        size++;  
    }  
    public int deleteHead(){  
        int val = head.value;  
        head = head.next;  
        if(head == null){  
            tail = null;  
        }  
        size--;  
          
        return val;  
    }  
    public int delete(int position){  
        if(position == 0) return deleteHead();  
        if(position == size-1) deleteTail();  
        
        Node prev = get(position - 1);  
        int val = prev.value;  
        
        prev.next = prev.next.next;  
        
        return val;  
    }  
    public int deleteTail(){  
        if(size <= 1) return deleteHead();  
        
        int val = tail.value;  
        Node secondLast = get(size-2);  
        tail = secondLast;  
        tail.next = null;  
        
        size--;  
        
        return val;  
    }  
    public int getSize(){  
        return size;  
    }  
    public Node get(int index){  
        Node node = head;  
        for(int i=0;i<index;i++){  
            node = node.next;  
        }  
        return node;  
    }  
    public Node find(int val){  
        Node node = head;  
        while(node != null){  
            if(node.value == val){  
                return node;  
            }  
            node = node.next;  
        }  
        return null;  
    }  
    private class Node{  
        private int value;  
        private Node next;  
        public Node(int value){  
            this.value = value;  
        }  
        public Node(int value,Node next){  
            this.value = value;  
            this.next = next;  
        }  
    }  
}
```

### Code for implementing Double linked list

```Java
  
public class DLL {  
    private Node head;  
    private Node tail;  
    private int size;  
  
    public DLL(){  
        this.size = 0;  
    }  
    public void insertFirst(int val){  
        Node node = new DLL.Node(val);  
  
        node.next = head;  
        node.prev = null;  
        if(head != null) head.prev = node;  
        head = node;  
    }  
    public void insertLast(int val){  
        Node node = new Node(val);  
        Node last = head;  
  
        node.next = null;  
  
        if(head == null){  
            node.prev = null;  
            head = node;  
            return;  
        }  
  
        while(last.next != null){  
            last = last.next;  
        }  
  
        last.next = node;  
        node.prev = last;  
  
        size++;  
    }  
    public void insert(int after,int val){  
        Node p = find(after);  
  
        if(p == null){  
            System.out.println("Doesn't exist");  
            return;  
        }  
        Node node = new Node(val);  
        node.next = p.next;  
        p.next = node;  
        node.prev = p;  
        if(node.next != null){  
            node.next.prev = node;  
        }  
  
    }  
    public Node find(int val){  
        Node node = head;  
        while(node != null){  
            if(node.value == val){  
                return node;  
            }  
        }  
        return node;  
    }  
    public void display(){  
        Node node = head;  
        while(node != null){  
            System.out.print(node.value + " ");  
            node = node.next;  
        }  
        System.out.println();  
    }  
  
    private class Node{  
        int value;  
        Node prev;  
        Node next;  
  
        public Node(int value){  
            this.value = value;  
        }  
        public Node(int value,Node next){  
            this.value = value;  
            this.next = next;  
        }  
    }  
}
```

### Code for implementing Circular linked list

```Java

```