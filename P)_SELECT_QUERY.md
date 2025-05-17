# SQL SELECT Query – Interview Notes

## 🔍 What is SQL SELECT?

* Used to **fetch data** from a database.
* Can retrieve **all rows** or based on **specific conditions**.
* Results are stored in a **result table**.

### 📌 Syntax

```sql
SELECT column1, column2, ...
FROM table_name;
```

---

## 🧪 Examples

### 1️⃣ Select Specific Columns

```sql
SELECT CustomerName, LastName
FROM Customer;
```

### 2️⃣ Select All Columns

```sql
SELECT * FROM Customer;
```

### 3️⃣ SELECT with WHERE (Row-level Filtering)

```sql
SELECT CustomerName
FROM Customer
WHERE Age = '21';
```

### 4️⃣ SELECT with GROUP BY (Grouping Data)

```sql
SELECT Customer_id, COUNT(*) AS order_count
FROM Orders
GROUP BY Customer_id;
```

### 5️⃣ SELECT with HAVING (Group-level Filtering)

```sql
SELECT Department, SUM(Salary) AS Salary
FROM employee
GROUP BY Department
HAVING SUM(Salary) >= 50000;
```

### 6️⃣ SELECT with ORDER BY (Sorting Data)

```sql
SELECT *
FROM Customer
ORDER BY Age DESC;
```

---

## 💡 Tips to Master SELECT

| Goal              | Query                                                         |
| ----------------- | ------------------------------------------------------------- |
| Get unique values | `SELECT DISTINCT column FROM table;`                          |
| Limit result rows | `SELECT * FROM table LIMIT 10;`                               |
| Use aliases       | `SELECT CustomerName AS Name FROM Customer;`                  |
| Join tables       | `SELECT a.*, b.* FROM TableA a JOIN TableB b ON a.id = b.id;` |

---

## ✅ Conclusion

* `SELECT` is the **backbone** of SQL queries.
* Combine with `WHERE`, `GROUP BY`, `HAVING`, `ORDER BY` for **powerful data analysis**.
* Practice with real tables and data for **mastery**.

> "WHERE for filtering rows, HAVING for filtering groups."

---

📝 *Prepared for interview revision – Keep it crisp, clear, and confident!*
