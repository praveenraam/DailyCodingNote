#algorithm/search 

know before this : [[Recursion and problem]]
Next topic : [[Sorting Algorithms]]
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



## Binary Search 
##### How Binary Search Works?

For a binary search to work, it is mandatory for the target array to be sorted. We shall learn the process of binary search with a pictorial example. The following is our sorted array and let us assume that we need to search the location of value 31 using binary search.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_0.jpg)

First, we shall determine half of the array by using this formula −

mid = low + (high - low) / 2

Here it is, 0 + (9 - 0 ) / 2 = 4 (integer value of 4.5). So, 4 is the mid of the array.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_1.jpg)

Now we compare the value stored at location 4, with the value being searched, i.e. 31. We find that the value at location 4 is 27, which is not a match. As the value is greater than 27 and we have a sorted array, so we also know that the target value must be in the upper portion of the array.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_2.jpg)

We change our low to mid + 1 and find the new mid value again.

low = mid + 1
mid = low + (high - low) / 2

Our new mid is 7 now. We compare the value stored at location 7 with our target value 31.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_3.jpg)

The value stored at location 7 is not a match, rather it is more than what we are looking for. So, the value must be in the lower part from this location.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_4.jpg)

Hence, we calculate the mid again. This time it is 5.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_5.jpg)

We compare the value stored at location 5 with our target value. We find that it is a match.

![Binary search](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_6.jpg)

We conclude that the target value 31 is stored at location 5.

Binary search halves the searchable items and thus reduces the count of comparisons to be made to very less numbers.

##### Problem :
Given a sorted array of elements and a target , find the index of the target element in the array. Return -1 if target element is not found

##### Solution 
```js
function binarySearch(arr,target){

    let leftindex = 0;
    let rightindex = arr.length - 1;

    while(leftindex <= rightindex ){
        let middleIndex = Math.floor((leftindex+rightindex)/2);

        if(target === arr[middleIndex]){
            return middleIndex;
        }

        if(target < arr[middleIndex]){
            rightindex = middleIndex - 1;
        }else{
            leftindex = middleIndex + 1;
        }
    }

    return -1;

}
console.log(binarySearch([-5,3,5,7,8],7));
console.log(binarySearch([-5,3,5,7,15],15));
console.log(binarySearch([-5,3,5,8,10],45));
```

==**Big O Notation : O(logn)**==

##### Solution using the recursion :
```js
function binarySearchRecursion(arr,target){
    return Search(arr,target,0,arr.length - 1);
}
  
function Search(arr,target,LeftIndex,RightIndex){
    if(LeftIndex > RightIndex){
        return - 1;
    }

    let middleIndex = Math.floor((LeftIndex+RightIndex)/2);
    if(target === arr[middleIndex]){
        return middleIndex;
    }
    
    if(target < arr[middleIndex]){
        return Search(arr,target,LeftIndex,middleIndex - 1);
    }
    else{
        return Search(arr,target,middleIndex + 1,RightIndex);
    }
}
console.log(binarySearchRecursion([-5,3,5,7,8],7));
console.log(binarySearchRecursion([-5,3,5,7,15],15));
console.log(binarySearchRecursion([-5,3,5,8,10],45));
```
