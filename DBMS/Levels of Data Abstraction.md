Topic No : 3
Previous Topic : [[DBMS Architecture]]
Next Topic : [[Data Models]]

### What is Data Abstraction
It is a process of removing the unwanted or irrelevant data from the end user and display the necessary details.
This is done to remove the complexity for the user in accessing the database.

These are done by the developer, this is known as level of Abstraction.

### What is Schema

- It is known as the structure or design of the database
- The Skeleton of the database is created by the attributes and this skeleton is named Schema.
- This is not changes often or not changed at all.
- Schema is similar to the variables, where data can be changes not the types (Structure).
- **Instance** is the value stored in the Schema.
### Levels of Abstraction
This is also know as **Three Levels of Schema or Levels of Schema**

There are three levels
- Physical or Internal Level
- Logical or conceptual level
- View or External Level

![[Pasted image 20241230153618.png]]

### Physical level or Internal Level

This is the lowest level in the data abstraction.  
In this level, it **describes how the data is stored in the database**, including the data structure and access method.

This is very complex level. So, it is better to hide it from the user.

### Logical Level or Conceptual Level

This is the intermediate level of data abstraction.
In this level, it **describe what data is going to be stored and what is relationship among them**. 

This uses only the simple data structures and it is less complex.
Any Changes made here, won't affect the Physical Level.

### View Level or External Level

This is the highest level of data abstraction.
This level deals with the users.

There are several views in this level, because the one user can only access to his/her data as per his/her permissions, not to other user's data. This is how security is achieved.

