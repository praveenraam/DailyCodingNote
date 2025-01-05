Topic No : 1
Previous Topic : [[Types of Commands in SQL]]
Next Topic : [[WHERE]]

### What is Select
This is a statement that returns a result of set of rows, from one or more table.

### Syntax 

##### Selecting everything from table

```SQL
SELECT * 
FROM database_name.table_name;
```

- `*` means everything from the table
- `database_name.table_name` this means that we need to search that database for the table.

#### Selecting specific Columns from table

```SQL
SELECT 
	column_name,
	column_name
FROM database_name.table_name;
```

### PEMDAS
This is prioritizing order of Arithmetic operations 
- Parentheses
- Exponents
- Multiplication
- Division
- Addition
- Subtraction

Ex :
```SQL
SELECT 
	First_name,
	Second_name,
	age,
	(age+10)*5
FROM parks_and_recreation.employee_demographics;
```

### DISTINCT 

This is a keyword used to only return the unique elements

While using `DISTINCT` on multiple columns, it verifies combination of them is unique or not
Ex : 
```SQL
SELECT DISTINCT 
	gender
FROM parks_and_recreation.employee_demographics;
```
```Output
Male 
Female
```

```SQL
SELECT DISTINCT
	age,gender
FROM parks_and_recreation.employee_demographics;
```
![[Pasted image 20250105124444.png]]

### All queries

```SQl
SELECT *
FROM parks_and_recreation.parks_departments;

SELECT first_name,last_name
FROM parks_and_recreation.employee_demographics;

SELECT 
	First_name,
	last_name,
	age,
	(age+10)*5
FROM parks_and_recreation.employee_demographics;


SELECT DISTINCT age,gender
FROM parks_and_recreation.employee_demographics;
```