Topic No : 9
Previous Topic : [[SubQueries]]
Next Topic : 

When compiler encounters the situation of sub query, that is executed first and then using the result of it, the main query is executed.
### Here we will solve some problems

##### Finding the average salary
```SQL
SELECT AVG(salary) FROM employee_salary;
```

##### Filter employees earning more then avg salary
```SQL
SELECT *
FROM employee_demographics
WHERE employee_id IN (
	SELECT employee_id 
	FROM employee_salary
	WHERE (SELECT AVG(salary) FROM employee_salary) < salary
);
```

##### Display their Salary also
```SQL
SELECT DEMO.employee_id.first_name, DEMO.last_name, SAL.salary
FROM employee_demographics AS DEMO
INNER JOIN employee_salary AS SAL
	ON DEMO.employee_id = SAL.employee_id
WHERE DEMO.employee_id IN (
	SELECT employee_id 
	FROM employee_salary
	WHERE (SELECT AVG(salary) FROM employee_salary) < salary
);
```

### Types of Sub-Query

##### Scalar Query
This only return a result of one row or one column.

```SQL
SELECT AVG(salary) FROM employee_salary;
```
We used this as sub Query as this only returns the avg salary in one row.

##### Multiple row subquery

- **Return multiple columns and multiple rows**
```SQL
/* FINDING MAX SALARY IN EACH DEPARTMENT */
SELECT dept_id, MAX(salary)
FROM employee_salary AS SAL
INNER JOIN parks_departments AS PD
	ON SAL.dept_id = PD.department_id
GROUP BY dept_id;
```

```SQL
/* Employee who earns highest in each department, this query may not run in all SQL */
SELECT *
FROM employee_demographics
WHERE (SAL.dept_id,SAL.salary) IN (
	SELECT dept_id, MAX(salary)
	FROM employee_salary AS SAL
	INNER JOIN parks_departments AS PD
		ON SAL.dept_id = PD.department_id
	GROUP BY SAL.dept_id
);
```

- **Return 1 column and multiple rows**
```SQL
SELECT PD.department_id
FROM parks_departments AS PD
LEFT JOIN employee_salary AS ES
	ON PD.department_id = ES.dept_id
WHERE ES.dept_id IS NULL;
```

##### Correlated Query
**A [correlated subquery](https://www.geeksforgeeks.org/videos/sql-correlated-subqueries/) is a subquery in SQL that refers to values from the outer query.**

Listing out employee's salary greater than their dept salary avg.
```SQL
SELECT DOM.employee_id,DOM.first_name,SAL.salary
FROM employee_demographics AS DOM
INNER JOIN employee_salary AS SAL
	ON DOM.employee_id = SAL.employee_id
WHERE SAL.employee_id IN  (
	SELECT SAL1.employee_id
	FROM employee_salary AS SAL1
	WHERE SAL1.salary > (
		SELECT AVG(salary)
		FROM employee_salary AS SAL2
		WHERE SAL2.dept_id = SAL1.dept_id
		)
	)
;
```

Here in the inner Query 
```SQL
SELECT SAL1.employee_id
	FROM employee_salary AS SAL1
	WHERE SAL1.salary > (
		SELECT AVG(salary)
		FROM employee_salary AS SAL2
		WHERE SAL2.dept_id = SAL1.dept_id -- We compare with the outer query's dept to find the dept for finding avg.
		)
	)
;
```

