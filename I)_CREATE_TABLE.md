---

# 📘 SQL Notes: `CREATE TABLE` Statement

> **Updated on:** 14 Apr, 2025
> **Author:** Rohar (Software Test Engineer)

---

## 🧠 What is `CREATE TABLE` in SQL?

`CREATE TABLE` SQL command se hum database me naye table banate hain. Isme table ka structure define karte hain jaise:

* Column names
* Data types
* Constraints (e.g., `PRIMARY KEY`, `NOT NULL`, `CHECK`, etc.)

Ye statement har ek SQL developer/tester ke liye basic aur must-know hai.

---

## 🧾 Syntax

```sql
CREATE TABLE table_name (
    column1 datatype(size),
    column2 datatype(size),
    ...
    columnN datatype(size)
);
```

### 🔑 Key Terms

| Term                   | Description              |
| ---------------------- | ------------------------ |
| `table_name`           | Naye table ka naam       |
| `column1, column2,...` | Table ke columns ke naam |
| `datatype(size)`       | Data type aur uska size  |

---

## ✅ Real-World Example

### Create Customer Table:

```sql
CREATE TABLE Customer(
    CustomerID INT PRIMARY KEY,
    CustomerName VARCHAR(50),
    LastName VARCHAR(50),
    Country VARCHAR(50),
    Age INT CHECK (Age >= 0 AND Age <= 99),
    Phone VARCHAR(15)
);
```

### 📌 Explanation:

* `CustomerID`: Primary key banaya (unique record ke liye)
* `VARCHAR`: Text type field ke liye use kiya gaya (CustomerName, Country, etc.)
* `CHECK`: Age range 0 se 99 ke beech hona chahiye
* `Phone`: VARCHAR use kiya gaya, taaki formatting aur leading zeros bhi aa sake

---

## 📥 Inserting Data

```sql
INSERT INTO Customer (CustomerID, CustomerName, LastName, Country, Age, Phone)
VALUES
(1, 'Shubham', 'Thakur', 'India', 23, '9876543210'),
(2, 'Aman', 'Chopra', 'Australia', 21, '8888888888'),
(3, 'Naveen', 'Tulasi', 'Sri Lanka', 24, '9999999999'),
(4, 'Aditya', 'Arpan', 'Austria', 21, '7777777777'),
(5, 'Nishant', 'Jain', 'Spain', 22, '6666666666');
```

📌 Tip: Zyada data ho to bulk insert ya CSV import ka use karo performance ke liye.

---

## 🔄 Creating Table From Existing Table

```sql
CREATE TABLE SubTable AS
SELECT CustomerID, CustomerName
FROM Customer;
```

### 🔁 Real Life Use-case:

* Agar tumhe backup table banana hai
* Ya kisi analysis ke liye sirf kuch columns ka table chahiye

📌 Note: Pura table copy karne ke liye `SELECT *` bhi use kar sakte ho.

---

## 🔍 Bonus Points You Should Remember

### 1️⃣ Constraints

```sql
Age INT NOT NULL
```

* NOT NULL, UNIQUE, DEFAULT jaise rules `CREATE TABLE` ke time define kar sakte ho.

### 2️⃣ Prevent Errors with `IF NOT EXISTS`

```sql
CREATE TABLE IF NOT EXISTS Customer (...);
```

* Ye ensure karta hai ki agar table already exist karta hai, toh error na aaye.

### 3️⃣ View Table Structure

```sql
DESC Customer;
```

* Ye command se aap table ke column names, types aur constraints dekh sakte ho.

### 4️⃣ Modify Table

```sql
ALTER TABLE Customer ADD Email VARCHAR(100);
```

* `ALTER TABLE` se column add/update/delete kar sakte ho after creation.

---

## 🏁 Conclusion

SQL ka `CREATE TABLE` command foundation hai har database design ka. Chahe tum Customer table create kar rahe ho ya Employee table, correct data types aur constraints use karna important hai for:

* ✅ Data accuracy
* ✅ Easy data access
* ✅ Table integrity

Practice karo aur confidently tables create karo real-world projects ke liye. ✅

---

## 🧰 Related Commands Cheat Sheet

| Purpose          | SQL Command              |
| ---------------- | ------------------------ |
| Table create     | `CREATE TABLE`           |
| Data insert      | `INSERT INTO`            |
| View structure   | `DESC table_name;`       |
| Modify structure | `ALTER TABLE`            |
| Create copy      | `CREATE TABLE AS SELECT` |

---

**Made with ❤️ by Rohar**
