Topic no : 19
Next Topic : [[Linked List]]


#### All the collection types have own class declared and it's methods
## List 
- It allow us to work with an ordered collection and access objects using the index
- It works just like array
### Array List
- It is a dynamic form of Array , 
- When the array is full , it automatically resize the array and store the data
### Linked List
- It is based on the linked list data structure
## Set 
- The collection that only have unique values in it, without duplicates
`` Set<Integer> variable = new HashSet<>(); ``
- It does not have index values

``Set<Integer> variable = new HashSet<>();
- This stores the value in the sorted order

### HashSet
- The collection that is implemented without duplicates 
### Function : 
- ``set.add(variable/number)``
- ``set.remove();``

## Queue
- We use queue in the situation where we have a resource that is shared among a lot of consumers 
- Ex : printer in the store, you can give many inputs to print but it prints in an order of FIFO which is queue
## Map

- It allow us to store the multiple data type in it
- For example : Storing of marks of student in a class

It have two inputs , a key and the value
In this example , the name of the student is key and the mark is the value

- Incase if you add the key name which is already existing , it will update with the existing one
- The Keys are actually a set
#### For each loop

```Java
for(datatype variable : mapName.keySet()){
	System.out.println("Key : " + variable + "\nValue : "+ mapName.get(variable));
}
```
### HashMap 

``Map<Datatype,Datatype> variable = new HashMap<>();``

- Uses a hash table to store key-value pairs.
- Does not maintain any order of the keys. The order of the elements can change when the map is modified.
- constant-time performance (`O(1)`) for `put`, `get`, and `remove` operations, assuming a good hash function.
- Iteration order is unpredictable and can change over time.
### Tree Map 
- Uses a red-black tree (a type of self-balancing binary search tree) to store key-value pairs.
- Maintains the natural ordering of the keys or a custom order defined by a comparator. While in the HashMap the order is not preserved
- The time complexity for put, get, remove is 0(log n)
- Iteration order is predictable and follows the natural ordering of the keys or the order defined by the comparator.

```Java
import java.util.*;
class HelloWorld {
    public static void main(String[] args) {
        Map<String, Integer> hashMap = new HashMap<>();
        hashMap.put("apple", 1);
        hashMap.put("banana", 2);
        hashMap.put("cherry", 3);
        
        // Output: Unpredictable order
        for (Map.Entry<String, Integer> entry : hashMap.entrySet()) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }
        
        System.out.println();
        
        Map<String, Integer> treeMap = new TreeMap<>();
        treeMap.put("apple", 1);
        treeMap.put("banana", 2);
        treeMap.put("cherry", 3);
        
        // Output: Sorted order (alphabetically)
        for (Map.Entry<String, Integer> entry : treeMap.entrySet()) {
            System.out.println(entry.getKey() + " = " + entry.getValue());
        }
    }
}
```

```Output
banana = 2
apple = 1
cherry = 3

apple = 1
banana = 2
cherry = 3
```