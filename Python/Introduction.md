Next Topic : [[Python/Data types|Data types]]
### Hello World Program

```Python
print("Hello World!")
```
```Outpu
Hello World
```

```Python 
import sys

sys.stdout.write("This is a alternate way to print in python")
```
### Python Syntax

- We don't use semi colons `;` as the statement terminator.
- We will use indentation instead of brackets
- We use `#` for comment
- We use `''' content '''` for multi line commanding

### if-else 
```Python
a = 5
b = 10

if(a > b):
    print("a is greater\n a : "+ str(a)+"\n b : "+str(b))
elif (b > a):
    print("B is greater\n a : "+ str(a)+"\n b : "+str(b))
else:
	print(f"A and B are equal\n a : {a}\n b : {b}")
```
```Output
B is greater
 a : 5
 b : 10
```

Short Hand 

- If else 
``true_condition_block if condition else false_condition_block``

Example : 
```Python
# Short hand if-else
print(f"{10} is greater") if (10 > 11) else print(f"{11} is greater")

# if-elif-else
print(f"{10} is greater") if (10 > 11) else print(f"{12} is greater") if(12 > 11) else print(f"{11} is greater")
```

`pass` is a keyword used inside the if or else or elif block where the block need to be empty because those blocks are not allowed to be empty
```Python
if(10 > 3):
    pass
```

