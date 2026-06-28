
2024-08-11 11:14

Status:

Tags: #UOM #L2S2-S4 #DB


# DB - Recap
## What is a Database?

A database is an organized collection of data that is stored and accessed electronically. It allows users to create, read, update and delete data efficiently. Databases are used in a wide range of applications, from banking systems to social networks. Some key characteristics of databases include:

- **Data is stored in tables** with rows and columns
- **Tables have a schema** that defines the structure of the data
- **Databases provide concurrency control** to allow multiple users to access data simultaneously
- **Databases ensure data integrity** by enforcing constraints and validating data
- **Databases provide security** to control who can access and modify data

## Entity Relationship (ER) Diagrams

ER diagrams are a visual representation of the entities in a database and their relationships. They consist of:

- **Entities**: Objects or concepts about which data is collected (e.g. **customers**, **products**, **orders**)
- **Attributes**: Properties that describe an entity (e.g. **customer name**, **product price**, **order date**)
- **Relationships**: Associations between entities (e.g. **customers place orders**, **products belong to categories**)

ER diagrams help design the logical structure of a database by identifying the key entities and their relationships. They provide a blueprint for creating the actual database tables and schema.

## Normalization

Normalization is the process of organizing data in a database to reduce redundancy and dependency. It involves breaking down a table into smaller tables and defining relationships between them. The main goals of normalization are:

- **Minimize data redundancy**: Avoid storing the same data in multiple places
- **Eliminate insertion, update and deletion anomalies**: Ensure data consistency and integrity
- **Simplify queries**: Make it easier to retrieve data by breaking it down into smaller related tables

There are different normal forms that define the level of normalization, starting from 1NF (first normal form) up to 5NF (fifth normal form). Most databases are normalized up to 3NF which eliminates transitive dependencies. Normalization is important because it:

- **Saves storage space** by eliminating redundant data
- **Improves data integrity** by ensuring data consistency
- **Simplifies database maintenance** by reducing update and deletion anomalies
- **Improves query performance** by breaking down data into smaller related tables

## SQL Queries

SQL (Structured Query Language) is the standard language used to manage and manipulate relational databases. Here are some common SQL queries:

## Creating a Database

``` sql
CREATE DATABASE my_database;
```

## Creating Tables

```sql
CREATE TABLE customers (   customer_id INT PRIMARY KEY,  name VARCHAR(50),  email VARCHAR(50) );
```

## Inserting Data

To insert multiple customers at once, you can use the `VALUES` clause with a comma-separated list of rows:

```sql
INSERT INTO customers (customer_id, name, email) 
VALUES 
(1, 'John Doe', 'john@example.com'), 
(2, 'Jane Smith', 'jane@example.com'), 
(3, 'Bob Johnson', 'bob@example.com');
```

## Updating Records

To update multiple customers at once, you can use a `CASE` statement in the `SET` clause:

```sql
UPDATE customers 
SET email = 'newemail@example.com' 
WHERE customer_id = 1;

UPDATE customers 
SET email = 
	CASE customer_id 
	WHEN 1 THEN 'newemail1@example.com' 
	WHEN 2 THEN 'newemail2@example.com' 
	WHEN 3 THEN 'newemail3@example.com' 
END 
WHERE customer_id IN (1, 2, 3);
```

## Querying Data

```sql
SELECT * FROM customers; 
SELECT name, email FROM customers WHERE customer_id = 1;
```

## Constraints

```sql
CREATE TABLE products ( 
	product_id INT PRIMARY KEY, 
	name VARCHAR(50) NOT NULL, 
	price DECIMAL(10,2) CHECK (price > 0) 
);
```

## Deleting Records

```sql
DELETE FROM customers WHERE customer_id = 1;
```

## Aggregate Functions

```sql
SELECT AVG(price) AS avg_price FROM products; 
SELECT COUNT(*) AS total_products FROM products;
```

## Joins

```sql
SELECT customers.name, orders.order_date 
FROM customers 
INNER JOIN orders ON customers.customer_id = orders.customer_id;
```

Real World Examples:

