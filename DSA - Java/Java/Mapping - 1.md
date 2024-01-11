Topic No : 15
Next Topic : [[]]
Article [Link](https://www.geeksforgeeks.org/introduction-to-map-data-structure-and-algorithm-tutorials/)

#### Map is a collection of key value pairs

#### There are several type of mapping 
- Hash Map
- Tree Map
- Linked Hash Map
- Trie Map
- Bloom Filter Map

## Mapping in Java

#### Types in Java
- [Hash Map](https://www.geeksforgeeks.org/linkedhashmap-class-in-java/)
- [Linked Hash Map](https://www.geeksforgeeks.org/linkedhashmap-class-in-java/)
- [Tree Map](https://www.geeksforgeeks.org/linkedhashmap-class-in-java/)
#### Hash Map

- If you need to use the hash map you need to import HashMap file
	``import java.util.HashMap;``

- Declaring the HashMap 
	``HashMap<String(YourDataType), Integer(YourDataType)> Vname = HashMap<>();`` 

- Adding Values 
	``Vname.put(Value,key)``

```Java
public static void main(String[] args) {  
    HashMap<String,Integer> Marks = new HashMap<>();  
    
    Marks.put("Praveen",30);  
    Marks.put("Kavin",40);  
    Marks.put("Rahul",60);  
    
    System.out.println(Marks);  
}
```

**HashMap in Java implements Serializable, Cloneable , [Map<K, V>](https://www.geeksforgeeks.org/map-interface-java-examples/) interfaces**

#### Hierarchy of Java HashMap : 

![[Pasted image 20240111233813.png]]

