# 📘 SQL Commands | DDL, DQL, DML, DCL, TCL

---

## 📌 What are SQL Commands?

SQL commands are **instructions** used to **interact with a database** — jaise ki data ko create karna, update karna, delete karna, ya query karna. Yeh commands 5 categories mein divide ki gayi hain:

### 🔹 Types of SQL Commands:
| Category | Description |
|----------|-------------|
| **DDL** | Data Definition Language |
| **DML** | Data Manipulation Language |
| **DQL** | Data Query Language |
| **DCL** | Data Control Language |
| **TCL** | Transaction Control Language |

---

## 1️⃣ DDL – **Data Definition Language**

DDL ka use **database objects ka structure define karne ke liye** hota hai — jaise **tables, schemas, indexes**.

### 📄 Common DDL Commands:

| Command | Description | Syntax |
|--------|-------------|--------|
| `CREATE` | Creates DB objects | `CREATE TABLE table_name (...);` |
| `DROP` | Deletes DB objects | `DROP TABLE table_name;` |
| `ALTER` | Modifies DB objects | `ALTER TABLE table_name ADD column_name datatype;` |
| `TRUNCATE` | Deletes all data from a table | `TRUNCATE TABLE table_name;` |
| `COMMENT` | Adds comment to DB objects | `COMMENT ON TABLE table_name IS 'text';` |
| `RENAME` | Renames DB objects | `RENAME old_name TO new_name;` |

### ✅ Real-World Example:
```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    hire_date DATE
);
```
> 👉 Explanation: HR department ne naye employees store karne ke liye ek table create kiya.

---

## 2️⃣ DQL – Data Query Language
DQL ka main kaam hota hai data ko fetch karna. Ismein sirf SELECT command aata hai.

### 📄 DQL Command:
| Command  | Description    | Syntax                                            |
| -------- | -------------- | ------------------------------------------------- |
| `SELECT` | Retrieves data | `SELECT column1 FROM table_name WHERE condition;` |

### ✅ Real-World Example:
```sql
SELECT first_name, last_name, hire_date
FROM employees
WHERE department = 'Sales'
ORDER BY hire_date DESC;
```
> 👉 Explanation: Sales department ke sabhi employees ko unke hire date ke basis pe descending order mein dikhana.

--- 

## 3️⃣ DML – Data Manipulation Language
DML commands ka use data insert, update, delete karne ke liye hota hai.

### 📄 Common DML Commands:
```sql
| Command  | Description                 | Syntax                                       |
| -------- | --------------------------- | -------------------------------------------- |
| `INSERT` | Adds new record             | `INSERT INTO table_name VALUES (...);`       |
| `UPDATE` | Modifies existing record    | `UPDATE table SET column = value WHERE ...;` |
| `DELETE` | Removes record              | `DELETE FROM table WHERE ...;`               |
| `LOCK`   | Locks table for transaction | `LOCK TABLE table_name IN lock_mode;`        |
| `CALL`   | Calls stored procedure      | `CALL procedure_name(...);`                  |
```

### ✅ Real-World Example:
```sql
INSERT INTO employees (first_name, last_name, department) 
VALUES ('Jane', 'Smith', 'HR');
```
> 👉 Explanation: Naye employee ka record HR department mein add karna.

--- 

## 4️⃣ DCL – Data Control Language
DCL ka use user permissions set karne ke liye hota hai. Jaise kis user ko kya access dena hai database mein.

### 📄 Common DCL Commands:
| Command  | Description    | Syntax                                             |
| -------- | -------------- | -------------------------------------------------- |
| `GRANT`  | Gives access   | `GRANT SELECT, UPDATE ON table_name TO user_name;` |
| `REVOKE` | Removes access | `REVOKE SELECT ON table_name FROM user_name;`      |

### ✅ Real-World Example:
```sql
GRANT SELECT, UPDATE ON employees TO hr_user;
```
> 👉 Explanation: `hr_user` ko employees table mein data dekhne aur update karne ki permission dena.

