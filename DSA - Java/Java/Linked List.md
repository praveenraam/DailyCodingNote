Topic No : 20
Next Topic : [[]]
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

### Code for implementing

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
    public void deleteHead(){  
          
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