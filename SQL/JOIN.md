Topic No : 5
Previous Topic : [[GROUP & ORDER BY]]
Next Topic : [[Union]]

### What is `JOIN`
The `JOIN` is used to join two or more tables and giving a view to us.

### Syntax

```SQL
SELECT *
FROM table_1
jointype JOIN table_2
	ON table_1.column_name_to_compare = talbe_2.column_name_to_compare;
```
### Types of Table


##### `INNER JOIN`
Used to return the column values that are common to both the ``table_1.column_name_to_compare = talbe_2.column_name_to_compare;``

Example 1 : 
```SQL
SELECT *
FROM parks_and_recreation.employee_demographics AS ED
INNER JOIN parks_and_recreation.employee_salary AS ES
	ON ED.employee_id = ES.employee_id;
```

Output : ![[Pasted image 20250107174312.png]]
We can see that the `employee_id` 2 is missing, because there is no ID 2 in table `employee_demographics`, so as we already discussed `INNER` only take common values between them.

Example 2 :
```SQL
SELECT ED.employee_id,age,occupation
FROM employee_demographics AS ED
INNER JOIN employee_salary AS ES
	ON ED.employee_id = ES.employee_id;
/* We need to mention which table's column we are refering from if we are handling two columns with same name from different tables
```

Output : 
![[Pasted image 20250107175201.png]]

##### `LEFT JOIN`
This only consider the values from the `LEFT` table's column and ignores the `RIGHT` table. This include the Common values also.
- `LEFT` mean first mentioning table
- `RIGHT` mean the other one.

Example : 
```SQL
SELECT *
FROM employee_demographics AS ED
LEFT JOIN employee_salary AS ES
	ON ED.employee_id = ES.employee_id;
```

Output : 
![[Pasted image 20250107180810.png]]Take the values only from the `LEFT` table's column.

##### `RIGHT JOIN`
This only consider the value from the `RIGHT` table's column and ignores the `LEFT` table. This include the Common values also.

Example : 
```SQL
SELECT *
FROM employee_demographics AS ED
RIGHT JOIN employee_salary AS ES
	ON ED.employee_id = ES.employee_id;
```

Output :
![[Pasted image 20250107181327.png]]This takes all the values from `RIGHT` table, as `employee_demographics` don't have ID 2, it display as `NULL`.
##### Multiple Joins
Joining more than 2 tables.

```SQL
SELECT *
FROM employee_demographics AS ED
INNER JOIN employee_salary AS ES
	ON ED.employee_id = ES.employee_id
INNER JOIN parks_departments AS PD
	ON PD.department_id = ES.dept_id;
```

Output :
![[Pasted image 20250107182938.png]]
We combined 3 tables, one by  `ED.employee_id` & `ES.employee_id`, this result is combined with table `result.depratment_id` with `PD.deparment_id`.