---

## 5️⃣ TCL – Transaction Control Language
TCL ka use transactions ko manage karne ke liye hota hai — jaise save, rollback, ya checkpoint create karna.

### 📄 Common TCL Commands:
| Command     | Description           | Syntax               |
| ----------- | --------------------- | -------------------- |
| `BEGIN`     | Start a transaction   | `BEGIN TRANSACTION;` |
| `COMMIT`    | Save all changes      | `COMMIT;`            |
| `ROLLBACK`  | Undo all changes      | `ROLLBACK;`          |
| `SAVEPOINT` | Create rollback point | `SAVEPOINT sp_name;` |

### ✅ Real-World Example:
```sql
BEGIN TRANSACTION;
UPDATE employees SET department = 'Marketing' WHERE department = 'Sales';
SAVEPOINT before_update;
UPDATE employees SET department = 'IT' WHERE department = 'HR';
ROLLBACK TO SAVEPOINT before_update;
COMMIT;
```
> 👉 Explanation: Sales ko Marketing mein convert kiya, HR ko IT mein convert kiya, fir HR wala rollback kiya. Final commit mein sirf Sales → Marketing change save hua.

---

⭐ Most Frequently Used SQL Commands (🔥 Important for Interviews)
| Command               | Purpose                |
| --------------------- | ---------------------- |
| `SELECT`              | Fetch data             |
| `INSERT`              | Add data               |
| `UPDATE`              | Modify data            |
| `DELETE`              | Remove data            |
| `CREATE TABLE`        | Create structure       |
| `ALTER TABLE`         | Modify structure       |
| `DROP TABLE`          | Remove table           |
| `TRUNCATE TABLE`      | Remove all records     |
| `WHERE`               | Filter                 |
| `ORDER BY`            | Sort                   |
| `GROUP BY`            | Group rows             |
| `HAVING`              | Filter groups          |
| `JOIN`                | Combine data           |
| `DISTINCT`            | Remove duplicates      |
| `IN / BETWEEN / LIKE` | Advanced filters       |
| `UNION`               | Combine queries        |
| `GRANT` / `REVOKE`    | Access control         |
| `COMMIT` / `ROLLBACK` | Save/Undo transactions |

---

## 🧠 Final Thoughts
✅ SQL commands help us control, retrieve, and modify data in any real-world database.

##📍 Project Example:
Aap ek e-commerce website bana rahe ho jahan pe products, users, aur orders tables honge.

- Table structure banane ke liye → DDL
- Product add/update/delete karne ke liye → DML
- Product list dikhane ke liye → DQL
- Admin ko access dene ke liye → DCL
- Order transactions manage karne ke liye → TCL

--- 

## 🧠 Theory-Based Interview SQL Questions with Answers

### 1. What are the five main categories of SQL commands? Explain each with one example.
#### Answer:
SQL commands are categorized into:

DDL (Data Definition Language) – Defines database structure.
👉 CREATE TABLE employees (...);

DML (Data Manipulation Language) – Manipulates data.
👉 INSERT INTO employees VALUES (...);

DQL (Data Query Language) – Retrieves data.
👉 SELECT * FROM employees;

DCL (Data Control Language) – Controls access.
👉 GRANT SELECT ON employees TO user1;

TCL (Transaction Control Language) – Manages transactions.
👉 COMMIT;, ROLLBACK;

--- 

### 2. Difference between DDL and DML commands?
#### Answer:
| Feature     | DDL                       | DML                          |
| ----------- | ------------------------- | ---------------------------- |
| Purpose     | Defines structure         | Manipulates data             |
| Commands    | `CREATE`, `ALTER`, `DROP` | `INSERT`, `UPDATE`, `DELETE` |
| Auto-commit | Yes                       | No (manual COMMIT needed)    |
| Rollback    | Not possible              | Possible                     |

---

