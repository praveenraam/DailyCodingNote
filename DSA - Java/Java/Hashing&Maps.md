Topic no : 18
Video [Link](https://youtu.be/KEs5UyBJ39g?si=D-emOEzYc14eiPNh)
Know this [[Mapping - 1]]
Next Topic [[Collections]]

**Hashing is an important topic in Data Structure**

### Why Hashing 

- Incase you are given a task for counting the number of specific numbers in an array , you would have to run the loop in time complexity of O(n^2) , for avoid it we introduce hashing

``` Java
static int[] numberCounter(int n,int arr[]){  // n is max of a single element
     int[] hash = new int[n+1];  
     for(int i=0;i< arr.length;i++){  
         hash[arr[i]] +=1;  
     }  
     return hash;  
} // This is done using array hashing
```

- Using of array for hashing have limits like size etc.. , so avoid using Arrays for hashing  ![[Pasted image 20240127142622.png]]

### Solution 
- In java , so HashMap datatype comes into play
- Instead of using an array , we will be using HashMap 
- Here we can store any number of element without any limitations 

**Hash Maps** will store the key and value in itself , while giving the input you have to include the both key and value of the key
![[Mapping - 1#Hash Map]]
**Output** : {Rahul=60, Kavin=40, Praveen=30}

### Time Complexity
The following table shows the time complexity of the main operations on a HashMap in Java:

|Operation|Time Complexity|
|---|---|
|Put|O(1) on average, O(n) in the worst case|
|Get|O(1) on average, O(n) in the worst case|
|Remove|O(1) on average, O(n) in the worst case|
|ContainsKey|O(1) on average, O(n) in the worst case|
|Iterate over keys or values|O(n)|
### Counting of char in word using HashMap
```Java
static HashMap charCounter(String word){  
     HashMap<Character,Integer> Hash = new HashMap<>();  
     for(int i=0;i<word.length();i++){  
	    char myChar = word.charAt(i)
        if(Hash.get(myChar) != null)  
            Hash.put(myChar,Hash.get(myChar)+1);  
        else Hash.put(myChar,1);  
     }  
     return Hash;  
}
```
### Advantages of using HashMap
- Take less memory
- Not compulsory to mention the size earlier
- Easy to store key and value
##### Methods in Hashing [Article Link](https://www.geeksforgeeks.org/hash-functions-and-list-types-of-hash-functions/)
- Division Method
- Multiplication Method
- Folding Method
##### While using these methods we may encounter a new problem **Collision**
- a situation where two or more key objects produce the same final hash value and hence point to the same bucket location or array index , to tackle this we use **Separate Chaining Method**


