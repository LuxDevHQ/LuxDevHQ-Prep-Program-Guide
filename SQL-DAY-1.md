## 1. Introduction to SQL & Databases

#### What is SQL?

* SQL = **Structured Query Language**
* Used to **store**, **retrieve**, **update**, and **delete** data in databases.

#### Why Use Databases?

* Store employee/customer records
* Manage inventory and transactions
* Support data analysis and reporting

---

### 2. Schema & Database Concepts

* A **schema** is a namespace that groups tables, views, functions, etc.
* Think of it like a drawer in a filing cabinet.

```sql
CREATE SCHEMA sales_data;
SET search_path TO sales_data;
```

---

### 3. SQL Data Types

| Category  | Data Type                   | Example          |
| --------- | --------------------------- | ---------------- |
| Numeric   | `INT`, `DECIMAL`, `NUMERIC` | `100`, `1234.56` |
| Character | `VARCHAR`, `TEXT`           | `'John Doe'`     |
| Date/Time | `DATE`, `TIMESTAMP`         | `'2024-01-01'`   |
| Boolean   | `BOOLEAN`                   | `TRUE`, `FALSE`  |

---

### 4. Creating Tables

```sql
CREATE TABLE employees (
  employee_id INT PRIMARY KEY,
  first_name VARCHAR(50),
  last_name VARCHAR(50),
  hire_date DATE,
  salary NUMERIC(10, 2)
);
```

**Constraints:**

* `PRIMARY KEY`, `NOT NULL`, `UNIQUE`, `DEFAULT`, `FOREIGN KEY`

---

### 5. Inserting, Updating, and Deleting Data

**Insert Example**

```sql
INSERT INTO customers (first_name, last_name, email)
VALUES ('Ali', 'Hassan', 'ali@example.com');
```

**Update Example**

```sql
UPDATE customers
SET city = 'Nairobi'
WHERE customer_id = 1;
```

**Delete Example**

```sql
DELETE FROM customers
WHERE customer_id = 1;
```

---

### 6. Table Alterations

| Operation              | Example                                                               |
| ---------------------- | --------------------------------------------------------------------- |
| Add Column             | `ALTER TABLE customers ADD COLUMN city VARCHAR(100);`                 |
| Drop Column            | `ALTER TABLE books DROP COLUMN published_date;`                       |
| Rename Table           | `ALTER TABLE customers RENAME TO clients;`                            |
| Rename Column          | `ALTER TABLE customers RENAME COLUMN phone_number TO contact_number;` |
| Change Column Type     | `ALTER TABLE orders ALTER COLUMN quantity TYPE DECIMAL(5,2);`         |
| Set/Drop Default Value | `ALTER COLUMN quantity SET DEFAULT 1;` / `DROP DEFAULT;`              |
| NOT NULL Constraint    | `ALTER COLUMN email SET NOT NULL;` / `DROP NOT NULL;`                 |

---

### 7. Keys & Relationships

**Foreign Key Example**

```sql
ALTER TABLE orders
ADD CONSTRAINT fk_customer
FOREIGN KEY (customer_id)
REFERENCES customers(customer_id);
```

---

### 8. Aggregate Functions

| Function | Description     | Example                           |
| -------- | --------------- | --------------------------------- |
| COUNT()  | Counts rows     | `SELECT COUNT(*) FROM customers;` |
| SUM()    | Adds values     | `SELECT SUM(price) FROM books;`   |
| AVG()    | Averages values | `SELECT AVG(price) FROM books;`   |
| MAX()    | Maximum value   | `SELECT MAX(price) FROM books;`   |
| MIN()    | Minimum value   | `SELECT MIN(price) FROM books;`   |

---

### 9. Filtering Records

```sql
-- Exact match
SELECT * FROM customers WHERE city = 'Nairobi';

-- Range
SELECT * FROM books WHERE price BETWEEN 1000 AND 3000;

-- Pattern match
SELECT * FROM books WHERE title LIKE '%Python%';

-- List match
SELECT * FROM customers WHERE city IN ('Nairobi', 'Kisumu');

-- Null values
SELECT * FROM books WHERE author IS NULL;
```

---

### 10. Logical Operators

| Operator | Meaning                             |
| -------- | ----------------------------------- |
| `AND`    | All conditions must be true         |
| `OR`     | At least one condition must be true |
| `NOT`    | Negates the condition               |

---

### 11. Arithmetic Operators

| Operator | Use            | Example        |
| -------- | -------------- | -------------- |
| `+`      | Addition       | `price + 100`  |
| `-`      | Subtraction    | `quantity - 2` |
| `*`      | Multiplication | `quantity * 5` |
| `/`      | Division       | `price / 2`    |
| `%`      | Modulus        | `quantity % 2` |

---

### 12. Set Operators

| Operator    | Purpose                                     |
| ----------- | ------------------------------------------- |
| `UNION`     | Combines results, removes duplicates        |
| `UNION ALL` | Combines results, keeps duplicates          |
| `INTERSECT` | Returns common records from both queries    |
| `EXCEPT`    | Returns rows from first query not in second |

---

### 13. Sorting, Grouping & Limiting

**Sorting Results**

```sql
SELECT * FROM books ORDER BY price DESC;
```

**Grouping & Filtering Groups**

```sql
SELECT author, COUNT(*) FROM books GROUP BY author;
SELECT author FROM books GROUP BY author HAVING COUNT(*) > 1;
```

**Limiting Results**

```sql
SELECT * FROM books LIMIT 5;
```

---

### 14. Other Useful Clauses

| Clause        | Example                                         |
| ------------- | ----------------------------------------------- |
| `IS NULL`     | `SELECT * FROM books WHERE author IS NULL;`     |
| `IS NOT NULL` | `SELECT * FROM books WHERE author IS NOT NULL;` |
| `DISTINCT`    | `SELECT DISTINCT city FROM customers;`          |

---

### Best Practices

* Use lowercase and `snake_case` for table/column names
* Always define a primary key
* Use `VARCHAR` instead of `CHAR` unless fixed length is needed
* Avoid using `SELECT *` in production
* Comment your SQL code using `--`

---


