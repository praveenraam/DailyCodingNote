Topic No : 17
Video [Link](https://youtu.be/lsOOs5J8ycw?si=T7cVO8OCj2ABBsc2)
Next Topic : [[]]

## How to approach a problem 
#### Step 1
- Run the outer loop for the number of lines you need to print 
- Simply run the outer loop no of times of the rows
#### Step 2 
- Identify no of columns in the every row or 
- Identity type of element in every row
#### Step 3
- What do we need to print
#### Step 4
- Once the Inner loop completed running
- Add a new line

## Problems
[All Patterns](https://github.com/kunal-kushwaha/DSA-Bootcamp-Java/blob/main/assignments/09-patterns.md)
### Question : Pattern 1

```Pattern 
*****
*****
*****
*****
*****
```
##### Code :
```Java
public static void Patter1(int n){  
    for(int row=1;row<=n;row++){  
        for(int column=0;column<5;column++){  
            System.out.print('*');  
        }  
        System.out.println();  
    }  
}
```
### Question : Pattern 2

```Pattern
*
**
***
****
*****
```
##### Code 
```Java
public static void Patter2(int n){  
    for(int row=1;row<=n;row++){  
        for(int column=0;column<row;column++){  
            System.out.print('*');  
        }  
        System.out.println();  
    }  
}
```
### Question : Pattern 3

```Pattern
*****
****
***
**
*
```
##### Code 
```Java
public static void Patter3(int n){  
    for(int row=1;row<=n;row++){  
        for(int column=n;column>=row;column--){  
            System.out.print('*');  
        }  
        System.out.println();  
    }  
}
```

### Question : Pattern 4

```Pattern
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

##### Code 
```Java
public static void Patter4(int n){  
    for(int row=1;row<=n;row++){  
        for(int column=1;column<=row;column++){  
            System.out.print(column);  
        }  
        System.out.println();  
    }  
}
```

### Question : Pattern 5

```Pattern

*
**
***
****
*****
****
***
**
*
```

##### Code 
```Java
public static void Patter5(int n){  
    int Counter = 2;  
    for(int row=1;row<=(n*2 - 1);row++){  
        if(row <= n) for(int column=0;column<row;column++) System.out.print('*');  
        else{  
            for(int column=0;column<=n-Counter;column++){  
                System.out.print('*');  
            }  
            Counter++;  
        }  
        System.out.println();  
    }  
}
```

### Question : Pattern 6 
```Pattern

```