### 3. What does the TRUNCATE command do? How is it different from DELETE?
#### Answer:

TRUNCATE: Quickly removes all rows from a table without logging individual row deletions. Cannot be rolled back.

DELETE: Removes selected rows and can be rolled back if used with a transaction.

🔸 Example:
``` sql
TRUNCATE TABLE employees;  -- DDL  
DELETE FROM employees WHERE dept = 'Sales'; -- DML
```
---

### 4. What is the purpose of the GRANT and REVOKE commands? Which category do they belong to?
#### Answer:

GRANT: Gives permissions to users (e.g., SELECT, UPDATE).

REVOKE: Removes those permissions.

They belong to DCL (Data Control Language).

🔸 Example:
```sql
GRANT SELECT ON employees TO user1;
REVOKE SELECT ON employees FROM user1;
```
---

### 5. Which command would you use to give a user read-only access to the employees table?
#### Answer:
```sql
GRANT SELECT ON employees TO user_name;
```
✅ This gives read-only access because only SELECT permission is granted.

---

### 6. What is the difference between ROLLBACK, COMMIT, and SAVEPOINT in SQL?
#### Answer:
| Command     | Purpose                                            |
| ----------- | -------------------------------------------------- |
| `COMMIT`    | Saves all changes made in the current transaction  |
| `ROLLBACK`  | Reverts all changes since last COMMIT              |
| `SAVEPOINT` | Creates a point within transaction to roll back to |
> 🔸 Use Case: Used in banking to prevent incorrect balance updates. 

---

### 7. Why is SELECT considered part of DQL and not DML?
#### Answer:
- SELECT only reads data; it doesn't modify anything.
- DML involves modifying data (INSERT, UPDATE, DELETE), hence SELECT falls under DQL.

---

### 8. Can we roll back a TRUNCATE operation? Why or why not?
#### Answer:
❌ No, because `TRUNCATE` is a DDL command and auto-commits changes — making rollback impossible.

---

### 9. Give real-life examples where DCL commands are used.
#### Answer:
In a banking system:
👉 Only the manager should be able to `UPDATE` account balances.
```sql
GRANT UPDATE ON accounts TO manager;
REVOKE UPDATE ON accounts FROM intern;
```

---

### 10. Why are TCL commands important in a banking application?
#### Answer:

Ensures data consistency and atomicity in critical operations.

Example: If money is debited from one account but not credited to another, we must ROLLBACK.
```sql
BEGIN TRANSACTION;
-- debit account A
-- credit account B
COMMIT;
```
> If anything fails → use ROLLBACK to revert both.

---


# SQL Commands – Interview Questions & Answers

This file contains theory-based, interview-oriented questions and answers for the following SQL command categories:

- DDL (Data Definition Language)
- DML (Data Manipulation Language)
- DQL (Data Query Language)
- DCL (Data Control Language)
- TCL (Transaction Control Language)
- Advanced/Real-Time Based

---

## 🔸 DDL (Data Definition Language)

### Q1. What is the difference between DROP, TRUNCATE, and DELETE?
- **DROP**: Completely removes the table structure and data from the database. Cannot be rolled back.
- **TRUNCATE**: Deletes all records but keeps the table structure. It’s faster than DELETE and cannot be rolled back (DDL).
- **DELETE**: Deletes rows based on a condition and can be rolled back. Slower, used for selective deletion.

### Q2. Can we use ALTER to rename a column in SQL?
- Yes, using `ALTER TABLE table_name RENAME COLUMN old_name TO new_name;` (Supported in most RDBMS).

### Q3. What happens internally when we run a CREATE TABLE command?
- Allocates metadata, stores table schema in system catalog, and reserves space for data.

### Q4. Does TRUNCATE reset identity columns (auto-increment)?
- Yes, in most databases like SQL Server. In MySQL, you can reset explicitly using `ALTER`.

### Q5. How is RENAME different from ALTER?
- **RENAME** changes table or column name. **ALTER** modifies structure (adds/removes columns, changes datatype).

