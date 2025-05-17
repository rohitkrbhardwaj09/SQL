
# 🧮 SQL Operators – Explained with Easy Examples

SQL Operators allow us to **manipulate and retrieve data** effectively in databases. These operators help in performing **mathematical, logical, comparison**, and other operations, making them crucial for writing efficient queries.

---

## 🎯 Why Use SQL Operators?

✅ **Data Filtering:** Retrieve only relevant records using logical/comparison operators.  
✅ **Data Manipulation:** Perform calculations, assignments, and set-based operations.  
✅ **Optimization:** Help write precise and optimized queries.

---

## 🔢 Types of SQL Operators

| Operator Type         | Purpose                                    |
|-----------------------|--------------------------------------------|
| Arithmetic            | For performing mathematical calculations   |
| Comparison            | For comparing values                       |
| Logical               | For combining conditions                   |
| Bitwise               | For bit-level data manipulation            |
| Compound              | Operation + Assignment in one              |
| Special               | Range, set, existence checks               |

---

## ➕ 1. SQL Arithmetic Operators

| Operator | Description                          |
|----------|--------------------------------------|
| `+`      | Addition                              |
| `-`      | Subtraction                           |
| `*`      | Multiplication                        |
| `/`      | Division                              |
| `%`      | Modulus (remainder)                  |

📌 **Example:** Calculate 5% salary hike

```sql
SELECT emp_salary, emp_salary * 1.05 AS "Revised Salary" FROM employee;
```

