Topic No : 6
Previous Topic : [[JOIN]]
Next Topic : [[StringFunctionsInSQL]]

### What is `UNION`
This is used to combine the values from multiple columns from different and same tables.
This is `DISTINCT` by default.

### Syntax
```SQL
SELECT column_name1
FROM table_name1
UNION
SELECT  column_name2
FROM table_name2
```

##### Example 1 :
```SQL
SELECT first_name,last_name
FROM employee_demographics
UNION 
SELECT first_name,last_name
FROM employee_salary;
```
![[Pasted image 20250108173435.png]]
Joins the two values in the tables and removed all the duplicates.

##### Example 2 :
```SQL
SELECT first_name, last_name, "OLD" AS Label
FROM employee_demographics
WHERE age >= 50
UNION
SELECT first_name,last_name, "High Paid" AS Label
FROM employee_salary
WHERE salary > 70000;
```
![[Pasted image 20250108174227.png]]

##### Example 3 :
```SQL
SELECT first_name, last_name, "OLD MAN" AS Label
FROM employee_demographics
WHERE age >= 40 AND gender = 'Male'
UNION
SELECT first_name, last_name, "OLD Lady" AS Label
FROM employee_demographics
WHERE age >= 40 AND gender = 'Female'
UNION
SELECT first_name,last_name, "High Paid" AS Label
FROM employee_salary
WHERE salary > 70000;
```
![[Pasted image 20250108174741.png]]
