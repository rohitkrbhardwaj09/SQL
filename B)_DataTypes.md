
# 🗂️ SQL Data Types

SQL Data Types are crucial in relational databases. They define what kind of data a column can hold, such as numbers, text, or dates, ensuring efficient and accurate data storage.

---

## 🎯 Why SQL Data Types Matter

- ✅ **Data Integrity** – Prevents invalid data (e.g., text in numeric fields)
- 💾 **Efficient Storage** – Uses only needed space
- ⚡ **Query Performance** – Enables faster indexing and search
- 🔄 **Application Compatibility** – Ensures smooth interaction with software

📌 _Example_: Use `DECIMAL` for financial values instead of `FLOAT` to avoid rounding errors.

---

## 📦 Categories of SQL Data Types

![SQL Data Types Overview](https://i.imgur.com/dqgHOeB.png)

1. Numeric Data Types
2. Character and String Data Types
3. Date and Time Data Types
4. Binary Data Types
5. Boolean Data Types
6. Special Data Types

---

## 1️⃣ Numeric Data Types

### Exact Numeric

| Data Type     | Description                          | Range |
|---------------|--------------------------------------|-------|
| `BIGINT`      | Large integers                        | ±9 quintillion |
| `INT`         | Standard integers                     | ±2 billion |
| `SMALLINT`    | Small integers                        | ±32,767 |
| `TINYINT`     | Very small integers                   | 0–255 |
| `DECIMAL`     | Fixed-point, precise (e.g. ₹, $)      | ±10^38 |
| `NUMERIC`     | Similar to DECIMAL                    | ±10^38 |
| `MONEY`       | Currency format                       | Huge |
| `SMALLMONEY`  | Smaller monetary values               | ±214,748 |

### Approximate Numeric

| Data Type | Description | Range |
|----------|-------------|-------|
| `FLOAT`  | Approximate values (scientific) | ±1.79E+308 |
| `REAL`   | Less precise float              | ±3.40E+38 |

---

## 2️⃣ Character and String Data Types

### Non-Unicode

| Data Type     | Description |
|---------------|-------------|
| `CHAR(n)`     | Fixed-length (max 8000 chars) |
| `VARCHAR(n)`  | Variable-length (max 8000) |
| `VARCHAR(MAX)`| Up to 2^31-1 chars |
| `TEXT`        | Large text, up to ~2 billion chars |

### Unicode

| Data Type     | Description |
|---------------|-------------|
| `NCHAR(n)`    | Fixed-length Unicode (max 4000) |
| `NVARCHAR(n)` | Variable-length Unicode (max 4000) |
| `NVARCHAR(MAX)`| Up to 2^31-1 Unicode chars |

---

## 3️⃣ Date and Time Data Types

| Data Type | Description | Storage |
|-----------|-------------|---------|
| `DATE`    | Stores only date (YYYY-MM-DD) | 3 bytes |
| `TIME`    | Stores only time (HH:MM:SS)   | 3 bytes |
| `DATETIME`| Stores full timestamp         | 8 bytes |

🕓 _Use Case_: Employee joining date, timestamps for transactions

---

## 4️⃣ Binary Data Types

| Data Type     | Description               | Max Length |
|---------------|---------------------------|------------|
| `BINARY`      | Fixed-length binary       | 8000 bytes |
| `VARBINARY`   | Variable-length binary    | 8000 bytes |
| `IMAGE`       | Store binary images/files | 2GB+ |

📷 _Use Case_: Profile pictures, document uploads

---

## 5️⃣ Boolean Data Type

| Data Type | Description |
|-----------|-------------|
| `BOOLEAN` | TRUE or FALSE (logical values) |

✔️ _Use Case_: Active status, payment success flag

---

## 6️⃣ Special Data Types

### XML Data Type

| Data Type | Description |
|-----------|-------------|
| `XML`     | Store and query XML data |

🧾 _Use Case_: Storing configurations, system logs

### Spatial Data Type

| Data Type | Description |
|-----------|-------------|
| `GEOMETRY`| Store spatial data (points, lines, polygons) |

🗺️ _Use Case_: GIS applications, location tracking

---

## ✅ Conclusion

Choosing the **right SQL data type** is essential for:

- Maintaining **data accuracy**
- Ensuring **query performance**
- Reducing **storage cost**
- Improving **application reliability**

🎯 Mastering SQL Data Types will help you build **efficient, scalable, and reliable** databases.

---

> 🧠 Tip: Always think about the **real-world meaning** of your data before selecting its type.
