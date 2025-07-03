# **Comprehensive SQL Guide**

## **Table of Contents**
1. [Introduction to SQL](#introduction-to-sql)
2. [SQL Basics](#sql-basics)
3. [Querying Data](#querying-data)
4. [Filtering and Sorting](#filtering-and-sorting)
5. [Joins](#joins)
6. [Aggregation and Grouping](#aggregation-and-grouping)
7. [Subqueries](#subqueries)
8. [Modifying Data](#modifying-data)
9. [Database Objects](#database-objects)
10. [Advanced SQL](#advanced-sql)
11. [Performance Optimization](#performance-optimization)
12. [SQL Best Practices](#sql-best-practices)

---

## **1. Introduction to SQL**
**SQL (Structured Query Language)** is the standard language for managing and manipulating relational databases.

### **Key Concepts**
- **Relational Databases**: Store data in tables with rows and columns
- **DBMS**: Database Management Systems (MySQL, PostgreSQL, SQL Server, Oracle)
- **CRUD Operations**: Create, Read, Update, Delete data

---

## **2. SQL Basics**

### **Data Types**
| Type | Examples |
|------|----------|
| Numeric | `INT`, `FLOAT`, `DECIMAL` |
| String | `VARCHAR`, `CHAR`, `TEXT` |
| Date/Time | `DATE`, `TIME`, `DATETIME` |
| Boolean | `BOOLEAN`, `BIT` |

### **Basic Commands**
```sql
-- Create database
CREATE DATABASE mydb;

-- Create table
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    email VARCHAR(100) UNIQUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Insert data
INSERT INTO users (id, name, email) 
VALUES (1, 'John Doe', 'john@example.com');
```

---

## **3. Querying Data**

### **SELECT Statement**
```sql
-- Basic select
SELECT * FROM users;

-- Select specific columns
SELECT name, email FROM users;

-- Limit results
SELECT * FROM users LIMIT 10;
```

### **Expressions**
```sql
-- Calculations
SELECT product, price, price * 0.9 AS discounted_price 
FROM products;

-- String concatenation
SELECT CONCAT(first_name, ' ', last_name) AS full_name 
FROM employees;
```

---

## **4. Filtering and Sorting**

### **WHERE Clause**
```sql
-- Basic filtering
SELECT * FROM products WHERE price > 100;

-- Multiple conditions
SELECT * FROM orders 
WHERE status = 'shipped' AND order_date > '2023-01-01';

-- IN operator
SELECT * FROM customers 
WHERE country IN ('USA', 'Canada', 'UK');

-- LIKE for pattern matching
SELECT * FROM products 
WHERE name LIKE '%Phone%';
```

### **ORDER BY**
```sql
-- Sort ascending (default)
SELECT * FROM products ORDER BY price;

-- Sort descending
SELECT * FROM customers ORDER BY last_name DESC;

-- Multiple sort criteria
SELECT * FROM orders 
ORDER BY order_date DESC, total_amount ASC;
```

---

## **5. Joins**

### **Join Types**
| Join Type | Description |
|-----------|-------------|
| `INNER JOIN` | Returns matching rows |
| `LEFT JOIN` | All rows from left table + matches |
| `RIGHT JOIN` | All rows from right table + matches |
| `FULL JOIN` | All rows when there's a match in either |
| `CROSS JOIN` | Cartesian product |

### **Examples**
```sql
-- Inner join
SELECT o.order_id, c.customer_name
FROM orders o
INNER JOIN customers c ON o.customer_id = c.customer_id;

-- Left join
SELECT p.product_name, o.order_date
FROM products p
LEFT JOIN order_items oi ON p.product_id = oi.product_id
LEFT JOIN orders o ON oi.order_id = o.order_id;
```

---

## **6. Aggregation and Grouping**

### **Aggregate Functions**
```sql
-- Basic aggregates
SELECT 
    COUNT(*) AS total_orders,
    SUM(amount) AS total_sales,
    AVG(amount) AS avg_order,
    MIN(order_date) AS first_order,
    MAX(order_date) AS last_order
FROM orders;

-- GROUP BY
SELECT 
    customer_id, 
    COUNT(*) AS order_count,
    SUM(amount) AS total_spent
FROM orders
GROUP BY customer_id
HAVING COUNT(*) > 5;  -- Filter groups
```

---

## **7. Subqueries**

### **Types of Subqueries**
```sql
-- In WHERE clause
SELECT * FROM products
WHERE price > (SELECT AVG(price) FROM products);

-- In FROM clause
SELECT avg_prices.category
FROM (
    SELECT category, AVG(price) AS avg_price
    FROM products
    GROUP BY category
) AS avg_prices
WHERE avg_price > 100;

-- Correlated subquery
SELECT e.first_name, e.last_name
FROM employees e
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
    WHERE department_id = e.department_id
);
```

---

## **8. Modifying Data**

### **INSERT, UPDATE, DELETE**
```sql
-- Insert multiple rows
INSERT INTO products (id, name, price)
VALUES 
    (1, 'Laptop', 999.99),
    (2, 'Phone', 699.99);

-- Update records
UPDATE customers
SET email = 'new@email.com', status = 'active'
WHERE customer_id = 123;

-- Delete records
DELETE FROM orders
WHERE order_date < '2020-01-01';
```

### **Transactions**
```sql
BEGIN TRANSACTION;

UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

-- If everything is OK
COMMIT;

-- If something went wrong
ROLLBACK;
```

---

## **9. Database Objects**

### **Views**
```sql
CREATE VIEW active_customers AS
SELECT * FROM customers
WHERE status = 'active';

SELECT * FROM active_customers;
```

### **Indexes**
```sql
-- Create index
CREATE INDEX idx_customer_email ON customers(email);

-- Composite index
CREATE INDEX idx_order_customer_date ON orders(customer_id, order_date);
```

---

## **10. Advanced SQL**

### **Window Functions**
```sql
-- Rank products by price
SELECT 
    product_name,
    price,
    RANK() OVER (ORDER BY price DESC) AS price_rank
FROM products;

-- Running total
SELECT 
    order_date,
    amount,
    SUM(amount) OVER (ORDER BY order_date) AS running_total
FROM orders;
```

### **Common Table Expressions (CTEs)**
```sql
WITH regional_sales AS (
    SELECT region, SUM(amount) AS total_sales
    FROM orders
    GROUP BY region
)
SELECT region, total_sales
FROM regional_sales
WHERE total_sales > 100000;
```

---

## **11. Performance Optimization**

### **Query Optimization Tips**
- Use `EXPLAIN` to analyze query plans
- Add appropriate indexes
- Avoid `SELECT *` - specify columns needed
- Use `LIMIT` for testing queries
- Normalize database structure

### **Indexing Strategies**
- Index columns used in `WHERE`, `JOIN`, and `ORDER BY`
- Consider composite indexes for multi-column queries
- Avoid over-indexing (slows down inserts/updates)

---

## **12. SQL Best Practices**

### **Coding Standards**
- Use consistent indentation
- Capitalize SQL keywords
- Use descriptive table/column names
- Comment complex queries

### **Security**
- Use parameterized queries to prevent SQL injection
- Limit user permissions (principle of least privilege)
- Encrypt sensitive data

### **Maintenance**
- Regularly back up databases
- Monitor and optimize query performance
- Document database schema

---

## **Conclusion**
SQL is a powerful language for working with relational databases. Mastering these concepts will enable you to:
- Efficiently query and analyze data
- Design optimized database structures
- Build robust data-driven applications

**Next Steps:**
- Practice with real-world datasets
- Learn database-specific features (e.g., PostgreSQL JSON support)
- Explore ORMs for application development

**Resources:**
- [SQLZoo](https://sqlzoo.net/) - Interactive SQL exercises
- [Mode Analytics SQL Tutorial](https://mode.com/sql-tutorial/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
