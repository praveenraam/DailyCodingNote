Previous Topics : [[Operators]]
Next Topics : [[Functions]]

### While Loops
```Python
iter = 1

while(iter<=5):
    print(iter,end=" ")
    iter+=1

print()
```

### Break
Terminate the loop from executing again
```Python
iter = 1

while(iter<10):
    print(iter,end=" ")
    iter+=1
    if(iter > 6): break

print()
```
```Output
1 2 3 4 5 6
```

### Continue 
Skip an iteration and stop from balance code to get executed in the loop block
```Python
iter = 1

while(iter<10):
    if(iter == 6 or iter == 7):
        iter+=1
        continue
    print(iter,end=" ")
    iter+=1
    
print()
```
```Output
1 2 3 4 5 8 9
```

### Else in Loop
```Python
iter = 1

while(iter<10):
    if(iter == 6 or iter == 7):
        iter+=1
        continue
    print(iter,end=" ")
    iter+=1
else:
	print()
    print("Iter is equals to 10, so loop got terminated")
```
```Output
1 2 3 4 5 8 9 
Iter is equals to 10, so loop got terminated
```

### For loop

For loop for string
```Python
# For Loop in char
str_value = "We are getting throught for loop"
for char in str_value:
    print(char+" ",end="")
else:
	print()
	print("Loop is finished")
```

### Using range

``range()`` is a function returns a sequence of numbers from 0 by default and incremented by 1 in default and ends at specified number

```Python
for iter in range(6): # return 0<=iter<5
    print(iter,end=" ")
print()

for iter in range(1,6): # return 1<=iter<5
    print(iter,end=" ")
print()
  
for iter in range(1,10,2): # return 1,3,5,7,9 values will be incremented by 2
    print(iter,end=" ")
print()
```

### Nested Loop
```Python
## nested loop
for iter in range(6):
    for inIter in range(1,11): ## from 1 to 10
        print(inIter,end=" ")
    print()
```
```Output
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
```
