# Ddl, dml , dcl, tcl

DDL (Data Definition Language) and DML (Data Manipulation Language) are two types of SQL statements used to interact with a database.

### 1. **DDL (Data Definition Language)**
DDL commands are used to define or modify the structure of database objects such as tables, indexes, schemas, etc. These commands deal with the schema and structure of the database.

#### Common DDL Commands:
- **CREATE:** Used to create new database objects (e.g., tables, indexes, views).
  ```sql
  CREATE TABLE Students (
      StudentID INT PRIMARY KEY,
      Name VARCHAR(50),
      Age INT
  );
  ```
- **ALTER:** Used to modify the structure of an existing database object (e.g., adding a column to a table).
  ```sql
  ALTER TABLE Students
  ADD COLUMN Address VARCHAR(100);
  ```
- **DROP:** Used to delete a database object (e.g., table, index).
  ```sql
  DROP TABLE Students;
  ```
- **TRUNCATE:** Used to remove all records from a table, but the table structure remains intact.
  ```sql
  TRUNCATE TABLE Students;
  ```
- **RENAME:** Used to rename a database object.
  ```sql
  RENAME TABLE Students TO Learners;
  ```

### 2. **DML (Data Manipulation Language)**
DML commands are used to manipulate data stored in database objects. These commands deal with the data within the database tables.

#### Common DML Commands:
- **INSERT:** Used to insert new records into a table.
  ```sql
  INSERT INTO Students (StudentID, Name, Age)
  VALUES (1, 'John Doe', 20);
  ```
- **UPDATE:** Used to update existing records within a table.
  ```sql
  UPDATE Students
  SET Age = 21
  WHERE StudentID = 1;
  ```
- **DELETE:** Used to delete records from a table.
  ```sql
  DELETE FROM Students
  WHERE StudentID = 1;
  ```
- **SELECT:** Used to retrieve data from one or more tables.
  ```sql
  SELECT Name, Age
  FROM Students
  WHERE Age > 18;
  ```

### Summary:
- **DDL** is concerned with defining the structure and schema of a database.
- **DML** is concerned with manipulating the data within that structure. 

These two types of SQL commands together allow you to fully manage and interact with a database.

DCL (Data Control Language) and TCL (Transaction Control Language) are two other categories of SQL commands that focus on controlling access to data and managing transactions, respectively.

### 1. **DCL (Data Control Language)**
DCL commands are used to control access to data in the database. They manage the permissions and access rights of users.

#### Common DCL Commands:
- **GRANT:** Used to give users access privileges to the database objects.
  ```sql
  GRANT SELECT, INSERT ON Students TO user_name;
  ```
  This command allows `user_name` to perform `SELECT` and `INSERT` operations on the `Students` table.

- **REVOKE:** Used to remove previously granted access privileges from users.
  ```sql
  REVOKE INSERT ON Students FROM user_name;
  ```
  This command removes the `INSERT` permission from `user_name` for the `Students` table.

### 2. **TCL (Transaction Control Language)**
TCL commands are used to manage transactions in the database. A transaction is a sequence of operations performed as a single logical unit of work. TCL commands ensure that transactions are processed correctly and maintain the integrity of the database.

#### Common TCL Commands:
- **COMMIT:** Used to save the changes made by the current transaction permanently to the database.
  ```sql
  COMMIT;
  ```
  After a `COMMIT`, the changes made in the transaction are permanent and visible to other users.

- **ROLLBACK:** Used to undo the changes made by the current transaction, reverting the database to its previous state.
  ```sql
  ROLLBACK;
  ```
  If something goes wrong during a transaction, `ROLLBACK` can be used to undo all the changes made in that transaction.

- **SAVEPOINT:** Used to set a point within a transaction to which you can later roll back.
  ```sql
  SAVEPOINT savepoint_name;
  ```
  You can roll back to a specific savepoint within a transaction using:
  ```sql
  ROLLBACK TO savepoint_name;
  ```

- **SET TRANSACTION:** Used to specify characteristics for the transaction, such as the isolation level.
  ```sql
  SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
  ```
  This command sets the transaction isolation level to `SERIALIZABLE`, which is the highest level of isolation.

### Summary:
- **DCL** commands manage user permissions and control access to database objects.
- **TCL** commands manage the transactions within a database, ensuring that they are completed correctly and allowing for rollback in case of errors. 

Together with DDL and DML, DCL and TCL commands provide a comprehensive set of tools for database management and operation.