1. **Banking System**: Stores customer accounts, transactions, loans, and other banking data. Ensures data integrity by enforcing constraints like unique account numbers and positive balances.
2. **E-commerce Website**: Stores product catalogs, customer profiles, shopping carts, and order histories. Uses normalization to avoid redundancy and simplify queries. Provides concurrency control to handle simultaneous customer sessions.
3. **University Database**: Stores student records, course information, grades, and faculty data. Uses ER diagrams to model the relationships between entities like students, courses, and professors. Enforces constraints like mandatory course prerequisites.
4. **Social Network**: Stores user profiles, connections, posts, comments, and likes. Ensures data integrity by validating user inputs and enforcing referential integrity between related entities. Provides security to control access to private user data.

# SQL Joins Overview

SQL joins are used to combine rows from two or more tables based on a related column between them. They enable the retrieval of data that is spread across multiple tables, which is common in relational databases. The four main types of joins are:

1. **Inner Join**
2. **Left Join (Left Outer Join)**
3. **Right Join (Right Outer Join)**
4. **Full Join (Full Outer Join)**

Each type of join serves different use cases and has distinct behaviors regarding how data is combined.

![[Pasted image 20240811114503.jpg | 700]]
## 1. Inner Join

**Description**: An inner join returns only the rows that have matching values in both tables. If there is no match, the rows are excluded from the result set.

**Use Case**: This is useful when you want to retrieve records that have related data in both tables.

**Example Query**:
```sql
SELECT e.emp_name, d.dept_name 
FROM employees e INNER JOIN departments d ON e.dept_id = d.id;
```

**Real-World Application**: In an office management system, if you want to list employees along with their department names, you would use an inner join to ensure only employees with assigned departments are included.


![[innerJoin_3.gif]]

## 2. Left Join (Left Outer Join)

**Description**: A left join returns all rows from the left table and the matched rows from the right table. If there is no match, the result will contain NULL values for columns from the right table.

**Use Case**: This is useful when you want to retrieve all records from one table regardless of whether there is a match in the other table.

**Example Query**:
```sql
SELECT e.emp_name, d.dept_name 
FROM employees e LEFT JOIN departments d ON e.dept_id = d.id;
```

**Real-World Application**: If you want to list all employees and their departments, including employees who are not assigned to any department, a left join will ensure that all employees are included, with NULL for department names where applicable.

![[leftJoin_1.gif | 700]]

## 3. Right Join (Right Outer Join)

**Description**: A right join returns all rows from the right table and the matched rows from the left table. If there is no match, the result will contain NULL values for columns from the left table.

**Use Case**: This is useful when you want to retrieve all records from the right table regardless of whether there is a match in the left table.

**Example Query**:
```sql
SELECT e.emp_name, d.dept_name 
FROM employees e RIGHT JOIN departments d ON e.dept_id = d.id;
```

**Real-World Application**: When you want to list all departments and the employees assigned to them, including departments that have no employees, a right join will ensure all departments are shown, with NULL for employee names where applicable.

![[leftJoin_3.gif | 700]]

## 4. Full Join (Full Outer Join)

**Description**: A full join returns all rows when there is a match in either the left or right table records. If there is no match, the result will contain NULL values for the non-matching side.

**Use Case**: This is useful when you want to retrieve all records from both tables, regardless of whether there is a match.

**Example Query**:
```sql
SELECT e.emp_name, d.dept_name 
FROM employees e FULL OUTER JOIN departments d ON e.dept_id = d.id;
```

**Real-World Application**: If you want to see all employees and all departments, including employees without departments and departments without employees, a full join will provide a comprehensive view.

![[fullOuter_1.gif | 700]]

## Best Practices for Using Joins

1. **Use Aliases**: To improve readability, especially when dealing with multiple tables, use table aliases.
2. **Be Specific with Columns**: Instead of using `SELECT *`, specify the columns you need to avoid unnecessary data retrieval.
3. **Filter with WHERE Clause**: Use the `WHERE` clause to filter results further after joining to improve performance.
4. **Indexing**: Ensure that the columns used in join conditions are indexed to speed up query performance.
5. **Understand the Data Relationships**: Before joining tables, understand the relationships between them to avoid incorrect results.
6. **Test Queries**: Always test your queries with sample data to ensure they return the expected results.

