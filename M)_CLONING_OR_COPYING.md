## SQL Cloning or Copying a Table

**Last Updated: 20 Dec, 2024**

Cloning or copying a table in SQL is a common task in database management. Whether for creating backups, testing, or needing a duplicate table structure, it's an essential skill for DBAs and developers.

### 🔍 What is a Copying or Cloning Table in SQL?

SQL Cloning is the operation of making a copy of a table — similar to taking a photocopy. The copy can include:

* Table Structure (columns, data types, constraints)
* Optionally, the Data

A cloned table is independent and used for testing, backups, or analysis without affecting the original.

#### 🧪 Real-Life Example

In a library management system, to test new features without impacting the production table, we can clone the original table and experiment safely.

---

## 🛠️ Methods for Cloning Tables in SQL

There are 3 methods:

1. **Simple Cloning**
2. **Shallow Cloning**
3. **Deep Cloning**

### Step 1: Create the Original Table

```sql
CREATE TABLE STUDENT(
  student_id INT NOT NULL AUTO_INCREMENT,
  name VARCHAR(255) NOT NULL,
  roll_no VARCHAR(255) NOT NULL UNIQUE,
  PRIMARY KEY (student_id)
);

INSERT INTO STUDENT(student_id, name, roll_no) VALUES
(1, 'Ritwik Dalmia', 'S100'),
(2, 'Rohan Singh', 'S200'),
(3, 'Mohan Singh', 'S300');

SELECT * FROM STUDENT;
```

---

## 1️⃣ Simple Cloning

✅ Copies **structure + data**
❌ Does **not** copy constraints (Primary Key, Unique, Auto-Increment)

```sql
CREATE TABLE STUDENT_COPY SELECT * FROM STUDENT;
SELECT * FROM STUDENT_COPY;
```

### ⚠️ Drawback

* Constraints are **not preserved**.
* Duplicates and data integrity issues can occur.

---

## 2️⃣ Shallow Cloning

✅ Copies **structure only** (no data)
✅ Preserves **constraints**

```sql
CREATE TABLE STUDENT_SHALLOW_CLONE LIKE STUDENT;
SELECT * FROM STUDENT_SHALLOW_CLONE;

INSERT INTO STUDENT_SHALLOW_CLONE(name, roll_no) VALUES
('Ritwik Dalmia', 'S100'),
('Rohan Singh', 'S200'),
('Mohan Singh', 'S300');
```

---

## 3️⃣ Deep Cloning

✅ Copies **structure + data + constraints**

```sql
CREATE TABLE STUDENT_DEEP_CLONE LIKE STUDENT;
INSERT INTO STUDENT_DEEP_CLONE SELECT * FROM STUDENT;
SELECT * FROM STUDENT_DEEP_CLONE;

INSERT INTO STUDENT_DEEP_CLONE(name, roll_no) VALUES
('Mohini Roy', 'S400'),
('Surbhi Roy', 'S500');
```

### ✅ Output

The `STUDENT_DEEP_CLONE` table now:

* Has all data from `STUDENT`
* Retains all constraints
* Accepts new valid data using `AUTO_INCREMENT`

---

## 🧾 Conclusion

| Cloning Type    | Structure | Data | Constraints |
| --------------- | --------- | ---- | ----------- |
| Simple Cloning  | ✅         | ✅    | ❌           |
| Shallow Cloning | ✅         | ❌    | ✅           |
| Deep Cloning    | ✅         | ✅    | ✅           |

Choosing the right cloning method depends on your specific use case:

* **Simple**: Quick data copy, no constraints
* **Shallow**: Structure for testing
* **Deep**: Complete replica

> 🧠 Knowing the differences helps in selecting the best approach for your database needs.
