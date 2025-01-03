Topic No : 10
Previous Topic : [[Transactions]]
Next Topic : [[SQL]]
Article Link : **Read for Better Understanding**
	- https://www.geeksforgeeks.org/serializability-in-dbms/
### What is Schedule 
Schedule is how the transactions are going to executed, there are two types
- **Serial Schedule :** Executing Transactions one after another, after one is got executed.
- **Concurrent Schedule :** When operations of transaction are interleaved with operations of other transaction of a schedule, this is called Concurrent Schedule.

### What is a serializable schedule, and what is it used for?

If **non-serialized schedule can be transformed into its corresponding serial schedule**, 
(non-serialized where the transactions are overlapped).

Types of Serialization : 

- **Conflict Serializability :** 
	What is Conflict : Two operations are said to be conflicting if all conditions are satisfied: 
		- They belong to different transactions
		- They operate on the same data item
		- At Least one of them is a write operation
	In order to solve this we use Graph method to decide the execution Order, read more in article to understand better.
- **View Serializability :**
	This is to overcome some limitation in the Conflict Serialization, there are some possibilities that loop or a cycle may form in the decision making in graph and to avoid inconsistency.
	
	In countering the limitations we use set of rules, consider S1 and S2 schedule,
	- The first prerequisite is that the same kind of transaction appears on every schedule. This requirement means that the same kind of group of transactions cannot appear on both schedules S1 and S2
	- The second prerequisite is that different read or write operations should not be used in either of them, 
	- The last requirement is that both of them are not allowed to have conflict between them.