🖼️ ![Arithmetic Example](https://dummyimage.com/600x200/000/fff&text=Revised+Salary+Calculation)

---

## 🆚 2. SQL Comparison Operators

| Operator | Meaning             |
|----------|---------------------|
| `=`      | Equal to             |
| `!=` or `<>` | Not equal to     |
| `>`      | Greater than         |
| `<`      | Less than            |
| `>=`     | Greater than or equal to |
| `<=`     | Less than or equal to |

📌 **Example:**

```sql
SELECT * FROM MATHS WHERE MARKS = 50;
```

🖼️ ![Comparison Example](https://dummyimage.com/600x200/222/fff&text=Marks+=+50)

---

## 🔗 3. SQL Logical Operators

| Operator | Description                                  |
|----------|----------------------------------------------|
| `AND`    | True if **both** conditions are true         |
| `OR`     | True if **any** condition is true            |
| `NOT`    | Reverses the result                          |

📌 **Example:**

```sql
SELECT * FROM employee WHERE emp_city = 'Allahabad' AND emp_country = 'India';
```

🖼️ ![Logical Example](https://dummyimage.com/600x200/333/fff&text=City+AND+Country+Filter)

---

## 🧠 4. SQL Bitwise Operators

| Operator | Action                  |
|----------|--------------------------|
| `&`      | Bitwise AND              |
| `|`      | Bitwise OR               |
| `^`      | Bitwise XOR              |
| `~`      | Bitwise NOT              |
| `<<`     | Left Shift               |
| `>>`     | Right Shift              |

🧪 Used for low-level programming or binary flags.

---

## 🧮 5. SQL Compound Operators

These perform an operation **and assignment** at the same time.

| Operator | Description         |
|----------|---------------------|
| `+=`     | Add and assign       |
| `-=`     | Subtract and assign  |
| `*=`     | Multiply and assign  |
| `/=`     | Divide and assign    |
| `%=`     | Modulus and assign   |
| `&=`, `|=`, `^=` | Bitwise compound ops |

---

## 🧰 6. SQL Special Operators

| Operator | Description |
|----------|-------------|
| `ALL`    | Compare with all values of subquery |
| `ANY`    | True if any value from subquery matches |
| `BETWEEN`| Filter values in a range |
| `IN`     | Matches any in a list |
| `EXISTS` | Checks subquery result existence |
| `SOME`   | Like ANY, returns true if one condition matches |
| `UNIQUE` | Ensures row uniqueness |

📌 **Example – BETWEEN:**

```sql
SELECT * FROM employee WHERE emp_id BETWEEN 101 AND 104;
```

🖼️ ![Between Example](https://dummyimage.com/600x200/666/fff&text=ID+Between+101+and+104)

---

## 🧾 Conclusion

✅ **SQL Operators** are vital for writing powerful queries.  
📊 They help you filter, update, compare, and manipulate data.  
💡 Mastering them boosts your SQL skills to the next level.

🚀 Use these operators wisely to write **faster, smarter, and cleaner** SQL queries!


---

### Here's some dummy table data you can use to practice SQL queries and understand how different operators work. I've included a few tables with realistic data:

### 🧾 Table 1: `employee`
```sql
CREATE TABLE employee (
    emp_id INT PRIMARY KEY,
    emp_name VARCHAR(100),
    emp_salary DECIMAL(10, 2),
    emp_city VARCHAR(50),
    emp_country VARCHAR(50),
    emp_dept VARCHAR(50)
);

INSERT INTO employee VALUES 
(101, 'Amit Kumar', 45000, 'Allahabad', 'India', 'HR'),
(102, 'Neha Sharma', 52000, 'Mumbai', 'India', 'IT'),
(103, 'Rajat Singh', 60000, 'Allahabad', 'India', 'Finance'),
(104, 'Sara Thomas', 58000, 'Delhi', 'India', 'IT'),
(105, 'John Carter', 70000, 'New York', 'USA', 'Marketing'),
(106, 'Meera Kapoor', 43000, 'Mumbai', 'India', 'HR'),
(107, 'Ali Rehman', 54000, 'Karachi', 'Pakistan', 'Finance');
```
| emp\_id | emp\_name    | emp\_salary | emp\_city | emp\_country | emp\_dept |
| ------- | ------------ | ----------- | --------- | ------------ | --------- |
| 101     | Amit Kumar   | 45000       | Allahabad | India        | HR        |
| 102     | Neha Sharma  | 52000       | Mumbai    | India        | IT        |
| 103     | Rajat Singh  | 60000       | Allahabad | India        | Finance   |
| 104     | Sara Thomas  | 58000       | Delhi     | India        | IT        |
| 105     | John Carter  | 70000       | New York  | USA          | Marketing |
| 106     | Meera Kapoor | 43000       | Mumbai    | India        | HR        |
| 107     | Ali Rehman   | 54000       | Karachi   | Pakistan     | Finance   |

### 📚 Table 2: `maths`
```sql
CREATE TABLE maths (
    student_id INT PRIMARY KEY,
    student_name VARCHAR(100),
    marks INT
);

INSERT INTO maths VALUES 
(1, 'Rohan', 45),
(2, 'Meena', 50),
(3, 'Kabir', 30),
(4, 'Aarti', 60),
(5, 'Ramesh', 55);
```
| student\_id | student\_name | marks |
| ----------- | ------------- | ----- |
| 1           | Rohan         | 45    |
| 2           | Meena         | 50    |
| 3           | Kabir         | 30    |
| 4           | Aarti         | 60    |
| 5           | Ramesh        | 55    |


### 🛍️ Table 3: `orders`
```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_name VARCHAR(100),
    order_total DECIMAL(10, 2),
    order_status VARCHAR(50),
    order_date DATE
);

INSERT INTO orders VALUES 
(201, 'Rahul Verma', 1200, 'Shipped', '2024-05-01'),
(202, 'Priya Mehta', 3400, 'Delivered', '2024-05-03'),
(203, 'Aman Joshi', 1500, 'Cancelled', '2024-05-07'),
(204, 'Suresh Raina', 999, 'Shipped', '2024-05-08'),
(205, 'Kriti Sen', 2789, 'Processing', '2024-05-10');
```
| order\_id | customer\_name | order\_total | order\_status | order\_date |
| --------- | -------------- | ------------ | ------------- | ----------- |
| 201       | Rahul Verma    | 1200         | Shipped       | 2024-05-01  |
| 202       | Priya Mehta    | 3400         | Delivered     | 2024-05-03  |
| 203       | Aman Joshi     | 1500         | Cancelled     | 2024-05-07  |
| 204       | Suresh Raina   | 999          | Shipped       | 2024-05-08  |
| 205       | Kriti Sen      | 2789         | Processing    | 2024-05-10  |

### 🧪 Table 4: `inventory`
```sql
CREATE TABLE inventory (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100),
    quantity INT,
    price DECIMAL(10, 2),
    category VARCHAR(50)
);

INSERT INTO inventory VALUES 
(301, 'Laptop', 20, 55000, 'Electronics'),
(302, 'Office Chair', 50, 3500, 'Furniture'),
(303, 'Notebook', 200, 50, 'Stationery'),
(304, 'Smartphone', 15, 22000, 'Electronics'),
(305, 'Water Bottle', 80, 150, 'Kitchen');
```
| product\_id | product\_name | quantity | price | category    |
| ----------- | ------------- | -------- | ----- | ----------- |
| 301         | Laptop        | 20       | 55000 | Electronics |
| 302         | Office Chair  | 50       | 3500  | Furniture   |
| 303         | Notebook      | 200      | 50    | Stationery  |
| 304         | Smartphone    | 15       | 22000 | Electronics |
| 305         | Water Bottle  | 80       | 150   | Kitchen     |


