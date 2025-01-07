Topic : 4
Previous Topic : [[WHERE]]
Next Topic : [[JOIN]]

### What is Group By
A group by Statement in SQL is used for organizing and summarizing data based on the identical values in specific columns.

This also gets the `DISTINCT` values.
##### Example 1 :
```SQL
SELECT gender 
FROM parks_and_recreation.employee_demographics
GROUP BY gender;
```
```Output
Male 
Female
```
##### Example 2 : Wrong
```SQL
SELECT first_name
FROM parks_and_recreation.employee_demographics
GROUP BY gender;
```
This give error because the `first_name` can't apply aggregate function.
###### Correct Version :
```SQL
SELECT gender, AVG(age) AS average_age
FROM parks_and_recreation.employee_demographics
GROUP BY gender;
```
This gives result as 
![[Pasted image 20250106161400.png]]
#### Example 3
```SQL
SELECT gender, AVG(age), MAX(age)
FROM parks_and_recreation.employee_demographics
GROUP BY gender;
```
Return gender, avg age of both gender, Max age of both gender.
#### Example 4 :
```SQL
SELECT occupation,salary
FROM parks_and_recreation.employee_salary
GROUP BY occupation,salary;
```
Both Occupation and Salary with only unique values of both combination.

### What is Order By

Order by is used to sort the data in ACS/DESC, by default `ORDER BY` sort by decs.
```SQL
SELECT first_name,age
FROM parks_and_recreation.employee_demographics
ORDER BY age;
```
```SQL
/* FOR DESCENDING ORDER */
ORDER BY age DESC;
```

##### For multiple Ordering condition
```SQL
SELECT first_name,gender
FROM parks_and_recreation.employee_demographics
ORDER BY gender,age;
```
![[Pasted image 20250106174652.png]]

```SQL
SELECT first_name,gender,age
FROM parks_and_recreation.employee_demographics
ORDER BY gender,age;
```
![[Pasted image 20250106174728.png]]

```SQL
SELECT first_name,gender,age
FROM parks_and_recreation.employee_demographics
ORDER BY first_name,gender,age;
```
![[Pasted image 20250106174902.png]]

The difference two example is the sorting is done by the order we give the column after `ORDER BY` statement, 

##### Adding `DESC` is similar to this also
```SQL
SELECT first_name,gender,age
FROM parks_and_recreation.employee_demographics
ORDER BY gender,age;
```

### What is Having 

`HAVING` is used to filter out after data after applying the `GROUP BY` method, as we can't use `WHERE` keyword, so instead we use `HAVING` 

##### Example 1 :
```SQL
SELECT gender,AVG(age)
FROM parks_and_recreation.employee_demographics
GROUP BY gender
HAVING AVG(age)>40; /* Can't use group here because we need to filter result */
```

##### Example 2 :
```SQL
SELECT occupation,AVG(salary)
FROM parks_and_recreation.employee_salary
WHERE occupation LIKE '%manager' /* Used for filtering data sent to GROUP BY */
GROUP BY occupation
HAVING AVG(salary) > 50000; /* Used for filtering the result of GROUP BY */
```

### What is Limit

Limiting the result of the statement to a certain no, combining this with ORDER to maximize this.
```SQL
SELECT * 
FROM parks_and_recreation.employee_demographics
LIMIT 3; /* Return first 3 elements */
```

##### Example : 3 Oldest Employee
```SQL
SELECT *
FROM parks_and_recreation.employee_demographics
ORDER BY age DESC 
LIMIT 3;
```

##### Example : Ranging between number
Actually this time limit takes 2 arguments, first one is for from where to start and second one is for this for this many count.
```SQL
SELECT *
FROM parks_and_recreation.employee_demographics
ORDER BY age 
LIMIT 3,5 /* FROM 4 to 9 range 8 */
```

### What is Aliasing
A user-defined object or a temporary name for a table or column in an SQL query

```SQL
SELECT gender, AVG(age) as avg_age
FROM parks_and_recreation.employee_demographics
GROUP BY gender
HAVING avg_age>40;
```
