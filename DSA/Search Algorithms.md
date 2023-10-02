know before this : [[Recursion and problem]]
## Linear algorithm 

##### ==Problem== : 
Given array of 'n' elements and a target number 't' , find the index of 't' in the array. Return -1 if the target element is not found

Ex :
- arr = (-5,2,3,5,7) t=3 , output 2
- arr = (-5,2,3,5,7,23) t=23 , output 5
- arr = (-5,2,3,5,7) t=24 , output -1

##### Solution 


```PseudoCode

Starting at the first element in the array and move towards last , at each element through check is the element is equal to the target element. 

If element found , return the index of the element 
else element not found , return -1
```

``` js
function LinearSearch(arr,target){
    for(let i=0;i<arr.length;i++){
        if(target === arr[i]){
            return arr[i]
        }
    }
    return -1;
}
console.log(LinearSearch([12,14,14,546,76,8,79,7,2,259,87,89,89023,1,31,1,3],89023))
console.log(LinearSearch([12,14,14,546,76,8,79,7,2,259,87,89,89023,1,31,1,30],30))
```

![[Algorithm Analysis#Big O notation Guide]]

Big O notation : O(n)