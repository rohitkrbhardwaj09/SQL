# 📘 SQL Select Database (Interview Notes)

---

## 🏷️ What is `USE DATABASE`?

The `USE DATABASE` statement is used in SQL-based DBMS (like MySQL) to select a specific database for the current session. Once selected, all further queries will run in the context of this chosen database.

> ⚠️ **Note:** Some DBMS like PostgreSQL do **not** support the `USE` statement. Instead, you must connect directly to the database during connection setup.

### 🔤 Syntax

```sql
USE database_name;
```

## 💡 Real-Life Analogy
> Imagine you enter a library that has multiple sections like History, Science, and Technology. You pick the "Technology" section to read. Now, all your reading is done inside that section—similarly, USE database_name sets the active section for your SQL session.

## 🛠️ Example - SQL Select Database
### ✅ Step 1: Create a Database
```sql
CREATE DATABASE GeeksforGeeks;
```

✅ Step 2: Select the Database
```sql
USE GeeksforGeeks;
```
> 📌 Now any query you run will target GeeksforGeeks DB.

## 🔍 How to Query Data from Selected Database
Let’s consider a table called employees.

### 📊 Table: employees
| id | name    | age | department | salary |
| -- | ------- | --- | ---------- | ------ |
| 1  | Alice   | 30  | Sales      | 50000  |
| 2  | Bob     | 40  | Marketing  | 60000  |
| 3  | Charlie | 35  | Sales      | 55000  |
| 4  | David   | 28  | HR         | 45000  |
| 5  | Eve     | 45  | Marketing  | 65000  |
| 6  | Frank   | 50  | HR         | 70000  |
| 7  | Grace   | 29  | IT         | 48000  |
| 8  | Hannah  | 38  | IT         | 53000  |

## 1️⃣ Basic SELECT Statement 
```sql
SELECT * FROM employees;
```
> 📌 Retrieves all columns and all rows from the employees table.

## 2️⃣ Selecting Specific Columns
```sql
SELECT name, age FROM employees;
```
> 📌 Shows only name and age for all employees.

## 3️⃣ Filtering Results with WHERE 
```sql
SELECT name, age FROM employees WHERE age >= 35;
```
> 📌 Shows employees whose age is 35 or older.

## 4️⃣ Sorting Results with ORDER BY
```sql
SELECT name, age FROM employees ORDER BY age DESC;
```
> 📌 Sorts employees by age in descending order.

## 5️⃣ Limiting Results with LIMIT 
``` sql
SELECT name, salary FROM employees ORDER BY salary DESC LIMIT 3;
```
> 📌 Returns top 3 highest paid employees.

## 6️⃣ Aggregating Data with GROUP BY
```sql
SELECT department, AVG(salary) AS average_salary 
FROM employees 
GROUP BY department;
```
| department | average\_salary |
| ---------- | --------------- |
| Sales      | 52500           |
| Marketing  | 62500           |
| HR         | 57500           |
| IT         | 50500           |
> 📌 Shows average salary for each department.

✅ Conclusion
- USE DATABASE helps in setting the context.
- SELECT helps in extracting the required data.
- Combine WHERE, ORDER BY, LIMIT, and GROUP BY to write efficient queries.

---

# ❓ SQL Select Database – Interview Questions & Answers

---

## 1️⃣ What is the purpose of the `USE` statement in SQL?

**Answer:**  
The `USE` statement sets a specific database as the current database for a session. All subsequent queries will execute in the context of the selected database.

---

## 2️⃣ Is `USE DATABASE` a standard SQL command?

**Answer:**  
No. `USE` is not part of the SQL standard. It is **DBMS-specific**—for example, MySQL and SQL Server support it, but PostgreSQL does not.

---

## 3️⃣ What is the alternative to `USE` in PostgreSQL?

**Answer:**  
In PostgreSQL, you cannot use `USE database_name`. Instead, you connect directly to the desired database at the time of establishing the database connection using a connection string.

---

## 4️⃣ What happens if you don’t use the `USE` command and try to run a query?

**Answer:**  
If a database is not selected and you try to run a query like `SELECT * FROM table_name`, you'll get an error saying the table does not exist because SQL doesn't know which database you're referring to.

---

## 5️⃣ Can you switch databases mid-session?

**Answer:**  
Yes, you can use `USE database_name` again to switch to another database in systems that support it (like MySQL).

---

## 6️⃣ How do you view the current database you are using?

**Answer (MySQL):**
```sql
SELECT DATABASE();
```

## 7️⃣ What does the SELECT statement do in SQL?
**Answer:**
The SELECT statement retrieves data from one or more tables in a database. It can be used with clauses like WHERE, ORDER BY, LIMIT, and GROUP BY to filter, sort, and aggregate data.

---

## 8️⃣ How do you retrieve only selected columns using SELECT?
**Answer:**
```sql
SELECT column1, column2 FROM table_name;
```
> 📌 This fetches only specific columns, reducing unnecessary data.

---

## 9️⃣ What is the difference between WHERE and HAVING?
**Answer:**

WHERE filters rows before grouping.

HAVING filters groups after the GROUP BY clause has been applied.

---

## 🔟 How do you get the top 5 highest-paid employees?**
Answer:**
```sql
SELECT name, salary 
FROM employees 
ORDER BY salary DESC 
LIMIT 5;
```

---

## 1️⃣1️⃣ How do you calculate the average salary per department?
**Answer:**

``` sql
SELECT department, AVG(salary) 
FROM employees 
GROUP BY department;
```

---

## 1️⃣2️⃣ Can you query tables from multiple databases in one SQL statement?
**Answer:**
Yes, if the DBMS supports it and if you fully qualify the table names using database_name.table_name.

Example:
```sql
SELECT * FROM database1.employees e 
JOIN database2.departments d ON e.department_id = d.id;
```

---

1️⃣3️⃣ What is the use of LIMIT clause in SQL?
Answer:
The LIMIT clause restricts the number of records returned in a query result. It’s useful for pagination or fetching top-N results.

---

1️⃣4️⃣ What is the output of SELECT * FROM employees?
Answer:
It retrieves all columns and all rows from the employees table.

---

1️⃣5️⃣ Can we use ORDER BY and LIMIT together?
Answer:
Yes. ORDER BY sorts the data, and LIMIT restricts the number of sorted results.

Example:
```sql
SELECT name FROM employees ORDER BY age DESC LIMIT 3;
```
