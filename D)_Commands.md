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

