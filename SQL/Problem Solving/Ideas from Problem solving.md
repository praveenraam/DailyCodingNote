
## Handling NULL Values in SQL Queries

When working with SQL, it's important to explicitly mention if you need to include `NULL` values in your query results.

#### **Why?**

- The condition `column_name != value` **does not** return rows where `column_name` is `NULL`.
- This happens because `NULL` represents an unknown value, and any comparison (`=`, `!=`, `<`, `>`, etc.) with `NULL` results in `UNKNOWN`, not `TRUE` or `FALSE`.

#### **Example**

Given the following SQL query:
```SQL
SELECT name  
FROM Customer  
WHERE referee_id != 2;
```

👉 This query **excludes** rows where `referee_id` is `NULL`.
------ ----

## **How to Include NULL Values?**

To ensure that rows with `NULL` values are included in the result, explicitly check for `NULL` using `IS NULL`:

```SQL
SELECT name  
FROM Customer  
WHERE referee_id != 2 OR referee_id IS NULL;
```

#### **Key Takeaway**

Whenever you need `NULL` values in your results, **always explicitly mention `IS NULL`** in your `WHERE` condition.

## Left join excluding inner join for MySQL and PostgreSQL

A **LEFT JOIN** returns all the rows from the left table and only the matching rows from the right table. If there is no match, the right table’s columns will show **NULL** values.

To exclude the common rows (which are present in both tables), we need to **filter out** those rows using a `WHERE` condition.

**Important:** MySQL and PostgreSQL do **not** have a built-in way to directly exclude the matching rows from a **LEFT JOIN**. Instead, we use `WHERE right_table.column IS NULL` to get only the rows that exist **only** in the left table.

![[Pasted image 20250315115608.png]]


Ex : 

![[Pasted image 20250315122218.png]]

```SQL
SELECT
    V.customer_id,
    COUNT(V.visit_id) AS count_no_trans
FROM Visits as V
LEFT JOIN
    Transactions as T
    ON T.visit_id = V.visit_id
WHERE T.transaction_id IS NULL
GROUP BY V.customer_id
;
```

------ ----
## Days in between dates 

The function `DATEDIFF(DATE1, DATE2)` returns the number of days between `DATE1` and `DATE2`.
- If `DATE1` is **after** `DATE2`, the result is **positive**.
- If `DATE1` is **before** `DATE2`, the result is **negative**.
- If both dates are the same, the result is **0**.

![[Pasted image 20250315122355.png]]

```SQL
SELECT w1.id as Id
FROM Weather w1
INNER JOIN
    Weather w2
    ON DATEDIFF(w1.recordDate,w2.recordDate) = 1
WHERE w1.temperature > w2.temperature
;
```

------ ----
## **How a Loop in JOIN Works**

![[Pasted image 20250316115853.png]]

Write a solution to find managers with at least **five direct reports**.  
Return the result table in **any order**.  
The result format is shown in the example below:

![[Pasted image 20250316115915.png]]

Initially, my idea for solving the problem was to use the `GROUP BY` clause, but it didn't work:

``` SQL
SELECT name  
FROM Employee  
WHERE COUNT(managerId) >= 5  
GROUP BY managerId;;
```
Here, SQL first finds **Dan** matching `101` and counts the other employees. However, when we try to print the name, we end up getting **"Dan"** as the result instead of the correct manager.

To fix this, we need to **track `101` in `manager_id` on `id`** and then use `GROUP BY (managerId)` to ensure that the result is **"John"** instead.

### **Solution:**

```SQL
SELECT e1.name  
FROM Employee as e1  
INNER JOIN  
    Employee as e2  
    ON e1.id = e2.managerId  
GROUP BY (e1.id)  
HAVING COUNT(e2.managerId) >= 5;
```
Now, we find `101` in the `id` of **John** and then search for employees where `managerId = 101`. This ensures we retrieve the correct result. 🚀

----- -----

## Aggregate Function

### Mod
- In sql `id%2 = 1` can be found using `MOD(id,2) = 1`, 
- MOD is used to find the remainder in the sql

### Find avg ourself

There maybe situation where we need to find the avg ourself,

![[Pasted image 20250317121049.png]]

