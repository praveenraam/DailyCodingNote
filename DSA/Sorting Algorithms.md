
#algorithm/sorting 

Know this before : [[Search Algorithms]]
Next Topic : [[ProblemSeries1]]

## Bubble sorting

##### ==Problem== :
Given an array and ordered to sort in the ascending or descending order

Ex : 
(34,45,23,124,42) => (23,34,42,45,124) in ascending 

##### Solution :
```js
function BubbleSort(arr){
    let swapped;
    do{
        swapped=false;
    for(let i=0;i<arr.length-1;i++){
        if(arr[i] > arr[i+1]){
            let temp = arr[i];
            arr[i] = arr[i+1];
            arr[i+1] = temp;
            swapped=true;
        }
    }}while(swapped)
    return arr
}
console.log(BubbleSort([8, 20, -2, 4, -6]));
```

Big O notation : O(n^2)




## Insertion sorting

![[Sorting Algorithms#==Problem==]]

Solution : 
```js
function InsertionSort(arr){
    for(let i=1;i<arr.length;i++){
        let numberToInsert = arr[i];
        let j = i-1
        while( j>=0 && arr[j] > numberToInsert){
            arr[j+1] = arr[j];
            j = j-1;
        }
        arr[j+1] = numberToInsert
    }
    return arr;
}  
  
console.log(InsertionSort([8, 20, -2, 4, -6]));
```

Big O Notation : O(n^2)


## Quick Sort 

![[Sorting Algorithms#==Problem==]]


Solution :
```js
function QuickSort(arr){
    if(arr.length < 2){
        return arr
    }
    
    let pivot = arr[arr.length - 1];
    let right = [];
    let left = [];
    
    for(let i=0;i < arr.length -1;i++){
        if(pivot > arr[i]){
            right.push(arr[i])
        }
        else{
            left.push(arr[i])
        }
  
    }
    return [...QuickSort(left) ,pivot,...QuickSort(right)]
}

console.log(QuickSort([8, 20, -2, 4, -6]));
```

Big O Notation : Worst Case : O(N^2)  Best Case : (nLogn)



## Merge Sort

![[Sorting Algorithms#==Problem==]]

Solution : 
```js
function mergeSort (arr) {
    if(arr. length < 2) {
        return arr
    }
    const mid= Math.floor(arr.length / 2)
    const leftArr = arr.slice (0, mid)
    const rightArr = arr.slice (mid)
    return merge (mergeSort (leftArr), mergeSort (rightArr))
}

function merge (leftArr, rightArr) {
    const sortedArr = []

    while (leftArr.length && rightArr.length) {
        if(leftArr [0] <= rightArr [0]) {
        sortedArr.push (leftArr.shift())
        } else {
        sortedArr.push (rightArr. shift ())
        }
    }
    return [...sortedArr, ...leftArr, ...rightArr]
}
const arr = [8, 20, -2, 4, -6]
console.log (mergeSort (arr)) // [-6, -2, 4, 8, 20]
```
