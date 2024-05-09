Topic no : 19
Next Topic : [[]]


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
``Map<Datatype,Datatype> variable = new HashMap<>();``
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
