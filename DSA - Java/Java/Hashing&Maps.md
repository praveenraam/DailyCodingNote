Video [Link](https://youtu.be/KEs5UyBJ39g?si=D-emOEzYc14eiPNh)
Know this [[Mapping - 1]]
Next Topic [[]]


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
}
```

- Using of array for hashing have limits like size etc.. , so avoid using Arrays for hashing  ![[Pasted image 20240127142622.png]]

### 