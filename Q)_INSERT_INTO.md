# SQL SELECT & INSERT INTO – Interview Notes

---

## 🔍 What is SQL SELECT?

Used to **fetch data** from a database.

### 📌 Syntax

```sql
SELECT column1, column2, ... 
FROM table_name;
```

---

## 🧪 SELECT Examples

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

## 💡 SELECT Tips

| Goal              | Query                                                         |
| ----------------- | ------------------------------------------------------------- |
| Get unique values | `SELECT DISTINCT column FROM table;`                          |
| Limit rows        | `SELECT * FROM table LIMIT 10;`                               |
| Use aliases       | `SELECT CustomerName AS Name FROM Customer;`                  |
| Join tables       | `SELECT a.*, b.* FROM TableA a JOIN TableB b ON a.id = b.id;` |

---

## 📥 What is SQL INSERT INTO?

Used to **add new data (rows)** into a table.

---

## 🔢 INSERT INTO Methods

### 1️⃣ Insert All Columns (Simple)

```sql
INSERT INTO table_name 
VALUES (value1, value2, ...);
```

**Note:** Values must match column order exactly.

**Example:**

```sql
INSERT INTO Student 
VALUES (5, 'HARSH', 'WEST BENGAL', 'XXXXXXXXXX', 19);
```

### 2️⃣ Insert Specific Columns (Flexible)

```sql
INSERT INTO table_name (col1, col2, ...) 
VALUES (val1, val2, ...);
```

**Example:**

```sql
INSERT INTO Student (ROLL_NO, NAME, AGE) 
VALUES (5, 'PRATIK', 19);
```

Unspecified columns = default or NULL.

### 3️⃣ Insert Multiple Rows

```sql
INSERT INTO table_name (col1, col2, ...) 
VALUES 
(val1, val2, ...),
(val1, val2, ...);
```

**Example:**

```sql
INSERT INTO Student (ROLL_NO, NAME, AGE, ADDRESS, PHONE) 
VALUES
(6, 'Amit Kumar', 15, 'Delhi', 'XXXXXXXXXX'),
(7, 'Gauri Rao', 18, 'Bangalore', 'XXXXXXXXXX');
```

### 4️⃣ Insert from Another Table

**a) Insert All Columns**

```sql
INSERT INTO target_table 
SELECT * FROM source_table;
```

**b) Insert Specific Columns**

```sql
INSERT INTO target_table (col1, col2) 
SELECT col1, col2 
FROM source_table;
```

**c) Insert with Condition**

```sql
INSERT INTO target_table 
SELECT * FROM source_table 
WHERE Age > 20;
```

---

## 🧠 INSERT INTO Tips

* Insert multiple rows for better performance.
* Omitted columns = default/NULL.
* Column order matters when not explicitly specified.
* Use `INSERT INTO SELECT` for data migration.

---

## ✅ Conclusion

* `SELECT` = for **reading** data.
* `INSERT INTO` = for **adding** data.
* Both are core commands for SQL CRUD operations.
* Practice and understand variations for real-world scenarios.

> SQL Tip: "If you SELECT well, you'll INSERT right!"

📝 *Prepared for interview revision – Keep it crisp, clear, and confident!*
