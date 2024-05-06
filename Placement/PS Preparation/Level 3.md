
### Count of array elements divisible by specific number

```C
#include <stdio.h>

int main(){
    int size;
    scanf("%d",&size);
    int nums[size];
    
    for(int i=0;i<size;i++){
        scanf("%d",&nums[i]);
    }
    
    int divisor,count=0;
    scanf("%d",&divisor);
    
    for(int i=0;i<size;i++){
        
        if(nums[i]%divisor == 0){
            count++;
        }
        
    }
    
    printf("The array elements divisible by %d is %d",divisor,count );
}
```

### Removing even numbers from an array

```C
#include <stdio.h>

int main(){
    int size;
    scanf("%d",&size);
    
    int nums[size];
    
    for(int i=0;i<size;i++){
        scanf("%d",&nums[i]);
    }
    
    int res[size];
    
    for(int i=0;i<size;i++){
        res[i] = 0;
    }
    
    int count = 0;
    for(int i=0;i<size;i++){
        if(nums[i]%2 != 0){
            res[count] = nums[i];
            count++;
        }
    }
    
    for(int i =0;i<size;i++){
        if(res[i] == 0){
            break;
        }else{
            printf("%d\n",res[i]);
        }
    }
}
```

### Give c program to print the number of occurrence of a number in an array

```C
#include <stdio.h>

int main() {
   int size;
   scanf("%d",&size);
   int no;
   scanf("%d",&no);
   int arr[size];
   int count = 0;
   for(int i=0;i<size;i++){
       scanf("%d",&arr[i]);
       if(arr[i] == no){
           count++;
       }
   }
   printf("%d",count);
}   
```

### Sum, product of an array

```C
// Online C compiler to run C program online
#include <stdio.h>

int main() {
   int size;
   scanf("%d",&size);
   
    int num[size];
   
   for(int i=0;i<size;i++){
       scanf("%d",&num[i]);
   }
   
   int sum = 0;
   for(int i=0;i<size;i++){
       sum+=num[i];
   }
   int prod = 1;
   for(int i=0;i<size;i++){
       prod*=num[i];
   }
   
   printf("Sum : %d\n",sum);
   printf("Pro : %d",prod);
   
}   
```

### Print square of the elements in an array

```C
// Online C compiler to run C program online
#include <stdio.h>

int main() {
   int size;
   scanf("%d",&size);
   
    int num[size];
   
   for(int i=0;i<size;i++){
       scanf("%d",&num[i]);
   }
   
   for(int i=0;i<size;i++){
       int temp = (num[i]*num[i]);
       printf("%d ",temp);
   }
   
}   
```

### Difference between maximum and minimum element of an array

```C
// Online C compiler to run C program online
#include <stdio.h>

int main() {
   int size;
   scanf("%d",&size);
   
   int arr[size];
   
   for(int i=0;i<size;i++){
       scanf("%d",&arr[i]);
   }
   
   int max = -1;
   int min = 100000;
   for(int i=0;i<size;i++){
       if(max < arr[i]) max = arr[i];
       if(min > arr[i]) min = arr[i];
   }
   
   printf("%d",max-min);
   
}   
```

### Print negative elements in array

```C
// Online C compiler to run C program online
#include <stdio.h>

int main() {
   int size;
   scanf("%d",&size);
   
   int arr[size];
   
   for(int i=0;i<size;i++){
       scanf("%d",&arr[i]);
   }
   
   for(int i=0;i<size;i++){
       if(arr[i] < 0) printf("%d ",arr[i]);
   }
   
}   
```

### Print the peak elements in array
`
```C
// Online C compiler to run C program online
#include <stdio.h>

int main() {
   int size;
   scanf("%d",&size);
   
   int arr[size];
   
   for(int i=0;i<size;i++){
       scanf("%d",&arr[i]);
   }
   int ans = -1;
   for(int i=1;i<size-1;i++){
       if(arr[i-1] < arr[i] && arr[i+1] < arr[i]){
           ans = arr[i];
       }
   }
   printf("%d",ans);
   
}   
```

### Find the count of the positive number

```C
// Online C compiler to run C program online
#include <stdio.h>

int main() {
   int size;
   scanf("%d",&size);
   
   int arr[size];
   
   for(int i=0;i<size;i++){
       scanf("%d",&arr[i]);
   }
   int count = 0;
   for(int i=0;i<size;i++){
       if(arr[i] > 0){
           count++;
       }
   }
   printf("%d",count);
   
}   
```

### Delete the element in the given position in an array
```C
#include<stdio.h>

int main(){
    int size;
    scanf("%d",&size);
    int num[size];
    
    int position;
    scanf("%d",&position);
    
    for(int i=0;i<size;i++){
        scanf("%d",&num[i]);
    }
    
    for(int i=0;i<size;i++){
        if(i == position) continue;
        printf("%d ",num[i]);
    }
}
```

### Find the non prime numbers in an array

```C
#include<stdio.h>

int isPrime(int n){
    if(n == 1 || n == 0) return n;
    int divi = 2;
    while(divi<n){
        if(n%divi == 0){
            return 0;
        }
        divi++;
    }
    return 1;
}

int main(){
    int size;
    scanf("%d",&size);
    int num[size];
    
    for(int i=0;i<size;i++){
        scanf("%d",&num[i]);
    }
    
    for(int i=0;i<size;i++){
        if(isPrime(num[i]) == 0){
            printf("%d ",num[i]);
        }
    }
    
}
```


### replace the peak number by adding it neighbor elements  (example:-   input: 1 2 4 3    output: 1 2 9 3   )

