Topic No : 10
Previous Topic : [[AdvSubQueries]]
Next Topic : 

**See for the explanation of Window Function in [Link](https://www.geeksforgeeks.org/window-functions-in-sql/)**

#### Examples

###### Max salary on each department on 
```SQL
SELECT *,
MAX(salary) OVER(PARTITION BY dept_id) AS Max_Salary
FROM employee_salary;
```

###### Create a count column by each record
```SQL
SELECT *,
ROW_NUMBER() OVER(ORDER BY salary) AS COUNT_VAL
FROM employee_salary;
```

###### Create a column by each dept_id member
```SQL
SELECT *,
ROW_NUMBER() OVER(PARTITION BY dept_id ORDER BY salary) AS count_val
FROM employee_salary;
```
This will give separate number for each people in dept

###### Listing old employee based on their dept
```SQL
SELECT *
FROM (
	SELECT *,
	ROW_NUMBER() OVER(PARTITION BY dept_id ORDER BY employee_id) AS count_val
	FROM employee_salary
) AS temp_table
WHERE count_val < 3;
```

###### List Employee top 3 employees in each dept with max salary
```SQL
SELECT * 
FROM (
	SELECT *,
	RANK() OVER(PARTITION BY dept_id ORDER BY salary) AS rank_of_sal
	FROM employee_salary
) AS temp_table
WHERE rank_of_sal < 4;
```

```SQL
SELECT * 
FROM (
	SELECT *,
	RANK() OVER(PARTITION BY dept_id ORDER BY salary) AS rank_of_sal,
	DENSE_RANK() OVER(PARTITION BY dept_id ORDER BY salary) AS dense_rank_of_sal
	FROM employee_salary
) AS temp_table
WHERE rank_of_sal < 3;
```
