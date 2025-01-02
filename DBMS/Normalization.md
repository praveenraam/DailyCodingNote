Topic No : 8
Previous Topic : [[Keys in RDBMS]]
Next Topic : [[Transactions]]

Before seeing Normalization, we know about Functional Dependencies
### What is Functional Dependency?

A functional dependency occurs when one attribute uniquely determines another attribute within a relation. It is a constraint that describes how attributes in a table relate to each other. If attribute A functionally determines attribute B we write this as the ***A→B***.

### What is Normalization
It is a process of organizing the data in the database
### Why Normalization
It is done to reduce the data redundancy in the database
##### What is Data Redundancy 
It is nothing but the repetition of same data in multiple places. (Duplicate Values)
It causes anomalies (Error : Abnormal) in database which make it harder for DBA to maintain it.

##### Types of Anomalies 
- Insertion : This occurs during inserting because some columns maybe missing at insertion time
- Updation :  This occurs when same data are repeated with same value
- Deletion : This occurs while deleting, by removing the necessary data while deleting the unwanted
### Types of Normalization

This normalization is done through Series of stage called Normalization Forms which follows constraints (Rules).

#### 1NF
1NF : 1st Normal Form

The Table is said to be in 1NF if it **doesn't have multi-Values Attributes**, should contains only **Single Value Attributes**.

First Normal Form disallows the multi-valued Attributes
Ex : 
![[Pasted image 20250101145448.png]]
#### 2NF
2NF : 2nd Normal Form

The Table is said to be in 2 conditions
- It should be in 1NF 
- **Not containing any partial Dependencies** ( in Primary Key column there should be no duplicates ).
So, we create a separate table for multi values and link them to this.
Ex : 
![[Pasted image 20250101145828.png]]

#### 3NF
3NF : 3rd Normal Form

Two Conditions for 3NF
- Should be in 2NF
- **Should not contains any transitive dependency** ( When one non-primary key attributes depend on another non-primary key attributes then it should be in another table )
Ex : 
![[Pasted image 20250101154415.png]]
The Item and Supplier is sent to separate table and where supplier is depended on Item.

#### BCNF
BCNF : Boyce-Codd Normal Form
This is extended version of 3NF, also called 3.5NF

Conditions for BCNF
- Should be in 3NF
- The any dependency A->B, **A should be a super key**

Ex : 
![[Pasted image 20250101155233.png]]
This is not in 3NF and BCNF, to convert it to 3NF, we move branch ID and Branch name to new table.
To convert to BCNF, we need to make the branch ID all unique ones
![[Pasted image 20250101155413.png]]

#### 4NF
4NF : 4th Normal Form
Conditions :
- Should be in BCNF
- Should not contains any multi value dependency. ( No more than one non primary key attributes depends on primary key column ).
Ex : 
![[Pasted image 20250101160635.png]]
#### 5NF
5NF : 5th Normal Form
Dividing the table into more possible tables.
Conditions : 
- Should be in 4NF
- Should not contains any join dependency
Ex : 
![[Pasted image 20250101161154.png]]
### Advantages and Disadvantages

| Advantages              | Disadvantages                        |
| ----------------------- | ------------------------------------ |
| Minimum data redundancy | Performance decreases on 4NF and 5NF |
| Data consistency        | 1NF don't allow multivalues          |
| Integrity               |                                      |

