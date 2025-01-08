Topic No : 6
Previous Topic : [[UNION]]
Next Topic :

### What is a string function
String Functions are powerful tools that allow you to manipulate, format, and extract specific parts of text data in your database.

### Length
##### String Length
Syntax
```SQL
SELECT LENGTH(column_name)
FROM table_name;
```
Example :
```SQL
SELECT LENGTH(first_name)
FROM employee_demographics;
```
##### Upper & Lower
Syntax : 
```SQL
SELECT UPPER(column_name)
FROM table_name;
```
```SQL
SELECT LOWER(column_name)
FROM table_name;
```

Example :
```SQL
SELECT UPPER(first_name),LOWER(last_name)
FROM employee_demographics;
```
##### Trim
Remove the whitespace in the string
There is `LTRIM` and `RTRIM` which remove on left and right side whitespaces respectively

Syntax :
```SQL
SELECT TRIM(column_name)
FROM table_name;
```
##### Substring 
Remove the character that we no need from string

Syntax : 
```SQL
SELECT LEFT(column_name,No_Of_Characters_From_Left_You_Need)
```
```SQL
SELECT RIGHT(column_name,No_Of_Characters_From_Right_You_Need)
```

Example :
```SQL
SELECT first_name,
LEFT(first_name,4),
RIGHT(last_name,4),
FROM employee_demographics;
```
![[Pasted image 20250108181612.png]]

We have an another function `SUBSTRING`

Syntax : 
```SQL
SELECT SUBSTRING(column_name,FromPosition,No_of_position_to_move_forward)
```

Example 1 : 
```SQL
SELECT first_name,
SUBSTRING(first_name,3,2)
FROM employee_demographics;
```
![[Pasted image 20250108181957.png]]

Example 2 : 
```SQL
SELECT first_name,
SUBSTRING(birth_date,6,2) AS Birth_Month
FROM employee_demographics;
```
![[Pasted image 20250108182213.png]]

##### Replace 
Replace a certain characters with another certain characters
These are case-sensitive

```SQL
SELECT REPLACE(column_name,'Characters_to_be_replaced','Characters_going_to_replace');
FROM table_name;
```

##### Locate 

Locate a certain characters in the string
These are case-sensitive

```SQL
SELECT LOCATE('Characters_to_find',column_Name)
FROM table_name;
```
Example :
```SQL
SELECT first_name,LOCATE('A',first_name)
FROM employee_demographics;
```

![[Pasted image 20250108183744.png]]

##### Concat

Combines two different string

Syntax :
```SQL
SELECT CONCAT(string1,string2); /* Can include one more also */
```
```SQL
SELECT CONCAT(column1,' ',column2) /* Giving a space */ 
FROM employee_demographics;
```

Example :
```SQL
SELECT CONCAT(first_name,' ',last_name) AS Full_name
FROM employee_demographics;
```