By understanding these types of joins and their applications, you can effectively retrieve and manipulate data across multiple tables in SQL, making your data analysis more robust and insightful.

![](https://miro.medium.com/v2/resize:fit:875/1*318PmBNM4c6wzlKEqmJQLQ.gif | 700)


# SQL Grouping, Aggregation, and Filtering

In SQL, the `GROUP BY` clause is used to arrange identical data into groups, often in conjunction with aggregate functions like `SUM()`, `COUNT()`, `AVG()`, `MAX()`, and `MIN()`. This allows for powerful data analysis and reporting capabilities. The `HAVING` clause is used to filter groups based on aggregate values, while the `EXISTS` clause checks for the existence of rows in a subquery.

## 1. GROUP BY Clause

**Description**: The `GROUP BY` clause groups rows that have the same values in specified columns into summary rows. It is typically used with aggregate functions to perform calculations on each group.

**Syntax**:
```sql
SELECT column1, aggregate_function(column2) 
FROM table_name 
WHERE condition 
GROUP BY column1;
```

**Use Case**: Useful for summarizing data, such as counting the number of orders per customer or calculating the total sales per product.

**Example**:

```sql
SELECT country, COUNT(*) AS customer_count 
FROM customers 
GROUP BY country;
```

**Real-World Application**: This query counts the number of customers in each country, which can help a business understand its market distribution.

## 2. HAVING Clause

**Description**: The `HAVING` clause is used to filter records that work on summarized `GROUP BY` results. Unlike the `WHERE` clause, which filters rows before aggregation, `HAVING` filters after aggregation.

**Syntax**:

```sql
SELECT column1, aggregate_function(column2) 
FROM table_name 
GROUP BY column1 
HAVING aggregate_function(column2) condition;
```

**Use Case**: Useful for filtering groups based on aggregate values, such as finding products with total sales above a certain threshold.

**Example**:

```sql
SELECT product_id, SUM(sales) AS total_sales 
FROM sales_data 
GROUP BY product_id 
HAVING SUM(sales) > 10000;
```

**Real-World Application**: This query identifies products that have generated more than $10,000 in sales, helping management focus on high-performing items.

## 3. EXISTS Clause

**Description**: The `EXISTS` clause is used to check if a subquery returns any rows. It returns true if the subquery returns one or more rows.

**Syntax**:

```sql
SELECT column1 
FROM table_name 
WHERE EXISTS (SELECT 1 FROM other_table WHERE condition);
```

**Use Case**: Useful for checking the presence of related records, such as confirming if a customer has placed any orders.

**Example**:

```sql
SELECT customer_id 
FROM customers c 
WHERE EXISTS (SELECT 1 FROM orders o WHERE o.customer_id = c.customer_id);
```

**Real-World Application**: This query retrieves all customers who have placed at least one order, which can be useful for targeted marketing campaigns.

## Best Practices for Using GROUP BY, HAVING, and EXISTS

1. **Use Aggregate Functions Wisely**: Always pair `GROUP BY` with aggregate functions to summarize data effectively.
2. **Filter Early**: Use the `WHERE` clause to filter rows before grouping to reduce the dataset size, which can improve performance.
3. **Use HAVING for Group Conditions**: Reserve the `HAVING` clause for conditions that apply to aggregated data, not for filtering individual rows.
4. **Optimize Subqueries with EXISTS**: Use `EXISTS` for checking the presence of related records instead of counting rows, as it can be more efficient.
5. **Indexing**: Ensure that columns used in `GROUP BY`, `HAVING`, and `EXISTS` clauses are indexed to improve query performance.
6. **Test Queries**: Always test your queries with sample data to ensure they return the expected results.

## Summary

By understanding and applying the `GROUP BY`, `HAVING`, and `EXISTS` clauses effectively, you can perform complex data analysis and reporting in SQL. These tools allow you to summarize, filter, and validate data in meaningful ways, providing valuable insights for decision-making in real-world applications.

# Reference
![[MSSQL - LAB 1 - Part 2.pdf]]