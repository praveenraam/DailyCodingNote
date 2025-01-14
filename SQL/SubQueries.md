Topic No : 8
Previous Topic : [[CASE Statements]]
Next Topic : [[AdvSubQueries]]

### What is Sub-Query
A statement within an another statement is Sub-Query. 

```SQL
SELECT column_name  
FROM table_name  
WHERE column_name expression operator   
    (SELECT column_name FROM table_name WHERE ...);
```

### Examples :

Example 1 : 
```SQL
SELECT *
FROM employee_demographics
WHERE employee_id IN 
( 	SELECT employee_id -- returns ID of employees with salary more than 50000
   FROM employee_salary
   WHERE salary > 50000a
);
```
![[Pasted image 20250112123134.png]]

Example 2 :
```SQL
SELECT first_name, last_name, (
	SELECT AVG(salary)
	FROM employee_salary
) AS avg_salary
FROM employee_salary;
```
![[Pasted image 20250112124003.png]]

Example 3 :
```SQL
SELECT first_name, last_name, salary
FROM employee_salary
WHERE salary > (SELECT AVG(salary)
FROM employee_salary);
```
![[Pasted image 20250112124030.png]]

