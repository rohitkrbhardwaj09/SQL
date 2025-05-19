# Query to Insert Multiple Rows

## SELECT Statement

The `SELECT` statement is used to retrieve data from a database. It can return one or many rows, depending on the query conditions.

### Syntax

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### Example

```sql
SELECT name, age
FROM Students
WHERE age > 18;
```

### Key Points

* Use `*` to select all columns.
* The `WHERE` clause filters records.
* `ORDER BY` can be used to sort results.
* Use `LIMIT` to restrict the number of results.

---

## INSERT INTO Statement

The `INSERT INTO` statement is used to add new rows to a table in a database.

### 1. Insert into All Columns

```sql
INSERT INTO table_name
VALUES (value1, value2, ...);
```

* Used when values for **all columns** are provided in order.

#### Example

```sql
INSERT INTO Student
VALUES (5, 'HARSH', 'WEST BENGAL', 'XXXXXXXXXX', 19);
```

### 2. Insert into Specific Columns

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

* Useful when inserting data into specific columns.

#### Example

```sql
INSERT INTO Student (ROLL_NO, NAME, AGE)
VALUES (5, 'PRATIK', 19);
```

### 3. Insert Multiple Rows at Once

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES
  (value1, value2, ...),
  (value1, value2, ...),
  ...;
```

* More efficient than multiple individual inserts.

#### Example

```sql
INSERT INTO Student (ROLL_NO, NAME, AGE, ADDRESS, PHONE)
VALUES
  (6, 'Amit Kumar', 15, 'Delhi', 'XXXXXXXXXX'),
  (7, 'Gauri Rao', 18, 'Bangalore', 'XXXXXXXXXX');
```

### 4. Insert from Another Table

```sql
INSERT INTO target_table
SELECT * FROM source_table;
```

* Copies all data from one table to another.

#### Specific Columns

```sql
INSERT INTO target_table (col1, col2)
SELECT col1, col2
FROM source_table;
```

#### With Condition

```sql
INSERT INTO target_table
SELECT * FROM source_table
WHERE condition;
```

---

## Insert Multiple Rows in SQL

### Table Setup

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    EmployeeName VARCHAR(100),
    Age INT,
    Department VARCHAR(50)
);
```

### 1. Basic INSERT for Multiple Rows

```sql
INSERT INTO Employees (EmployeeID, EmployeeName, Age, Department)
VALUES
    (1, 'John Doe', 30, 'Engineering'),
    (2, 'Jane Smith', 28, 'Marketing'),
    (3, 'Sam Brown', 35, 'Sales'),
    (4, 'Lucy Green', 25, 'Human Resources');
```

* Efficient method for inserting multiple records.

### 2. INSERT INTO ... SELECT

```sql
CREATE TABLE NewEmployees (
    EmployeeID INT PRIMARY KEY,
    EmployeeName VARCHAR(100),
    Age INT,
    Department VARCHAR(50)
);

INSERT INTO NewEmployees (EmployeeID, EmployeeName, Age, Department)
VALUES
    (5, 'Alice Johnson', 29, 'HR'),
    (6, 'Bob Martin', 32, 'Finance'),
    (7, 'Charlie Baker', 28, 'Marketing'),
    (8, 'David Lee', 40, 'Engineering'),
    (9, 'Eva Davis', 22, 'Sales');

INSERT INTO Employees (EmployeeID, EmployeeName, Age, Department)
SELECT EmployeeID, EmployeeName, Age, Department
FROM NewEmployees
WHERE Age > 30;
```

* Useful for copying or transforming data across tables.

### 3. Using Transactions

```sql
BEGIN TRANSACTION;

    INSERT INTO Customers (CustomerID, CustomerName, ContactName, Country)
    VALUES (5, 'Sarah White', 'John White', 'Canada');

    INSERT INTO Customers (CustomerID, CustomerName, ContactName, Country)
    VALUES (6, 'Mohamed Ibrahim', 'Ahmed Ibrahim', 'UAE');

COMMIT;
```

* Ensures either all or none of the operations succeed.
* Use `ROLLBACK` to undo if needed.

---

## Summary

* `INSERT INTO` allows inserting data into a table.
* Multiple rows can be added in one query using a comma-separated list.
* `INSERT INTO ... SELECT` copies data from another query or table.
* Transactions help maintain data integrity during bulk inserts.
* Efficient use of insertions enhances performance and reduces errors.
