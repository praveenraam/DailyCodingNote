Topic Referred From [[SQL]]

### Data Definition Language (DDL)

This actually consist of SQL commands that can be used for defining, altering, deleting the database structure such as table, index, schemas.

| Command                                                          | Description                                                                                   | Syntax                                                                     |
| ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| [CREATE](https://www.geeksforgeeks.org/sql-create)               | Create database or its objects (table, index, function, views, store procedure, and triggers) | **CREATE** `TABLE table_name (column1 data_type, column2 data_type, ...);` |
| [DROP](https://www.geeksforgeeks.org/sql-drop-truncate)          | Delete objects from the database                                                              | **DROP** `TABLE table_name;`                                               |
| [ALTER](https://www.geeksforgeeks.org/sql-alter-add-drop-modify) | Alter the structure of the database                                                           | **ALTER** `TABLE table_name ADD COLUMN column_name data_type;`             |
| [TRUNCATE](https://www.geeksforgeeks.org/sql-drop-truncate)      | Remove all records from a table, including all spaces allocated for the records are removed   | **TRUNCATE** `TABLE table_name;`                                           |
| [COMMENT](https://www.geeksforgeeks.org/sql-comments)            | Add comments to the data dictionary                                                           | **COMMENT** `'comment_text' ON TABLE table_name;`                          |
| [RENAME](https://www.geeksforgeeks.org/sql-alter-rename)         | Rename an object existing in the database                                                     | **RENAME** `TABLE old_table_name TO new_table_name;`                       |
### Data Query Language (DQL)

This is used to perform query operation on data from the database. 

When a [SELECT](https://www.geeksforgeeks.org/sql-select-query/) is fired against a table or tables the result is compiled into a further ****temporary table****, which is displayed or perhaps received by the program.

| Command                                                       | Description                                   | Syntax                                                         |
| ------------------------------------------------------------- | --------------------------------------------- | -------------------------------------------------------------- |
| [**SELECT**](https://www.geeksforgeeks.org/sql-select-clause) | It is used to retrieve data from the database | `SELECT column1, column2, ...FROM table_name WHERE condition;` |
### Data Manipulation Language (DML)

This is performed to manipulate the exciting data in the database, and it include the most of SQL statements.

DCL statement is grouped withe DML

| Command | Description                        | Syntax                                                                                   |
| ------- | ---------------------------------- | ---------------------------------------------------------------------------------------- |
| Insert  | Insert the data into the table     | **`**INSERT**`** `INTO table_name (column1, column2, ...) VALUES (value1, value2, ...);` |
| Update  | Update the exciting within a table | **`**UPDATE**`** `table_name SET column1 = value1, column2 = value2 WHERE condition;`    |
| Delete  | Delete a record from the table     | **`**DELETE**`** `FROM table_name WHERE condition;`                                      |
| Lock    | Take control concurrency           | **`**LOCK**`** `TABLE table_name IN lock_mode;`                                          |
### Data Control Language (DCL)

This is performed to deal with giving and taking the permissions and other controls of the database System.

| Command                                                                     | Description                                                                                                                 | Syntax                                                                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| [GRANT](https://www.geeksforgeeks.org/mysql-grant-revoke-privileges)        | Assigns new privileges to a user account, allowing access to specific database objects, actions, or functions.              | **`**GRANT**`** `privilege_type [(column_list)] ON [object_type] object_name TO user [WITH GRANT OPTION];`             |
| [REVOKE](https://www.geeksforgeeks.org/difference-between-grant-and-revoke) | Removes previously granted privileges from a user account, taking away their access to certain database objects or actions. | **`**REVOKE**`** `[GRANT OPTION FOR] privilege_type [(column_list)] ON [object_type] object_name FROM user [CASCADE];` |
### Transaction Control Language (TCL)

Transactions group a set of operations executed as single unit,  If any of the **tasks fail**, the transaction fails. Therefore, a transaction has only two results: **success** or **failure**. We can explore more about transactions.

| Command                                                                       | Description                                        | Syntax                                  |
| ----------------------------------------------------------------------------- | -------------------------------------------------- | --------------------------------------- |
| [BEGIN TRANSACTION](https://www.geeksforgeeks.org/sql-transactions/#:~:text=) | Starts a new transaction                           | `BEGIN TRANSACTION [transaction_name];` |
| [COMMIT](https://www.geeksforgeeks.org/sql-transactions/#:~:text=)            | Saves all changes made during the transaction      | `COMMIT;`                               |
| [ROLLBACK](https://www.geeksforgeeks.org/sql-transactions/#:~:text=)          | Undoes all changes made during the transaction     | `ROLLBACK;`                             |
| [SAVEPOINT](https://www.geeksforgeeks.org/sql-transactions/#:~:text=)         | Creates a savepoint within the current transaction | `SAVEPOINT savepoint_name;`             |
### Important SQL commands : 

- Insert : Used to add data to the database
- Select : Used to retrieve data from database
- Update : Used to modify existing data in a database
- Delete : Used to remove the remove data from the database
- Create Table : Used to create a new table in database
- Alter Table : Used to modify the exciting table
- Drop Table : Used to Delete the table from the database
- Where : It is a type of Clause that is used to filter the data from database
- Order by : Used to sort the result in ascs /decs
- Join : Used to join the two or more tables based on related column between them.