In this problem, we need to divide the total Product Price with no of product, incase of avg used, it will take total Product Price with 2 as there are only two rows, so we need to calculate ourself

```SQL
SELECT
    p.product_id,
    ROUND(
        SUM(p.price*u.units)
        /
        SUM(u.units)
    ,2) as average_price
FROM
    Prices as p
LEFT JOIN
    UnitsSold as u
    ON p.product_id = u.product_id
WHERE
    u.purchase_date BETWEEN p.start_date AND p.end_date OR u.units is null
GROUP BY p.product_id
;
```

---- ---- 
## If we need to find the number of row in a table while inside another query

Just write the sub-query to find it

```SQL
SELECT
    contest_id,
    ROUND(  
        (
            COUNT(user_id)
            /
            (
                SELECT COUNT(user_id) -- this is for counting total no of users
                FROM Users
            )
        )*100
    ,2) as percentage
FROM
    Register
GROUP BY
    contest_id
```

--- --- 
## To order a row by decs and applying asc if tie happens

```SQL
SELECT
    contest_id,
    ROUND(  
        (
            COUNT(user_id)
            /
            (
                SELECT COUNT(user_id) -- this is for counting total no of users
                FROM Users
            )
        )*100
    ,2) as percentage
FROM
    Register
GROUP BY
    contest_id
ORDER BY
    percentage DESC, -- Mention explicitly
    contest_id ASC
;
```

--- --- 
### Can't use WHERE to alias

We can't use where to alias because in SQL, the executer evaluates the `WHERE` before `SELECT`

So in alternate we will using `HAVING`

```SQL
SELECT
    employee_id,
    name,
    (
        SELECT COUNT(e2.employee_id)
        FROM Employees e2
        WHERE e1.employee_id = e2.reports_to
    ) as reports_count,
    (
        SELECT ROUND(AVG(e2.age))
        FROM Employees e2
        WHERE e1.employee_id = e2.reports_to
    ) as average_age
FROM Employees e1
WHERE reports_count > 0 AND average_age IS NOT NULL
;
```
```Error
Unknown column 'reports_count' in 'where clause'
```

##### Correct Query
```SQL
SELECT
    employee_id,
    name,
    (
        SELECT COUNT(e2.employee_id)
        FROM Employees e2
        WHERE e1.employee_id = e2.reports_to
    ) as reports_count,
    (
        SELECT ROUND(AVG(e2.age))
        FROM Employees e2
        WHERE e1.employee_id = e2.reports_to
    ) as average_age
FROM Employees e1
HAVING reports_count > 0 AND average_age IS NOT NULL -- Changed to HAVIng
ORDER BY employee_id
;
```

## Sub query should return only one row

```SQL
SELECT
    employee_id,
    name,
    COUNT(
        SELECT e2.employee_id
        FROM Employees e2
        WHERE e1.employee_id = e2.reports_to
    ) as reports_count,
    ROUND(AVG(
        SELECT e2.age
        FROM Employees e2
        WHERE e1.employee_id = e2.reports_to
    )) as average_age
FROM Employees e1
HAVING reports_count > 0 AND average_age IS NOT NULL
ORDER BY employee_id
;
```
```
check the manual that corresponds to your MySQL server version for the right syntax to use near 
	'SELECT e2.employee_id FROM Employees e2 WHERE e1.employee_id = e' at line 6
```

This is nothing but saying that sub query should return only one row, so we use function inside the sub query itself

```SQL
SELECT
    employee_id,
    name,
    (
        SELECT COUNT(e2.employee_id)
        FROM Employees e2
        WHERE e1.employee_id = e2.reports_to
    ) as reports_count,
    (
        SELECT ROUND(AVG(e2.age))
        FROM Employees e2
        WHERE e1.employee_id = e2.reports_to
    ) as average_age
FROM Employees e1
HAVING reports_count > 0 AND average_age IS NOT NULL
ORDER BY employee_id
;
```

### IFNULL

If a certain statement is expected to be null, we can handle it using `IFNULL(NULL,HANDLING)`
```SQL
SELECT IFNULL(
	NULL, 
	-- Handling Logic
	"Handled Null"
);
```