---

## 🔸 DML (Data Manipulation Language)

### Q1. What is the difference between UPDATE and MERGE?
- **UPDATE**: Used to modify existing records.
- **MERGE**: Combines INSERT, UPDATE, DELETE in a single command for upserts.

### Q2. Can we insert multiple rows using a single INSERT statement?
- Yes. Example: `INSERT INTO table (col1, col2) VALUES (1, 'A'), (2, 'B');`

### Q3. What happens if we don’t specify a WHERE clause in an UPDATE or DELETE?
- All rows will be updated or deleted. Always use WHERE cautiously.

### Q4. How can you copy data from one table to another using DML?
- `INSERT INTO new_table SELECT * FROM old_table;`

### Q5. What is the difference between INSERT INTO SELECT and SELECT INTO?
- `INSERT INTO SELECT`: Requires pre-existing table.
- `SELECT INTO`: Creates new table with selected data.

---

## 🔸 DQL (Data Query Language)

### Q1. How does SELECT DISTINCT work?
- Removes duplicate rows based on selected columns.

### Q2. What is the use of GROUP BY and how is it different from ORDER BY?
- **GROUP BY**: Aggregates rows (e.g., COUNT, SUM).
- **ORDER BY**: Sorts the result set. GROUP BY groups, ORDER BY sorts.

### Q3. Explain use cases for HAVING clause.
- Used with GROUP BY to filter aggregated results. E.g., `HAVING COUNT(*) > 1`.

### Q4. Can we use WHERE with aggregate functions? Why not?
- No, WHERE filters before aggregation. Use HAVING to filter aggregated results.

### Q5. What is the purpose of aliases in SELECT statements?
- Makes result set easier to read or rename columns temporarily. Example: `SELECT col1 AS name`.

---

## 🔸 DCL (Data Control Language)

### Q1. Can we use GRANT to allow a user to create new tables?
- No. Object-level privileges don’t allow CREATE TABLE. Use role/DB-level permissions.

### Q2. What is the difference between WITH GRANT OPTION and a simple GRANT?
- **WITH GRANT OPTION**: Allows the user to grant privileges to others.
- Simple GRANT: Just allows usage of the object.

### Q3. What does CASCADE do in REVOKE?
- Removes privileges from users who were granted access by the revoked user.

### Q4. How is access control implemented in multi-user environments?
- Using roles, privileges, schemas, and user-specific GRANT/REVOKE.

### Q5. Can you restrict SELECT on some columns only?
- Yes, by creating views or granting SELECT on specific columns.

---

## 🔸 TCL (Transaction Control Language)

### Q1. What is a transaction? What are ACID properties?
- A transaction is a group of operations executed as a unit.  
- **ACID**: Atomicity, Consistency, Isolation, Durability.

### Q2. What is the purpose of SAVEPOINT? Can we have multiple savepoints?
- YES. SAVEPOINT creates checkpoints inside a transaction to rollback partially.

### Q3. What happens if you forget to COMMIT after BEGIN TRANSACTION?
- Changes remain uncommitted and will be lost on session end or rollback.

### Q4. Can we roll back a part of a transaction?
- Yes, using `ROLLBACK TO SAVEPOINT`.

### Q5. What is the difference between ROLLBACK TO SAVEPOINT and ROLLBACK?
- `ROLLBACK`: Undoes all changes in the transaction.
- `ROLLBACK TO SAVEPOINT`: Undoes changes after the savepoint.

---

## 🔸 Advanced/Real-Time Based

### Q1. You are inserting multiple rows in a transaction and one fails. How would you handle it?
- Use `TRY-CATCH` or rollback the transaction and retry the failed row.

### Q2. What is the impact of using COMMIT inside a loop while inserting records?
- Each record is committed separately, reducing rollback capability but improving performance.

### Q3. Explain a scenario where TRUNCATE fails.
- If table has foreign key constraints or is referenced in an active transaction.

