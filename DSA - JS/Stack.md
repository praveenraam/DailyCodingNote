Know this before : [[Map]]
Next Topic : [[Queue]]

- The stack data structure is a sequential collection of elements that follows the principle of Last In First Out (LIFO)
- The last element inserted into the stack is first element to be removed
- A stack of plates. The last plate placed on top of the stack is also the first plate removed from the stack.
- Stack is an abstract data type. It is defined by its behavior rather than being a mathematical model
- The Stack data structure supports two main operations

#### Main Actions 
• Push, which adds an element to the collection
• Pop, which removes the most recently added element from the collection

#### Usage :
- Browser history tracking
- Undo operation when typing
- Expression conversions
- Call stack in JavaScript runtime



#### Stack Implementation
- push(element) - add an element to the top of the stack
- pop() - remove the top most element from the stack
- peek() - get the value of the top element without removing it
- isEmpty() - check if the stack is empty
- size() - get the number of elements in the stack
- print() - visualize the elements in the stack

```js
class Stack {

    constructor(){
        this.items = []
    }
    push(element){
        this.items.push(element)
    }
    pop(){
        return this.items.pop();
    }
    peek(){
        return this.items[this.items.length-1]
    }
    isEmpty(){
        return this.items.length === 0;
    }
    size(){
        return this.items.length;
    }
    print(){
        console.log(`Element in the Stack : ${this.items.toString()}`)
    }
}
const Stack1 = new Stack;

console.log(`Is the stack empty : ${Stack1.isEmpty()}`)

Stack1.push(3);
Stack1.push(6);
Stack1.push(5);

Stack1.print();

console.log(`Stack size : ${Stack1.size()}`)
console.log(`Element Popped : ${Stack1.pop()}`)
console.log(`Element Popped : ${Stack1.pop()}`)

/*
Is the stack empty : true
Element in the Stack : 3,6,5
Stack size : 3
Element Popped : 5
Element Popped : 6
*/

```

