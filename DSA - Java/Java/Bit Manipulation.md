Topic No : 22
Next Topic [[]]
Playlist [Link](https://youtube.com/playlist?list=PLgUwDviBIf0rnqh8QsJaHyIX7KUiaPUv7&si=6cK6gcwi2isO0uxr)

The Bitwise operations are executed at high speed by the computers

### What is Decimal & Binary numbers

The numbers that we use in the day today life is in the form of decimal which is represented in 10's, while the Binary is represented in 1 and 0 which is used for the understanding of the computers as its main purpose.

#### Conversion

```Java
public static String DtoB(int n){  

    StringBuilder sb = new StringBuilder();  
    
    while(n>1){  
        int rem = n%2;  
        sb.insert(0,rem);  
        n = n/2;  
    }  
    if(n==1) sb.insert(0,1);  
    return sb.toString();  
}  
public static int BtoD(String B){  
    int res = 0;  
    int p1 = B.length()-1;  
    int base =1;  
    
    for(int i=0;i<B.length();i++) {  
        if (B.charAt(p1) == '1') res += pow(2,i);  
        p1--;  
    }  
    return res;  
}
```

**Decimal and Binary is good enough to solve the Bit Manipulation problems**

#### 1's Compliment

To do the 1's Compliment for a number, find a numbers binary form and flip it
Ex : 
```
13 Binary = 1101
13 1's    = 0010

15 Binary = 1111
15 1's    = 0000
```

#### 2's Compliment

To do the 2's Compliment for the number, find the 1's compliment and do binary addition of 1 with it 
Ex:
```
13 1's = 0010
13 2's = 0011
```


### Operators

#### AND operator (&)
```
ALL True -> true
1 False  -> false
```

Ex:
```
int m = 13 & 7;
```

We get the two numbers in binary and do **AND** operation
```
13 B -> 1101
7 B  -> 0111
AND  -> 0101 -> which is 5
```

#### OR operator ( | )
```
ALL False -> false
1 True    -> true
```

Ex:
```
int m = 13 | 7;
```

We get the two numbers in binary and do **OR** operation
```
13 B -> 1101
7 B  -> 0111
OR   -> 1111 -> which is 15
```

#### XOR operator (^)
```
Odd No of 1  -> 1
Even No of 1 -> 0
```

Ex:
```
int m = 13 ^ 7;
```

We get the two numbers in binary and do **XOR** operation
```
13 B -> 1101
7 B  -> 0111
XOR  -> 1010 -> which is 10
```

**XOR of same number gives 0**
#### Shift ( >> or <<)

##### Right Shift (>>)

We remove the last numbers in the binary as per input,

Ex:
```
int m = 13 >> 1;
int n = 13 >> 2;
int k = 13 >> 4;
```

```
13 B -> 1101
RS   -> 110  -> which is 6

13 B -> 1101
RS   -> 11  -> which is 3

13 B -> 1101
RS   -> 0   -> which is 0
```
###### Simple method to get the Value is using formula (x >> k) which is x/(pow(2,k)) 

##### Left Shift (<<)

We remove the first numbers in the binary as per input and add it to the last

Ex:
```
int m = 13 << 1;
```

```
13 B -> 1101
LS   -> 11010 -> which is 26
```
###### Simple method to get the Value is using formula (x<<k) which is x* pow(2,k)
###### There will be overflow in some cases, we have to do the left shift in caution of it

#### NOT operator (~)

```
int m = ~ (5);
```

The procedure is to flip the binary once, then if it is negative number do the 2's compliment, if positive stops at flipping.

A negative number is stored in the 2's compliment of number in the storage
