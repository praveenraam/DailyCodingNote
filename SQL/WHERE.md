Topic No : 2
Previous Topic : [[SELECT]]
Next Topic : 

### What is where
This returns the rows that met the specific condition given by us.

### Conditional Operators in SQL
| Operator | Description                                                                                                                                 |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| =        | The SQL Equal Operator checks if the values of two operands are equal.                                                                      |
| !=       | The SQL Not Equal Operator checks if the values of two operands are not equal.                                                              |
| >=       | The SQL Greater Than Equals to Operator checks if the value of the left operand is greater than or equal to the value of the right operand. |
| <        | The SQL Less Than Operator checks if the value of the left operand is less than the value of the right operand.                             |
| >        | The SQL Greater Than Operator checks if the value of the left operand is greater than the value of the right operand.                       |
| <=       | The SQL Less Than Equals to Operator checks if the value of the left operand is less than or equal to the value of the right operand.       |
### Syntax
```SQL
/* Your statement SELECT or DELETE or UPDATE or etc.. */
WHERE condition;
```

Ex 1 : Integer
```SQL
SELECT 
	first_name,
	employee_salary
FROM parks_and_recreation.employee_salary
WHERE
	salary > 50000;
```
This is used to eliminate the rows that have less than or equal salary than 50000, 
- Include the salary of 50000, ``salary >= 50000``.
- Only employee with less than 50000, ``salary < 50000``
- Only employee with equal to 50000, ``salary = 50000``

Ex 2 : String
```SQL
SELECT
	first_name
FROM parks_and_recreation.employee_demographics
WHERE
	gender = 'female';
```
This will list all the first names who's genders are `female`

Ex 3 : Date
```SQL
SELECT 
	first_name,
	birth_date
FROM parks_and_recreation.employee_demographics
WHERE
	birth_date >= '1985-01-01';
```
This will list the person who born on or before `1985-01-01` and the format of date can differ as per the format used in columns

### Logical operators

There are two logical operators
- AND
- OR

##### Syntax 
```SQL
/* Our Statement */
WHERE condition1 AND condition2 /* Both has to be true */
```
```SQL
/* Our Statement */
WHERE condition1 OR condition2 /* Atleast one has to be true */
```

Ex : 
```SQL
SELECT 
	first_name,
	age
FROM parks_and_recreation.employee_demographics
WHERE
	birth_date >= '1985-01-01' OR gender != 'male';
```

##### Nested Usage
Ex :
```SQL
SELECT 
	first_name,
	age
FROM parks_and_recreation.employee_demographics
WHERE 
	(first_name = 'Leslie' AND age = 44) OR gender = 'male';
```
List the only girl `Leslie` if age if 44 and all other `males`

### LIKE statement

This statement has use case,
It has two symbols
- `%` percentage : anything
- `_` underscore : specific

This can be used for all the Data types within `' '` or `" "`.
##### `%` Percentage
```SQL
SELECT 
	first_name,
	age
FROM parks_and_recreation.employee_demographics

WHERE 
	first_name LIKE '%er' /* anything that has er at end are given as result */
```
```SQL
WHERE
	first_name LIKE 'Je%' /* anything that has Je as start are given as result */
```
```SQL
WHERE
	first_name LIKE '%er%' /* anything that has er in it are returned, either start or end or in middle somewhere */ 
```
```SQL
WHERE
	birth_date LIKE '1985%' /* return all the one's born on 1985 */
```

##### `_` Underscore
```SQL
SELECT 
	first_name,
	age
FROM parks_and_recreation.employee_demographics

WHERE 
	first_name LIKE 'a__' /* return string has a in start and contains only 2 characters after that */
```
```SQL
WHERE
	first_name LIKE '__a' /* return string has a in the end and contains only 3 character before that */
```
```SQL
WHERE 
	first_name LIKE '__a_' /* return 5 character string with a as the 3rd letter
```

##### Combining both
```SQL
SELECT 
	first_name,
	age
FROM parks_and_recreation.empoyee_demogrpahics

WHERE 
	first_name LIKE '_a%' /* return string has a as 2nd character and after that anything can be coming */
```

