# 🧾 Temporary Tables in SQL

## ❓ What Are Temporary Tables in SQL?
- 🧊 Temporary tables are special tables created to hold intermediate data during query execution or session operations.
- Stored in a system’s temporary database like TempDB (in SQL Server).
- Automatically deleted when the session or procedure ends.
- Ideal for:
  - 🧪 Intermediate calculations
  - 🧹 Data transformations
  - 🧷 Backup/testing without affecting permanent tables

### 🔧 Syntax Examples
### 📌 Create a Temporary Table:
```sql
CREATE TABLE #EmpDetails (
  id INT,
  name VARCHAR(25)
);
```

---

### ➕ Insert Values:
```sql
INSERT INTO #EmpDetails 
VALUES (01, 'Lalit'), (02, 'Atharva');
```

---

### 🔍 Select from the Temp Table: 
```sql
SELECT * FROM #EmpDetails;
```

🧾 Output:
| id | name    |
| -- | ------- |
| 1  | Lalit   |
| 2  | Atharva |

---

### 🧬 Types of Temporary Tables
| Type                   | Symbol | Scope                | Lifetime                            | Accessibility        |
| ---------------------- | ------ | -------------------- | ----------------------------------- | -------------------- |
| Local Temporary Table  | `#`    | Only current session | Dropped when session ends           | Only creator session |
| Global Temporary Table | `##`   | All sessions         | Dropped when last connection closes | Accessible to all    |

---

### 🔹 Local Temporary Table
- Uses `#` prefix (e.g., #EmpDetails)
- Dropped automatically after the session ends or stored procedure finishes.

🧪 Example:
```sql
CREATE PROCEDURE ProcTemp 
AS
BEGIN
  CREATE TABLE #EmpDetails (id INT, name VARCHAR(25));
  INSERT INTO #EmpDetails VALUES (01, 'Lalit'), (02, 'Atharva');
  SELECT * FROM #EmpDetails;
END;

EXECUTE ProcTemp;
```

--- 

## 🔸 Global Temporary Table
- Uses ## prefix (e.g., ##EmpDetails)
- Shared across all sessions.
- Dropped only after the last session using it closes.
- Must have a unique name (no suffix like local temp tables).

🧪 Example:
```sql
CREATE TABLE ##EmpDetails (id INT, name VARCHAR(25));
INSERT INTO ##EmpDetails VALUES (1, 'Lalit'), (2, 'Atharva');
SELECT * FROM ##EmpDetails;
```

---

🆚 Local vs. Global Temp Tables
| Feature          | Local Temp Table (`#`)           | Global Temp Table (`##`)        |
| ---------------- | -------------------------------- | ------------------------------- |
| 🔢 Prefix        | `#`                              | `##`                            |
| 🌐 Scope         | Current session only             | All sessions                    |
| ⏳ Lifetime       | Ends when session/procedure ends | Ends when last user disconnects |
| 🔒 Accessibility | Only the creating session        | All sessions can access         |
| ⚙️ Use Case      | Session-specific tasks           | Multi-session shared operations |

---

## 🧠 Conclusion
✅ Temporary tables are ideal for:
- Performing complex data manipulations
- Handling intermediate results
- Running isolated test cases
- Supporting stored procedures and batch operations

🔍 Choose between Local and Global depending on your need for scope and session access.
