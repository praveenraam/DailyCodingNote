Topic to know before : [[DSA - JS/Object]] 
Next Topic : [[Map]]

- A set is a data structure that can hold a collection of values. The values however
must be unique
- Set can contain a mix of different data types. You can store strings, boolean,
numbers or even objects all in the same set
- Sets are dynamically sized. You don't have to declare the size of a set before
creating it
- Sets do not maintain an insertion order
- Sets are iterable. They can be used with a for of loop


### Set vs Array
- Arrays can contain duplicate values whereas Sets cannot
- Insertion order is maintained in arrays but it is not the case with sets
- Searching and deleting an element in the set is faster compared to arrays

##### Set can be created using the constructor

```js

const sets = new Set([1,2,3,4,5,5,5,6]);

sets.add(7) // Can add 1 element using this method

console.log(`Is 6 present in set : ${sets.has(6)}`); // check whether number present or not

console.log(`Is 10 present in set : ${sets.has(10)}`); // check whether number present or not

sets.delete(6) // Delete the element from the set
console.log(`Size of the set : ${sets.size}`) // Gives the size of the set

for(const n of sets){
    console.log(n)
} 
sets.clear() // Delete the all element in sets
  
/* OUTPUT : 
Is 6 present in set : true
Is 10 present in set : false
Size of the set : 6
1
2
3
4
5
7
*/
```

