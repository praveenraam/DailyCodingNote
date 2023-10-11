Know this before : [[Stack]] 
Next topic : [[Circular Queue]]

- The queue data structure is a se uential collection of elements that follows the principle of First In First Out (FIF8)
- The first element inserted into the queue is first element to be removed
- A queue of people. People enter the queue at one end (rear/tail) and leave the queue from the other end (front/ head).
- Queue is an abstract data type. It is defined by its behavior rather than being a mathematical model


#### Main Actions

The Queue data structure supports two main operations

• Enqueue, which adds an element to the rear/tail of the collection
• Dequeue, which removes an element from the front/head of the collection

#### Usage 

- Printers
- CPU task scheduling
- Callback queue in JavaScript runtime

#### Queue Implementation

- enqueue(element) - add an element to the queue
- dequeue() - remove the oldest element from the queue
- peek() - get the value of the element at the front of the queue without removing it
- isEmpty() - check if the queue is empty
- size() - get the number of elements in the queue
- print() - visualize the elements in the queue

##### Using the array 

```js
class Queue {
    constructor() {
        this.items = []
    }
    enqueue(element){
        this.items.push(element)
    }
    dequeue(){
        this.items.shift() // Shift remove element from the front of the Array
    }
    isEmpty(){
        return this.items.length === 0;
    }
    peek(){
        if(!this.isEmpty()){
            return this.items[0]
        }
        return null;
    }
    size(){
        return this.items.length;
    }
    print(){
        console.log(`Element in the Queue : ${this.items.toString()}`)
    }
}
const Queue1 = new Queue;

Queue1.enqueue(10);
Queue1.enqueue(12);
Queue1.enqueue(100);
Queue1.enqueue(15);
Queue1.enqueue(9);

console.log(`The element in the front of the Queue : ${Queue1.peek()}`)
Queue1.dequeue();
console.log(`The element in the front of the Queue : ${Queue1.peek()}`)
Queue1.dequeue();

Queue1.print();
console.log(`The size of the Queue is ${Queue1.size()}`)
```

Used Queue in the array but the dequeue method have the time complexity of O(n) because of using the shift method inside the dequeue function that we have created

The dequeue and the Enqueue should have the time complexity of Big O Notation of O(1)

```js
class Queue {
    constructor() {
        this.items = {};
        this.rear = 0;
        this.front = 0;
    }
    enqueue(element){
        this.items[this.rear] = element;
        this.rear++;
    }
    dequeue(){
        const items = this.items[this.front];
        delete this.items[this.front]
        this.front++;
    }
    isEmpty(){
        return this.rear - this.front === 0;
    }
    peek(){
        return this.items[this.front]
    }
    size(){
        return this.rear - this.front
    }
    print(){
        console.log(this.items)
    }
} 
const Queue1 = new Queue;
console.log(`Is the Queue is empty : ${Queue1.isEmpty()}`)

Queue1.enqueue({Name:'Praveen',Age:12})
Queue1.enqueue({Name:'Tharun',Age:21})

console.log(`The element in the front : ${Queue1.peek()}`)
Queue1.print();

/*
Is the Queue is empty : true
{ '0': { Name: 'Praveen', Age: 12 }, '1': { Name: 'Tharun', Age: 21 } }
*/
```

