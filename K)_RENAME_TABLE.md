---

### 📘 SQL RENAME TABLE

**Last Updated:** 13 Jan, 2025

---

Renaming a table is a common operation used to maintain clarity and structure in the database schema. This guide provides a complete overview of the SQL RENAME TABLE command, including its syntax, usage in various database systems, and best practices.

---

## 🔄 What is SQL RENAME TABLE?

The `RENAME TABLE` statement allows you to change the name of an existing table without altering its data, structure, or constraints. This command is useful when:

* Correcting naming mistakes
* Reorganizing schema
* Adapting to new business requirements

**Key Points:**

* All table data and structure remain intact.
* You must manually update any dependent objects (e.g., queries, views).

---

## 🧾 Syntax

```sql
RENAME TABLE old_table_name TO new_table_name;
```

### 🔑 Terms

* `old_table_name`: Current name of the table
* `new_table_name`: New name to assign to the table

---

## 💻 Examples Across Database Systems

### ✅ MySQL

```sql
RENAME TABLE Customers TO Clients;
```

To verify:

```sql
SELECT * FROM Clients;
```

### 🏢 SQL Server

```sql
EXEC sp_rename 'Employees', 'Workers';
```

To verify:

```sql
SELECT * FROM Workers;
```

### 🐘 PostgreSQL

```sql
ALTER TABLE Products RENAME TO Product_Inventory;
```

To verify:

```sql
SELECT * FROM Product_Inventory;
```

---

## ✅ Best Practices

1. **Ensure No Active Transactions**

   * Avoid renaming during ongoing INSERT, UPDATE, DELETE operations to prevent conflicts or data loss.

2. **Update References**

   * Manually revise all references in queries, views, procedures, and foreign keys.

3. **Perform During Off-Peak Hours**

   * Reduce impact of potential table locks.

4. **Test Changes Thoroughly**

   * Run application queries to confirm everything works after renaming.

---

## ⚠️ Limitations & Considerations

1. **Dependent Objects**

   * Manually update references in triggers, views, stored procedures, and foreign key constraints.

2. **Database Locking**

   * The rename operation might lock the table briefly. Schedule during low-traffic times.

3. **Permission Issues**

   * Requires administrative privileges. Check user permissions before executing.

---

## 🏁 Conclusion

Renaming tables in SQL is a powerful but safe operation when performed carefully. Always:

* Choose the correct syntax for your database (MySQL, SQL Server, PostgreSQL, etc.)
* Follow best practices to prevent issues
* Update all dependent objects

Done properly, renaming helps keep your database clean, clear, and well-structured.

---