### Q4. Can DDL commands be rolled back if executed within a transaction block?
- In most databases, **NO**. DDL is auto-commit. In Oracle, some support exists with `EXECUTE IMMEDIATE`.

### Q5. What are implicit vs. explicit transactions in SQL?
- **Implicit**: Auto-commit after each statement.
- **Explicit**: User manually defines BEGIN, COMMIT, ROLLBACK.

---


# 📘 SQL Commands - Query-Based Practice (Hands-On)

## 🔹 DDL (Data Definition Language)

### 1. Create a new table named `employees`.
```sql
CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    emp_name VARCHAR(100),
    department VARCHAR(50),
    salary DECIMAL(10, 2),
    hire_date DATE
);
```

### 2. Add a new column `email` to `employees`.
```sql
ALTER TABLE employees ADD email VARCHAR(100);
```

### 3. Rename column `emp_name` to `full_name`.
```sql
ALTER TABLE employees RENAME COLUMN emp_name TO full_name;
```

### 4. Delete the entire `employees` table.
```sql
DROP TABLE employees;
```

### 5. Remove all rows from the `employees` table but keep structure.
```sql
TRUNCATE TABLE employees;
```

## 🔹 DML (Data Manipulation Language)

### 1. Insert a new record into `employees`.
```sql
INSERT INTO employees (emp_id, full_name, department, salary, hire_date)
VALUES (1, 'John Doe', 'IT', 50000.00, '2023-01-01');
```

### 2. Insert multiple rows.
```sql
INSERT INTO employees (emp_id, full_name, department, salary, hire_date) VALUES
(2, 'Jane Smith', 'HR', 60000.00, '2023-03-10'),
(3, 'Raj Kumar', 'Sales', 45000.00, '2022-07-15');
```

### 3. Update salary of employees in IT department.
```sql
UPDATE employees SET salary = salary + 5000 WHERE department = 'IT';
```

### 4. Delete employee with ID = 3.
```sql
DELETE FROM employees WHERE emp_id = 3;
```

### 5. Copy data to backup table.
```sql
INSERT INTO employees_backup SELECT * FROM employees;
```

## 🔹 DQL (Data Query Language)

### 1. Retrieve all employees from HR.
```sql
SELECT * FROM employees WHERE department = 'HR';
```

### 2. Retrieve distinct departments.
```sql
SELECT DISTINCT department FROM employees;
```

### 3. Group by department and find average salary.
```sql
SELECT department, AVG(salary) AS avg_salary FROM employees GROUP BY department;
```

### 4. Use HAVING to filter departments with avg salary > 50000.
```sql
SELECT department, AVG(salary) AS avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;
```

### 5. Use alias for better readability.
```sql
SELECT full_name AS Name, salary AS Salary FROM employees;
```

## 🔹 DCL (Data Control Language)

### 1. Grant SELECT and UPDATE on employees to user `john`.
```sql
GRANT SELECT, UPDATE ON employees TO john;
```

### 2. Revoke UPDATE permission from user `john`.
```sql
REVOKE UPDATE ON employees FROM john;
```

## 🔹 TCL (Transaction Control Language)

### 1. Transaction with COMMIT.
```sql
BEGIN TRANSACTION;
UPDATE employees SET salary = salary + 2000 WHERE emp_id = 1;
COMMIT;
```

### 2. Transaction with ROLLBACK.
```sql
BEGIN TRANSACTION;
UPDATE employees SET department = 'Finance' WHERE emp_id = 2;
ROLLBACK;
```

### 3. Using SAVEPOINT and ROLLBACK TO.
```sql
BEGIN TRANSACTION;
UPDATE employees SET department = 'Finance' WHERE emp_id = 2;
SAVEPOINT sp1;
UPDATE employees SET department = 'Legal' WHERE emp_id = 1;
ROLLBACK TO sp1;
COMMIT;
```
