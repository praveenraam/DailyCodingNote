Next Topic : [[Operators]]
Previous Topic : [[Python/Introduction|Introduction]]


- Text : ``string``
- Numeric : ``int``, ``float``, ``complex``
- Sequence : ``list``, ``tuple``, ``range``
- Mapping type : ``dict``
- Set types : ``set``, ``frozen_set``
- Boolean : ``bool``
- Binary : ``bytes``, ``bytesarray``, ``memoryview``
- None : ``NoneType``

```Python
number = 5

stringType = "Google"

floatType = 20.05

complexType = 1j

listType = ["apple","banana","Cherry"] # mutalbe

tupleType = ("apple","banana","cherry") # immutable
# tupleType.__add__("Google")

rangeType = range(6)

dictType = {"name":"john","age":"20"}

setType = {"apple", "banana", "cherry"}

frozensetType = frozenset({"apple", "banana", "cherry"})

booleanType = True

bytesType = b"Hello"

bytearrayType = bytearray(5)

noneType = None
```

### Casting

- ``str(variable)`` -> change to str from int , float
- ``float(variable)`` -> change to float from string, int
- ``int(variable)`` -> change to int from string, float


### String

``' content'`` or `'' content ''
- Multiline String `""" content """` `''' content '''`

String are represented as array in python

Functions used on String 

```Python
# Index
greeting = "Good afternoon"
print(greeting[1])

# Loop a String
for char in greeting:
    print(char,end="") # we skip the new line
print() # for new line

# Length
print(len(greeting))

# Check for letters in String
wordTofind = "aft"
if (wordTofind in greeting):
    print(wordTofind +" is in "+greeting)
if(wordTofind not in greeting):
    print(wordTofind +" is not in"+greeting)

# Slicing
print(greeting[2:5]) # from 2 to 4
print(greeting[:5]) # from 0 to 4
print(greeting[2:]) # from 2 to end
print(greeting[-12:1]) # checking index from back

# Modifying string
print(greeting.upper())
print(greeting.lower())
print(greeting.strip()) # remove whitespace (similar to trim() in java)
print(greeting.split(" ")) # split the sentence with " "
print(greeting.replace("o","a")) # replace all the o's with a

# Formating string using F-string
print(greeting+str(23)) # need to convert int to str to print
number_to_print = 23
print(f"greeting {number_to_print}") # will print 23 without use of str() func
print(f"{number_to_print:..2f}") # Will print 23.00
```

Escape Sequence : https://www.w3schools.com/python/python_strings_escape.asp
Function in python for Strings : https://www.w3schools.com/python/python_strings_methods.asp

### Boolean in python

All the variable, number can be used as Booleans in python except `0`, empty string, list, tuple, set, dict.

```Python
print(bool(1)) # true
print(bool([])) # false : empty list
print(bool(0)) # false
```