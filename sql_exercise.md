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


---

## Retrive the `product_name` and `unit_price` from the products table
```sql
select product_name, unit_price from products;
```

