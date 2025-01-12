Topic No : 7
Previous Topic : [[StringFunctionsInSQL]]
Next Topic : [[SubQueries]]

### What is `CASE` statement
A conditional statement that evaluates expressions and performs actions based on the results.

### Syntax
```SQL
SELECT 
CASE
-- CONDITIONS
	WHEN condition THEN FollowUp
END
FROM TABLE_NAME;
```


Example 1 :
```SQL
SELECT first_name,age,
CASE 
	WHEN age >= 50 THEN 'OLD'
	WHEN age < 50 THEN 'YOUND'
END AS described
FROM employee_demographics;
```

Example 2 :
```SQL
SELECT first_name,last_name,salary,
CASE
	WHEN salary > 50000 THEN salary*1.05
	WHEN salary <= 50000 THEN salary*1.07
END AS new_salary
FROM employee_salary;
```
![[Pasted image 20250112120900.png]]

Example 3 :
```SQL
SELECT first_name,last_name,salary,
CASE
	WHEN salary > 50000 THEN salary*1.05
	WHEN salary <= 50000 THEN salary*1.07
END AS new_salary,
CASE 
	WHEN dept_id = 6 THEN salary*.1
	WHEN dept_id != 6 THEN 0
END AS bonus
FROM employee_salary;
```
![[Pasted image 20250112121430.png]]

