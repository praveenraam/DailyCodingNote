Topic No : 10
Previous Topic : [[AdvSubQueries]]
Next Topic : 

**See for the explanation of Window Function in [Link](https://www.geeksforgeeks.org/window-functions-in-sql/)**

#### Examples

Max salary on each department on 
```SQL
SELECT *,
MAX(salary) OVER(PARTITION BY dept_id) AS Max_Salary
FROM employee_salary;
```

Create a count column by each record
```SQL
SELECT *,
ROW_NUMBER() OVER(ORDER BY salary) AS COUNT_VAL
FROM employee_salary;
```

Create a column by each dept_id member
```SQL
SELECT *,
ROW_NUMBER() OVER(PARTITION BY dept_id ORDER BY salary) AS count_val
FROM employee_salary;
```
This will give separate number for each people in dept

