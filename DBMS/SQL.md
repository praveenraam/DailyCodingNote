Topic No : 11
Previous Topic : [[Schedule in DBMS]]
Next Topic : [[SELECT]]
### What is SQL
SQL : Structured Query Language
- It is a standardized programming language used for managing the relational databases.
- We can perform various tasks such as querying data, create and modify database and managing access permissions.
### How it is worked
There are several steps involved in using SQL,
- Input : The process of SQL is started with application Interface which allow to enter SQL query
- Parsing : The data is breakdown into smaller tokens, and the smaller tokens are evaluated and the database schema is cross checked query is well-formed.
- Optimization : After parsing, the query is going to optimizer, evaluating multiple way to run query and picks the one requires minimum resource and maximum performance
- Execution : The execution engine follows the plan of optimizer.
- Output : Once the execution engine process the query, the result is formatted and returned.
### Rules for SQL

- Statement Terminator : Every SQL statement end with `;`.
- Case Insensitive : SQL keywords are insensitive, but the table names, database name maybe sensitive dependent on on DBMS
- White Space Flexibility : every keyword must be separated by at least one space.
- Unique Identifiers : Reserve words can't be used as table or attributes.
- Commands : 
	- Single line : `--`
	- multi line : `/* Our content /*`
- String literals : String values must be enclosed with in single Quotes
- Valid Identifiers : Table and columns 
	- Must start with alphabetic Character
	- Contains only up to 30 characters
	- No special characters except `_`

### SQL commands

Various tasks done by the SQL is categorized into several types
- DDL : Data Definition Language
- DQL : Data Query Language
- DML : Data manipulation Language
- DCL : Data Control Language
- TCL : Transaction Control Language
[[Types of Commands in SQL]]
![[Pasted image 20250104124303.png]]