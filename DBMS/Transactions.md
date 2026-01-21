x`Topic No : 9
Previous Topic : [[Normalization]]
Next Topic : [[Schedule in DBMS]]
Article Link : **Must read**
- https://www.geeksforgeeks.org/concurrency-control-in-dbms/
### What is Transaction
Transaction is group of operations that are performs a simple logical functions in database.
### What is ACID Properties
This is a concept of ACID properties in DBMS that are necessary for maintaining data consistency, integrity, and reliability while performing transactions in the database.
#### Atomicity
As a transaction is a set of logically related operations, **either all of them should be executed or none is executed***.
#### Consistency
A consistent transaction will not violate integrity constraints placed on the data by the database rules
#### Isolation
This property ensures that multiple transactions can occur concurrently without leading to the affect on one another of the database state.
#### Durable 
Once the changes were made to the Database, that changes should be always permanent and backup taken.