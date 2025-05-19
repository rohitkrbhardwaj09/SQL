# SQL Practice

### Products Table 
The Products table contains details about products, including their names, categories, and unit prices. It provides reference data for linking product information to sales transactions.
```sql
 create table products(
    -> product_id int primary key,
    -> product_name varchar(100),
    -> category varchar(50),
    -> unit_price decimal(10, 2)
    -> );
```

#### Inserting data to `products` table
```sql
 insert into sales (sale_id, product_id, quantity_sold, sale_date, total_price) values
    -> (1, 101, 5, '2024-01-01', 2500.00),
    -> (2, 102, 3, '2024-01-02', 900.00),
    -> (3, 103, 2, '2024-01-02', 60.00),
    -> (4, 104, 4, '2024-01-03', 80.00),
    -> (5, 105, 6, '2024-01-03', 90.00);
```

**Output** 
![image](https://github.com/user-attachments/assets/70b7a8d5-0a4e-4cfe-954d-708e976a00c5)


### Sales Table
The Sales table records information about product sales, including the quantity sold, sale date, and total price for each sale. It serves as a transactional data source for analyzing sales trends.

```sql
 create table sales (
    -> sale_id int primary key,
    -> product_id int,
    -> quantity_sold int, sale_date date,
    -> total_price decimal(10, 2),
    -> foreign key (product_id) references products(product_id));
```

#### Inserting data to `sales` table
```sql
 insert into sales (sale_id, product_id, quantity_sold, sale_date, total_price) values
    -> (1, 101, 5, '2024-01-01', 2500.00),
    -> (2, 102, 3, '2024-01-02', 900.00),
    -> (3, 103, 2, '2024-01-02', 60.00),
    -> (4, 104, 4, '2024-01-03', 80.00),
    -> (5, 105, 6, '2024-01-03', 90.00);
```

**Output**
![image](https://github.com/user-attachments/assets/dead8fea-184e-4198-a641-785bec13e998)

---
# SQL PRACTICE EXERCISE FOR BEGINNERS
---

## Retrive all columns fro the sales table

**Query:**
```sql
select * from sales;
```

**Output**
![image](https://github.com/user-attachments/assets/6029f93c-8ec1-48b8-b398-272219da1085)


---

## Retrive the `product_name` and `unit_price` from the products table
```sql
select product_name, unit_price from products;
```
**Output:**
![image](https://github.com/user-attachments/assets/7ad8d1c0-4ea6-4ad2-944e-4b66422c993d)

---

## Retrive the sale_id and sale_date from the Sales table
```sql
select sale_id, sale_date from sales;
```
**Output:**
![image](https://github.com/user-attachments/assets/d6a8600c-355c-448d-8f2c-bb54801b7c3f)

---

## Filter the Sales table to show only sales with a total_price greater than $100
```sql
select * from sales where total_price > 100.00;
```
**Output:**
![image](https://github.com/user-attachments/assets/e50bfb11-27c8-49f1-8dd5-f9ac3023bc32)

---

## Filter the Products table to show only products in the 'Electronics' category
```sql
select * from products where category = 'Electronics';
```
**Output:**
![image](https://github.com/user-attachments/assets/9e49f879-ecb3-4e46-99fa-2dc8049c6f06)

---

## Retrive the sale_id and total_price from the Sales table for sales made on January 2, 2024.
```sql
select sale_id, total_price from sales where sale_date = '2024-01-03';
```
**Output:**
![image](https://github.com/user-attachments/assets/d0d2ea99-06d0-445c-a1a5-01a83dc30054)
