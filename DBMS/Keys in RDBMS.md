Topic No : 7
Next Topic : [[Normalization]]

### What is key :
 It is widely used to identify the tuples(rows) uniquely in the table
### Why we need keys : 
We use a key **for defining various types of integrity constraints in a database**

### Types of Key

![[Pasted image 20241231120814.png]]
##### Super key
This is collection of one or more keys that allow only unique values in tuples.
Ex : From the above Picture, we can see that the collection of EmpID, EmpLicense and EmpPassport is a super key in the table.

You can make any number of combination to form the collection.
##### Candidate key
It is a set of one of more columns that can be uniquely identify each rows.
Ex : EmpID, EmpLicence, EmpPassport
##### Primary key
The attribute that should be unique and should not contains null value and it should be only one. The instance also should not be altered.
Ex : EmpID, as everyone has EmpID. The other two EmpLicence and EmpPassport is also eligible but it is decided by DBA.
##### Alternate key
The attributes that are eligible to be primary but not selected is called Alternate key.
Ex : EmpLicence and EmpPassport.
##### Unique key
The attributes where the values should be unique and allowed have null values
Ex : EmpLicence and EmpPassport are unique and not all need to have License and Passport
##### Foreign key
The column in a table that is reference a column in another table.
![[Pasted image 20241231123959.png]]
##### Composite key
The table that combines two or more attributes to uniquely identify a column.