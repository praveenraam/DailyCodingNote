
Article [Link](https://www.baeldung.com/solid-principles)
Notes [Link](https://www.notion.so/SOLID-PRINCIPLE-1ba20ab447a380019766ed13047bcce2)
### What is SOLID

These are the **design principles encourage us to create more maintainable, understandable, and flexible software**, these are mainly focus on the OOP concepts across all the language
### Single responsibility

The class should only have one responsibility to handle, 
Further -> It should only have one reason to change
##### How it helps us to write better code :
- Testing 
- Lower coupling
- Organization

Look for examples in Article

### Open and close

This means that the classes should be open for the extensions but closed for the modifications,
There is one exception, incase of bug in code we can modify it.
##### How it helps us : 
In doing so we can stop modifying existing code and closing potential new bugs.

Look for examples in Article

### Liskov Substitution

This is the most complex of five principles

In simple, we consider a class A and class B which is a subtype of A
We should be able to replace the class B in the places of class A without any disrupt to behavior of our program

Look for examples in Article

### Interface segregation

Larger interfaces should be split into smaller ones
##### How it helps us :
By doing so, we can ensure that implementing class only need to be concerned about the methods that are of interest of them

Look for examples in Article

### Dependency Inversion

This principle refers to decoupling of software components, 
##### How it helps us : 
This way, instead of high level modules depending on low level module, both will depend on abstraction

Look for examples in Article.