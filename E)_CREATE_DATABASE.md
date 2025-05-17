
# 📘 SQL CREATE DATABASE – Interview Notes

## ✅ What is `CREATE DATABASE` in SQL?
`CREATE DATABASE` is a **Data Definition Language (DDL)** command used to create a **new database** in SQL-based DBMS (like MySQL, PostgreSQL, SQL Server). It's the **first step** in organizing data before creating tables and inserting records.

---

## 🧠 Syntax:
```sql
CREATE DATABASE database_name;
```
- `database_name`: Unique name of the new database.
- Avoid spaces; use underscores `_` if needed.

---

## 🚀 Example – Create a Database:
```sql
CREATE DATABASE GeeksForGeeks;
```
✅ This creates an **empty database** named `GeeksForGeeks`.

---

## 📌 Real-Time Use Case:
For an online book management app, we can create:
```sql
CREATE DATABASE BookLibrary;
```

---

## 🔍 How to Verify Creation?
Use the `SHOW DATABASES` command:
```sql
SHOW DATABASES;
```
Check if `GeeksForGeeks` appears in the result.

---

## 🔄 Switch to the Database:
Use the `USE` command to begin working inside the newly created DB:
```sql
USE GeeksForGeeks;
```

---

## ⚠️ Delete a Database:
To delete the database **permanently**:
```sql
DROP DATABASE GeeksForGeeks;
```
🔴 **Irreversible!** Deletes all data in that DB.

---

## 🌐 Compatibility (MySQL, PostgreSQL, SQL Server)
- **MySQL**: Supports charset and collation
```sql
CREATE DATABASE GeeksForGeeks CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
- **PostgreSQL**: Supports `OWNER` and `TEMPLATE` options.
- **SQL Server**: Allows file size and location specification.

---

## ⚠️ Common Errors
### 1. Database Already Exists:
```sql
CREATE DATABASE IF NOT EXISTS GeeksForGeeks;
```
✔ Prevents duplication.

### 2. Insufficient Privileges:
🔒 Ensure you have **admin-level permissions** to execute `CREATE DATABASE`.

---

## 💡 Best Practices
- ✅ Use unique, meaningful names (e.g., `employee_records`)
- ✅ Use underscores `_` instead of spaces.
- ✅ Maintain consistent naming convention (e.g., all lowercase)
- ✅ Check max name length (usually 128 characters)
- ✅ Ensure correct privileges

---

## 🧾 Interview Perspective Summary
| Key Point                      | Explanation                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| What it does                  | Creates a new database schema                                               |
| Syntax                        | `CREATE DATABASE db_name;`                                                 |
| Common command to verify      | `SHOW DATABASES;`                                                          |
| How to switch DB              | `USE db_name;`                                                             |
| Safe creation                 | `CREATE DATABASE IF NOT EXISTS db_name;`                                   |
| When to use DROP              | To delete entire database permanently                                      |
| Real-life use case            | Organize tables for BookStore, HRSystem, Inventory                         |
| Important DBMS differences    | MySQL: charset/collation, PostgreSQL: owner/template, SQL Server: files    |
| Errors to avoid               | Duplicates and missing privileges                                          |

---

## 🏁 Conclusion
The `CREATE DATABASE` command is a **foundational step** in SQL. Whether building small apps or enterprise systems, understanding this command is critical for proper **database architecture** and **data management**.
