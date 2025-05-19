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

## 1) Retrive all columns fro the sales table

**Query:**
```sql
select * from sales;
```

**Output**
![image](https://github.com/user-attachments/assets/6029f93c-8ec1-48b8-b398-272219da1085)


---

## 2) Retrive the `product_name` and `unit_price` from the products table
```sql
select product_name, unit_price from products;
```
**Output:**
![image](https://github.com/user-attachments/assets/7ad8d1c0-4ea6-4ad2-944e-4b66422c993d)

---

## 3) Retrive the sale_id and sale_date from the Sales table
```sql
select sale_id, sale_date from sales;
```
**Output:**
![image](https://github.com/user-attachments/assets/d6a8600c-355c-448d-8f2c-bb54801b7c3f)

---

## 4) Filter the Sales table to show only sales with a total_price greater than $100
```sql
select * from sales where total_price > 100.00;
```
**Output:**
![image](https://github.com/user-attachments/assets/e50bfb11-27c8-49f1-8dd5-f9ac3023bc32)

---

## 5) Filter the Products table to show only products in the 'Electronics' category
```sql
select * from products where category = 'Electronics';
```
**Output:**
![image](https://github.com/user-attachments/assets/9e49f879-ecb3-4e46-99fa-2dc8049c6f06)

---

## 6) Retrive the sale_id and total_price from the Sales table for sales made on January 2, 2024.
```sql
select sale_id, total_price from sales where sale_date = '2024-01-03';
```
**Output:**
![image](https://github.com/user-attachments/assets/d0d2ea99-06d0-445c-a1a5-01a83dc30054)

---

## 7) Calculate the total revenue generated from all sales in the Sales table
```sql
select SUM(total_price) as total_revenue from sales;
```
**Output:** <br/>
![image](https://github.com/user-attachments/assets/c8871f8c-4541-411c-a41a-7a9d9d005597)

---

## 8) Calculate the average unit_price of products in the Products table
```sql
select avg(unit_price) as average_price from products;
```
**Output:** <br/>
![image](https://github.com/user-attachments/assets/b053cd4a-0ba5-4a72-bc70-623167cc518a)


---

## 9) Calculate the total quantity_sold from the sales table
```sql
select sum(quantity_sold) as total_sold from sales;
```
**Output: ** <br/>

![image](https://github.com/user-attachments/assets/8bd0696c-44b1-46b2-8de9-699869771c81)

---

## 10) Count Sales per day from the Sales table
```sql
select sale_date, count(*) as sales_count from sales
    -> Group by sale_date
    -> Order by sale_date;
```
**Output: ** <br/>
![image](https://github.com/user-attachments/assets/725d2a11-6e9a-4f27-b199-7a965acf90c2)


---

## 11) Retrive product_name and unit_price from the Products table with the highest unit price
Way-1 (Handles Ties)
```sql
select product_name, unit_price from products
    -> where unit_price = (select max(unit_price) from products);
```

**Output: ** <br/>
![image](https://github.com/user-attachments/assets/8aebbf3e-171c-4614-9756-e08c0136f079)


Way-2 (Doesn't handle ties)
```sql
select product_name, unit_price from products
    -> order by unit_price desc
    -> limit 1;
```
**Output: ** <br/>
![image](https://github.com/user-attachments/assets/1f85ae0d-985f-4583-803e-2bd15b646b4d)

---

## 12) Retrive the sale_id, product_id, and total_price from the Sales table for saes with a quantity_sold greater than 4
```sql
select sale_id, product_id, total_price from sales
    -> where quantity_sold > 4;
```
**Output: ** <br/>
![image](https://github.com/user-attachments/assets/4bf41fdb-6bf7-46dc-afaf-3c3a0a839435)


---

## 13) Retrive the product_name and unit_price from the Products table, ordering the results by unit_price in descending_order.
```sql
select product_name, unit_price from products
    -> order by unit_price desc;
```
**Output: ** <br/>
![image](https://github.com/user-attachments/assets/a61199b6-72e5-41ae-b70c-1debf17392ef)

---

## 14) Retrive the total_price of all sales, rounding the values to two decimal places
```sql
 select round(sum(total_price), 2) as total_sales from sales;
```
**Output: ** <br/>
![image](https://github.com/user-attachments/assets/3f80afc5-6396-4594-849b-fbd34aad1174)

---

## 15) Calculate the average total_price of sales in the sales table
```sql
 select avg(total_price) as average_price from sales;
```
**Output:** <br/>
![image](https://github.com/user-attachments/assets/62ba6b73-6fa7-4ae3-b76e-c8f286a79d78)

---

## 16) Retrive the sale_id and sale_date from the Sales table, formatting the sale_date as 'YYYY-MM-DD'.
```sql
 select sale_id, date_format(sale_date, '%Y-%m-%d') as formatted_date from sales;
```
**Output:** <br/>
![image](https://github.com/user-attachments/assets/33b94975-1952-4069-9888-33cce66caebf)

---

## 17) Calculate the total revenue generated from sales of products in the `Electronics` category
```sql
select sum(sales.total_price) as total_revenue from sales
    -> JOIN products on sales.product_id = products.product_id
    -> where products.category = 'Electronics';
```
**Output:** <br/>
![image](https://github.com/user-attachments/assets/4723f006-9e0f-4c48-924b-e56e938f3ff3)

---

## 18) Retrive the product_name and unit_price from the `products` table, filtering the unit_price to show only values between $20 and $60
```sql
select product_name, unit_price from products
    -> where unit_price >= 20.00 and unit_price <= 600;
```
**Output:**<br/>
![image](https://github.com/user-attachments/assets/0d8d216a-fcc8-4be8-a509-16ef32ad827f)

---

## 19) Retrive the Product_name and category from the products table, ordering the result by category in ascending order.
```sql
select product_name, category from products order by category ASC;
```
**Output:** <br/>
![image](https://github.com/user-attachments/assets/9753decc-45f6-4ab5-980f-df3bc980dc56)

---
