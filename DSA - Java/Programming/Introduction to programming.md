
Video [link](https://youtu.be/wn49bJOYAZM?si=OoP7RfIiUczRxABB)

### Type of Programming languages

![[Pasted image 20231201180502.png]]

##### Different programming languages follows different properties of many type of languages

##### Java is more based on Object Oriented 

### Another type of language

![[Pasted image 20231201181223.png]]

### Memory Management (Heap and Stack)

The Reference variable is stored in the Stack and pointing the value(object) stored in the Heap

###### ==Make a point clear that multiple reference variable can point into a single object==

Ex : 

You are an object , named "Rahul"
You are organizing a party for friends , family , gf and cousins

Your mom , father mention you as son :: your friends mentions you as friend :: your sister mentions you as brother :: your gf mentions you as baby 

They may use different name (reference variable) but they points only single you (object)

Similarly there is only one object inside the heap memory and it can pointed by multiple variables

``` java
int a = [10,12,15];
int b = a;

a[0] = 92;

system.out.print(a) // [92,12,15]
system.out.print(b) // [92,12,15]
```

==incase if there is a change in value of the object inside the heap , it reflects the other variables too

