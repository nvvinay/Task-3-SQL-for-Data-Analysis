# 🗄️ Task 3 – SQL for Data Analysis

## 📌 Objective
To use SQL queries to extract and analyze structured data from a database using SQLite.

---

## 🛠 Tools Used
- SQLite  
- Python (sqlite3 module)  
- VS Code  

---

## 📂 Project Structure

Task-3-SQL/
│
├── ecommerce_queries.sql # All SQL queries
├── run_sqlite.py # Python script to execute SQL
├── ecommerce.db # SQLite database file
└── screenshots/ # Output screenshots

---

## 🧱 Database Design

### Tables Created
- customers  
- products  
- orders  

### Relationships
- orders.customer_id → references customers.customer_id  
- orders.product_id → references products.product_id  

---

## 🧾 SQL Concepts Implemented
✔ SELECT  
✔ WHERE  
✔ ORDER BY  
✔ GROUP BY  
✔ Aggregate Functions (SUM)  
✔ INNER JOIN  
✔ Subquery  
✔ CREATE VIEW  
✔ CREATE INDEX  

---

## 🔍 Queries Performed

1️⃣ SELECT with WHERE
```sql
SELECT * FROM customers
WHERE country = 'India';

2️⃣ ORDER BY
SELECT * FROM products
ORDER BY price DESC;

3️⃣ GROUP BY with SUM
SELECT customer_id, SUM(total_amount) AS total_spent
FROM orders
GROUP BY customer_id;

4️⃣ INNER JOIN
SELECT c.customer_name, o.total_amount
FROM customers c
INNER JOIN orders o
ON c.customer_id = o.customer_id;

5️⃣ Subquery
SELECT customer_name
FROM customers
WHERE customer_id IN (
    SELECT customer_id
    FROM orders
    GROUP BY customer_id
    HAVING SUM(total_amount) > 30000
);

6️⃣ View Creation
CREATE VIEW high_value_customers AS
SELECT customer_id, SUM(total_amount) AS total_spent
FROM orders
GROUP BY customer_id
HAVING total_spent > 30000;

7️⃣ Index Creation
CREATE INDEX idx_customer_id
ON orders(customer_id);

📊 Output
Screenshots of executed queries and results

🎯 Outcome
Successfully created a relational database using SQLite
Executed multiple SQL queries for data analysis
Demonstrated understanding of joins, aggregation, subqueries, views, and indexing

👨‍💻 Author

Jayanth B