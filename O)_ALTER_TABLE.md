# 📘 SQL ALTER TABLE Statement

The ALTER TABLE statement is used to modify an existing table's structure without losing data.

🔧 Syntax
```sql
ALTER TABLE table_name
[ADD | DROP | MODIFY] column_name datatype;
```

### 📌 Common Clauses 
| Clause          | Description                                            |
| --------------- | ------------------------------------------------------ |
| `ADD`           | Adds a new column                                      |
| `MODIFY`        | Changes datatype or size (some DBs use `ALTER COLUMN`) |
| `DROP`          | Deletes a column                                       |
| `RENAME COLUMN` | Renames an existing column                             |
| `RENAME TO`     | Renames the entire table                               |

## 📘 Examples
### 1. ➕ Add a Column
```sql
ALTER TABLE Students ADD Email varchar(255);
```

### 2. ➖ Drop a Column 
```sql
ALTER TABLE Students DROP COLUMN Email;
```

### 3. 🛠 Modify a Column
```sql
ALTER TABLE Students MODIFY COLUMN salary DECIMAL(10,2);
```

### 4. ✏ Rename a Column
```sql
ALTER TABLE Students RENAME COLUMN old_name TO new_name;
```

### 5. 📝 Rename the Table
```sql
ALTER TABLE Students RENAME TO NewStudents;
```

## 🧪 Use Case: Student Table
### Initial Table:
| ROLL\_NO | NAME  |
| -------- | ----- |
| 1        | Ram   |
| 2        | Abhi  |
| 3        | Rahul |
| 4        | Tanu  |

### 1. Add AGE & COURSE Columns
```sql
ALTER TABLE Student ADD (AGE number(3), COURSE varchar(40));
```

### 2. Modify COURSE Column Size
```sql
ALTER TABLE Student MODIFY COURSE varchar(20);
```

### 3. Drop COURSE Column
``` sql
ALTER TABLE Student DROP COLUMN COURSE;
```

### ✅ Conclusion
The `ALTER TABLE` statement is essential for:

- Structural changes to a table without data loss.
- Adding, modifying, deleting, or renaming columns/tables.
- Maintaining schema flexibility and ensuring data integrity.
