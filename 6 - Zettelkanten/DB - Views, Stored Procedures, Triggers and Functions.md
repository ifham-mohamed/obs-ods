
2024-08-11 12:56

Status:

Tags: #UOM #L2S2-S4 #DB 


# DB - Views
\
# Understanding Views in SQL

**Definition**: A view in SQL is a virtual table that is based on the result of a SELECT query. It does not store the data itself but provides a way to represent data from one or more tables in a simplified manner. Views can be used to simplify complex queries, enhance security, and provide a level of abstraction.

![[Pasted image 20240811144817.png | 700]]
### Types of Views

1. **Simple View**: 
   - Based on a single table.
   - Does not contain any aggregate functions or GROUP BY clauses.
   - Example: A view that displays only specific columns from a customer table.

2. **Complex View**: 
   - Based on multiple tables.
   - May contain aggregate functions, GROUP BY clauses, and JOIN operations.
   - Example: A view that combines customer and order information.

3. **Inline View**: 
   - A temporary view defined within a SELECT statement.
   - Useful for simplifying complex queries without creating a permanent view.

4. **Materialized View**: 
   - Stores the result of the query physically.
   - Can be refreshed periodically and provides better performance for read-heavy operations.
   - Example: A view that aggregates sales data for reporting purposes.

### Use Cases of Views

1. **Simplifying Complex Queries**: Views can encapsulate complex SQL logic, making it easier for users to retrieve data without needing to understand the underlying complexity.

2. **Security**: Views can restrict access to sensitive data by exposing only specific columns or rows. For example, a view can be created to show only customer names and contact information, hiding sensitive details like credit card numbers.

3. **Data Abstraction**: Views provide a layer of abstraction, allowing users to interact with data without needing to know the details of the underlying tables.

4. **Reporting**: Views can be used to create reports by aggregating and summarizing data from multiple tables, making it easier to generate insights.

### Best Practices for Using Views

1. **Use Descriptive Names**: Name views clearly to indicate their purpose, making it easier for others to understand their function.

2. **Limit the Complexity**: Avoid overly complex views that combine too many tables or logic. This can lead to performance issues and make maintenance difficult.

3. **Index Underlying Tables**: Ensure that the tables underlying the views are indexed appropriately to improve performance.

4. **Regularly Review and Update**: Periodically review views to ensure they still meet business needs and update them as necessary, especially if the underlying table structures change.

5. **Use Views for Security**: Implement views to control user access to sensitive data, allowing users to see only what they need.

### Example Queries

**Creating a Simple View**:
```sql
CREATE VIEW V_CustomerNames AS
SELECT customer_id, name, email
FROM customers;
```
This view allows users to access customer names and emails without exposing other sensitive information.

**Creating a Complex View**:
```sql
CREATE VIEW V_SalesSummary AS
SELECT c.customer_id, c.name, SUM(o.amount) AS total_sales
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
GROUP BY c.customer_id, c.name;
```
This view summarizes total sales per customer, making it easier to analyze sales performance.

**Using a View**:
```sql
SELECT * FROM V_CustomerNames;
```
This query retrieves all customer names and emails from the view.

**Updating a View**:
```sql
CREATE OR REPLACE VIEW V_CustomerNames AS
SELECT customer_id, name, email, phone
FROM customers;
```
This updates the view to include the phone number.

**Dropping a View**:
```sql
DROP VIEW IF EXISTS V_CustomerNames;
```
This command removes the view from the database.
	
Views in SQL are powerful tools that provide a virtual representation of data from one or more tables. While they offer numerous advantages, they also come with certain limitations. Here’s an overview of the limitations of using views, along with their implications and best practices.

### Limitations of Using Views

1. **No Parameter Passing**:
   - **Description**: You cannot pass parameters to views. This limits the flexibility of views in dynamic queries.
   - **Example**: Attempting to create a view that accepts parameters will result in an error.
   - **Implication**: Users must filter data after querying the view, which can lead to more complex SQL statements.
   - **Alternative**: Use inline table-valued functions instead of views for parameterized queries[1].

2. **ORDER BY Clause Restrictions**:
   - **Description**: The `ORDER BY` clause cannot be used in a view unless combined with `TOP` or `FOR XML`.
   - **Example**: A view cannot enforce a specific order of results unless it includes these clauses.
   - **Implication**: Users may need to sort data after retrieving it from the view, which can lead to inconsistencies.
   - **Recommendation**: Always apply sorting in the final SELECT statement rather than relying on views to maintain order[1].

3. **Dependency on Underlying Tables**:
   - **Description**: If the underlying tables are modified (e.g., columns renamed or dropped), the view may become invalid.
   - **Example**: If a column used in a view is removed from the base table, querying the view will result in an error.
   - **Implication**: Maintenance overhead increases, as views must be updated whenever the underlying table structure changes[3][4].

4. **Performance Issues**:
   - **Description**: Views can introduce performance overhead, especially if they are based on complex queries or large datasets.
   - **Example**: Each time a view is queried, the underlying SQL statement is executed, which can slow down performance.
   - **Implication**: Frequent use of views in complex queries may lead to slower response times compared to querying base tables directly[2][4].
   - **Best Practice**: Use views judiciously, especially for frequently accessed data, and consider materialized views for performance-critical scenarios.

5. **Read-Only Restrictions**:
   - **Description**: Some views are read-only, particularly complex views that involve joins or aggregations.
   - **Example**: Attempting to insert or update data through a read-only view will result in an error.
   - **Implication**: This limits the usability of views in scenarios where data manipulation is required[2][4].

6. **Storage and Resource Utilization**:
   - **Description**: While views themselves do not store data, they can consume resources during execution.
   - **Example**: Complex views may require significant CPU and memory resources when queried.
   - **Implication**: Overusing views can lead to resource contention and impact overall database performance[3][4].

### Best Practices for Using Views

1. **Use Views for Security**: Create views that expose only necessary columns to limit access to sensitive data. This helps enforce data security policies.

2. **Keep Views Simple**: Avoid creating overly complex views. Instead, focus on creating simple views that encapsulate specific logic or data.

3. **Regularly Review Views**: Periodically assess views for relevance and performance. Update or remove views that are no longer needed or that reference outdated table structures.

4. **Test Performance**: Monitor the performance of views and consider optimizing or replacing them with alternative solutions if they cause bottlenecks.

5. **Use Inline Table-Valued Functions for Parameterization**: When dynamic filtering is needed, consider using inline table-valued functions instead of views to allow parameter passing.

6. **Document View Definitions**: Maintain clear documentation of view definitions and their intended use cases to facilitate easier maintenance and understanding for other developers.

### Conclusion

While views in SQL provide significant benefits, including simplified data access and enhanced security, they also come with limitations that can impact performance and usability. Understanding these limitations and following best practices can help you effectively leverage views in your database applications while minimizing potential drawbacks.

Citations:
[1] https://www.mssqltips.com/sqlservertip/5147/limitations-when-working-with-sql-server-views/
[2] https://www.tutorchase.com/answers/a-level/computer-science/what-are-the-advantages-and-disadvantages-of-using-a-view-in-sql
[3] https://stackoverflow.com/questions/3854606/what-are-the-disadvantage-of-sql-views
[4] https://www.c-sharpcorner.com/blogs/advantages-and-disadvantages-of-views-in-sql-server1
[5] https://www.datacamp.com/tutorial/views-in-sql


# Understanding Stored Procedures in SQL

**Definition**: A stored procedure is a precompiled collection of SQL statements that can be executed as a single unit. Stored procedures are stored in the database and can accept parameters, perform operations, and return results. They enhance performance, security, and maintainability by encapsulating complex logic.

![[Pasted image 20240811150015.png | 700]]
### Key Features of Stored Procedures

1. **Reusability**: Stored procedures can be called multiple times with different parameters, reducing code duplication.
  
2. **Performance**: Since stored procedures are precompiled, they can execute faster than individual SQL statements, especially when called repeatedly.

3. **Security**: They provide a layer of security by allowing users to execute procedures without granting direct access to the underlying tables.

4. **Maintainability**: Changes to business logic can be made in one place (the stored procedure), rather than updating multiple queries throughout the application.

5. **Error Handling**: Stored procedures can include error handling logic, making it easier to manage exceptions and ensure data integrity.

### Use Cases of Stored Procedures

1. **Data Manipulation**: Performing complex operations like inserting, updating, or deleting records in a single call.
   
2. **Batch Processing**: Executing a series of SQL statements that need to be run together, such as data migrations or scheduled tasks.

3. **Reporting**: Generating reports by aggregating data from multiple tables and returning the results in a structured format.

4. **Business Logic Implementation**: Encapsulating business rules that dictate how data should be processed or validated.

### Syntax for Creating Stored Procedures

The basic syntax for creating a stored procedure varies slightly between different SQL databases, but generally follows this structure:

```sql
CREATE PROCEDURE procedure_name (parameter1 datatype, parameter2 datatype, ...)
BEGIN
    -- SQL statements to be executed
END;
```

### Example Queries

**1. Creating a Simple Stored Procedure**:

This example creates a stored procedure that retrieves customer information based on age.

```sql
DELIMITER //
CREATE PROCEDURE GetCustomerInfo(IN CustomerAge INT)
BEGIN
    SELECT * FROM Customers WHERE Age = CustomerAge;
END //
DELIMITER ;
```

**2. Executing the Stored Procedure**:

To call the stored procedure and retrieve customer data for those aged 25:

```sql
CALL GetCustomerInfo(25);
```

**3. Using Output Parameters**:

This example demonstrates a stored procedure that counts the number of customers of a specific age and returns that count.

```sql
DELIMITER //
CREATE PROCEDURE GetCustomerCount(OUT total INT)
BEGIN
    SELECT COUNT(*) INTO total FROM Customers WHERE Age = 25;
END //
DELIMITER ;
```

To call this procedure and get the count:

```sql
CALL GetCustomerCount(@total);
SELECT @total AS TotalCustomers;
```

**4. Handling Multiple Parameters**:

A stored procedure that retrieves employee titles based on gender and returns the count of employees.

```sql
CREATE PROCEDURE GetTitleForHREmployees (
    IN Gender NCHAR(1),
    OUT EmployeeCount INT
)
BEGIN
    SELECT JobTitle FROM HumanResources.Employee WHERE Gender = Gender;
    SELECT EmployeeCount = @@ROWCOUNT;  -- Get the number of rows returned
END;
```

### Best Practices for Using Stored Procedures

1. **Use Descriptive Names**: Name stored procedures clearly to indicate their purpose, making it easier for others to understand their functionality.

2. **Limit Complexity**: Keep stored procedures focused on a single task to enhance readability and maintainability. Avoid overly complex logic within a single procedure.

3. **Parameterize Queries**: Use parameters to pass values to stored procedures, enabling dynamic execution and reducing SQL injection risks.

4. **Implement Error Handling**: Include error handling within stored procedures to manage exceptions gracefully and maintain data integrity.

5. **Document Procedures**: Provide comments and documentation within the stored procedure to explain its purpose and functionality for future reference.

6. **Regularly Review and Optimize**: Periodically review stored procedures for performance and relevance, optimizing them as necessary.


Stored procedures are a powerful feature of SQL that enhance the efficiency, security, and maintainability of database operations. By encapsulating complex logic and promoting code reuse, stored procedures can significantly improve application performance and simplify database management. Understanding how to create and utilize stored procedures effectively will enable developers to build robust and efficient database applications.

# Understanding Triggers in SQL

**Definition**: A trigger is a database object that automatically executes a specified set of SQL statements in response to certain events on a particular table or view. Triggers are useful for enforcing business rules, maintaining data integrity, and automating tasks without requiring explicit calls from applications.

![[Pasted image 20240811150720.png | 700]]
### Types of Triggers

1. **DML Triggers (Data Manipulation Language)**:
   - **Description**: These triggers respond to data manipulation events such as `INSERT`, `UPDATE`, and `DELETE`.
   - **Types**:
     - **AFTER Trigger**: Executes after the triggering event has occurred.
     - **BEFORE Trigger**: Executes before the triggering event occurs.
     - **INSTEAD OF Trigger**: Executes in place of the triggering event, allowing for custom actions.

2. **DDL Triggers (Data Definition Language)**:
   - **Description**: These triggers respond to changes in the database schema, such as `CREATE`, `ALTER`, and `DROP` statements.
   - **Use Case**: Useful for auditing changes to the database structure or enforcing rules on schema modifications.

3. **LOGON and LOGOFF Triggers**:
   - **Description**: These triggers execute in response to user logon or logoff events.
   - **Use Case**: Can be used for auditing or enforcing security policies.

### Use Cases of Triggers

1. **Auditing Changes**: Automatically logging changes to important tables, such as recording who modified a record and when.
   - **Example**: A trigger that logs every change made to a customer’s data into an audit table.

2. **Enforcing Business Rules**: Ensuring that certain conditions are met before data is modified.
   - **Example**: A trigger that prevents the deletion of a customer record if there are outstanding orders.

3. **Maintaining Data Integrity**: Automatically updating or validating data in related tables.
   - **Example**: A trigger that updates a total sales column in a summary table whenever a new sale is recorded.

4. **Automating Tasks**: Performing routine tasks automatically in response to changes in the database.
   - **Example**: Sending notifications or updating related records when a new user is added.

### Example Queries

**1. Creating a Simple AFTER Trigger**:

This example creates a trigger that logs user creation into a separate log table whenever a new user is added.

```sql
CREATE TRIGGER log_user_creation
AFTER INSERT ON users
FOR EACH ROW
AS
    INSERT INTO user_creation_log(user_id, created_at)
    VALUES (NEW.id, NOW());
GO;
```

**2. Creating a BEFORE Trigger**:

This trigger prevents the insertion of a record if the age of the user is less than 18.

```sql
CREATE TRIGGER check_user_age
BEFORE INSERT ON users
FOR EACH ROW
AS
    IF NEW.age < 18 THEN
        SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'User must be at least 18 years old';
    END IF;
GO;
```

**3. Creating an INSTEAD OF Trigger**:

This example shows how to use an INSTEAD OF trigger to handle updates on a view that aggregates data.

```sql
CREATE TRIGGER update_sales_summary
INSTEAD OF UPDATE ON sales_summary_view
FOR EACH ROW
AS
    UPDATE sales
    SET amount = NEW.amount
    WHERE sale_id = NEW.sale_id;
GO;
```

### Best Practices for Using Triggers

1. **Keep Triggers Simple**: Avoid complex logic within triggers to maintain performance and readability. Complex triggers can lead to maintenance challenges.

2. **Limit the Number of Triggers**: Overusing triggers can complicate debugging and performance. Use them judiciously to avoid confusion.

3. **Document Trigger Logic**: Provide clear comments and documentation for triggers to explain their purpose and functionality for future reference.

4. **Test Thoroughly**: Ensure that triggers are tested in various scenarios to confirm they behave as expected and do not introduce unintended side effects.

5. **Monitor Performance**: Regularly review the performance impact of triggers, especially if they are executing complex queries or are triggered frequently.

6. **Avoid Recursive Triggers**: Be cautious of creating triggers that can invoke themselves indirectly, as this can lead to infinite loops and performance issues.


Row-level triggers and statement-level triggers are two types of triggers in SQL that serve different purposes and operate in distinct ways. Here’s a detailed comparison of the two, including their characteristics, use cases, and real-world applications.

## Row-Level Triggers

**Definition**: Row-level triggers are executed once for each row affected by a triggering event (e.g., `INSERT`, `UPDATE`, or `DELETE`). This means that if a single SQL statement affects multiple rows, the row-level trigger will fire for each of those rows.

**Characteristics**:
- **Execution**: Executes for each row affected.
- **Syntax**: Uses the `FOR EACH ROW` clause in the trigger definition.
- **Access to Row Data**: Can use the `NEW` and `OLD` qualifiers to access the values of the affected rows.
- **Performance**: Generally has lower performance compared to statement-level triggers when processing large data sets, as it executes multiple times.

**Use Cases**:
- **Auditing Changes**: Keeping track of changes made to individual rows, such as logging updates to a customer record.
- **Data Validation**: Enforcing business rules on each row, such as preventing the insertion of rows with invalid data.
- **Cascading Actions**: Automatically updating related records when a row is modified.

**Example**:
```sql
CREATE TRIGGER update_employee_salary
AFTER UPDATE ON employees
FOR EACH ROW
BEGIN
    INSERT INTO salary_audit(employee_id, old_salary, new_salary, change_date)
    VALUES (OLD.id, OLD.salary, NEW.salary, NOW());
END;
```
In this example, the trigger logs the old and new salary for each employee whenever their salary is updated.

### Statement-Level Triggers

**Definition**: Statement-level triggers are executed once for the entire SQL statement, regardless of how many rows are affected. This means that even if a single statement modifies multiple rows, the trigger will only fire once.

**Characteristics**:
- **Execution**: Executes only once per triggering event.
- **Syntax**: Does not use the `FOR EACH ROW` clause.
- **Access to Row Data**: Cannot use `NEW` and `OLD` qualifiers since it does not operate on individual rows.
- **Performance**: Generally has better performance for operations affecting many rows, as it executes only once.

**Use Cases**:
- **Enforcing Business Rules**: Implementing restrictions that apply to the entire transaction, such as preventing updates if certain conditions are met.
- **Logging Operations**: Recording an event that occurs regardless of the number of rows affected, such as logging the time when a bulk update occurs.
- **Aggregate Calculations**: Performing calculations that summarize data across multiple rows, such as updating a summary table after a batch operation.

**Example**:
```sql
CREATE TRIGGER log_employee_updates
AFTER UPDATE ON employees
BEGIN
    INSERT INTO update_log(update_time, updated_by)
    VALUES (NOW(), USER());
END;
```
In this example, the trigger logs the time and user who performed an update on the employees table, regardless of how many rows were updated.

### Key Differences

| Feature             | Row-Level Triggers                      | Statement-Level Triggers                         |
| ------------------- | --------------------------------------- | ------------------------------------------------ |
| Execution Frequency | Executes once for each affected row     | Executes once for the entire statement           |
| Syntax              | Uses `FOR EACH ROW` clause              | Does not use `FOR EACH ROW` clause               |
| Access to Row Data  | Can use `NEW` and `OLD` qualifiers      | Cannot access individual row data                |
| Performance         | Slower for bulk operations              | Faster for operations affecting many rows        |
| Use Cases           | Auditing, validation, cascading actions | Enforcing rules, logging, aggregate calculations |

### Real-World Applications

- **Row-Level Trigger Example**: In a banking application, a row-level trigger can be used to log every transaction made by customers, capturing details such as transaction amount and type for auditing purposes.
  
- **Statement-Level Trigger Example**: In an e-commerce application, a statement-level trigger can be used to enforce a business rule that prevents any updates to product prices during a sale event, regardless of how many products are affected.

### Types of Triggers

Triggers in SQL are powerful tools that allow you to automate tasks in response to specific events on a database table. Here’s an overview of the different types of triggers, their real-world use cases, and code examples for each type.

#### 1. DML Triggers (Data Manipulation Language)

DML triggers respond to data manipulation events such as `INSERT`, `UPDATE`, and `DELETE`. They can be categorized into three types:

- **AFTER Trigger**: Executes after the triggering event has occurred.
- **BEFORE Trigger**: Executes before the triggering event occurs.
- **INSTEAD OF Trigger**: Executes in place of the triggering event, allowing for custom actions.

##### Use Cases for DML Triggers

- **Auditing Changes**: Automatically log changes to critical tables.
- **Data Validation**: Ensure that data meets specific criteria before it is modified.
- **Cascading Actions**: Update or delete related records automatically.

##### Example Code

**AFTER Trigger Example**: Logging changes to a product's price.

```sql
CREATE TABLE ProductPriceHistory (
    PriceHistoryID INT PRIMARY KEY IDENTITY,
    ProductID INT,
    PreviousPrice DECIMAL(10, 2),
    NewPrice DECIMAL(10, 2),
    ChangeDate DATETIME DEFAULT GETDATE()
);

CREATE TRIGGER trgAfterPriceUpdate
AFTER UPDATE ON Products
FOR EACH ROW
BEGIN
    INSERT INTO ProductPriceHistory (ProductID, PreviousPrice, NewPrice)
    VALUES (OLD.ProductID, OLD.Price, NEW.Price);
END;
```

**BEFORE Trigger Example**: Preventing insertion of invalid data.

```sql
CREATE TRIGGER trgBeforeInsert
BEFORE INSERT ON Employees
FOR EACH ROW
BEGIN
    IF NEW.Age < 18 THEN
        SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Employee must be at least 18 years old';
    END IF;
END;
```

**INSTEAD OF Trigger Example**: Custom handling of DELETE operations.

```sql
CREATE TRIGGER trgInsteadOfDelete
INSTEAD OF DELETE ON Employees
FOR EACH ROW
BEGIN
    INSERT INTO DeletedEmployees (EmployeeID, DeletedAt)
    VALUES (OLD.EmployeeID, NOW());
END;
```

#### 2. DDL Triggers (Data Definition Language)

DDL triggers respond to changes in the database schema, such as `CREATE`, `ALTER`, and `DROP` statements. They are useful for auditing schema changes or enforcing rules on schema modifications.

##### Use Cases for DDL Triggers

- **Auditing Schema Changes**: Track who made changes to the database schema and when.
- **Preventing Unauthorized Changes**: Restrict certain users from making schema modifications.

##### Example Code

**DDL Trigger Example**: Auditing changes to the database schema.

```sql
CREATE TABLE SchemaChangeLog (
    ChangeID INT PRIMARY KEY IDENTITY,
    ChangeType NVARCHAR(50),
    ChangeTime DATETIME DEFAULT GETDATE(),
    UserName NVARCHAR(50)
);

CREATE TRIGGER trgDDLChanges
AFTER CREATE OR ALTER OR DROP ON SCHEMA
FOR EACH STATEMENT
BEGIN
    INSERT INTO SchemaChangeLog (ChangeType, UserName)
    VALUES (EVENT_TYPE, USER());
END;
```

#### 3. LOGON and LOGOFF Triggers

These triggers execute in response to user logon or logoff events. They can be used for auditing or enforcing security policies.

##### Use Cases for LOGON and LOGOFF Triggers

- **Auditing User Access**: Log user logon and logoff times for security purposes.
- **Restricting Access**: Prevent certain users from logging in during specific times.

##### Example Code

**LOGON Trigger Example**: Logging user logon times.

```sql
CREATE TABLE UserLogins (
    LoginID INT PRIMARY KEY IDENTITY,
    UserName NVARCHAR(50),
    LoginTime DATETIME DEFAULT GETDATE()
);

CREATE TRIGGER trgLogon
AFTER LOGON ON DATABASE
FOR EACH SESSION
BEGIN
    INSERT INTO UserLogins (UserName)
    VALUES (USER());
END;
```

### Conclusion

Triggers are a powerful feature in SQL that can automate tasks, enforce business rules, and maintain data integrity. By understanding the different types of triggers and their use cases, you can effectively implement triggers in real-world scenarios to enhance the functionality and performance of your database applications. Always consider best practices when using triggers to avoid potential pitfalls, such as performance issues and maintainability challenges.

Citations:
[1] https://solutioncenter.apexsql.com/how-to-create-and-use-dml-triggers-in-sql-server-using-real-world-examples/
[2] https://www.scholarhat.com/tutorial/sqlserver/after-trigger-instead-of-trigger-example
[3] https://www.youtube.com/watch?v=2nQtHZ5VTAM
[4] https://www.red-gate.com/simple-talk/databases/sql-server/database-administration-sql-server/sql-server-triggers-good-scary/
[5] https://www.youtube.com/watch?v=oJl24w8D1gY


# Understanding Functions in SQL

**Definition**: SQL functions are predefined operations that perform calculations, manipulate data, and return results. They are essential for data retrieval, transformation, and analysis in relational databases. Functions can be categorized into two main types: **aggregate functions** and **scalar functions**.

### Types of SQL Functions

1. **Aggregate Functions**: Operate on a set of values and return a single value. Common aggregate functions include:
   - `COUNT()`: Counts the number of rows.
   - `SUM()`: Calculates the total of a numeric column.
   - `AVG()`: Computes the average of a numeric column.
   - `MAX()`: Returns the maximum value in a set.
   - `MIN()`: Returns the minimum value in a set.

2. **Scalar Functions**: Operate on a single value and return a single value. They can be further categorized into:
   - **String Functions**: Manipulate string data (e.g., `UPPER()`, `LOWER()`, `CONCAT()`).
   - **Numeric Functions**: Perform calculations on numeric data (e.g., `ROUND()`, `ABS()`).
   - **Date and Time Functions**: Manipulate date and time values (e.g., `NOW()`, `DATEDIFF()`).

### Use Cases of SQL Functions

1. **Data Aggregation**: Summarizing data for reporting purposes.
2. **Data Transformation**: Modifying data formats or values for consistency.
3. **Data Validation**: Ensuring data meets specific criteria before processing.
4. **Conditional Logic**: Implementing business rules through conditional expressions.

### Real-World Applications

1. **Sales Reporting**: Using aggregate functions to summarize sales data.
2. **User Management**: Using string functions to format user names and emails.
3. **Date Calculations**: Using date functions to calculate age or tenure.

### Example Queries

#### Aggregate Functions

**Example 1**: Using `COUNT()` to determine the number of products in a table.

```sql
SELECT COUNT(*) AS TotalProducts FROM Products;
```

**Example 2**: Using `SUM()` to calculate total sales.

```sql
SELECT SUM(SaleAmount) AS TotalSales FROM Sales;
```

**Example 3**: Using `AVG()` to find the average price of products.

```sql
SELECT AVG(Price) AS AveragePrice FROM Products;
```

#### Scalar Functions

**String Functions**:

**Example 4**: Using `UPPER()` and `LOWER()` to change the case of strings.

```sql
SELECT UPPER(ProductName) AS UppercaseName, LOWER(ProductName) AS LowercaseName FROM Products;
```

**Example 5**: Using `CONCAT()` to combine first and last names.

```sql
SELECT CONCAT(FirstName, ' ', LastName) AS FullName FROM Customers;
```

**Numeric Functions**:

**Example 6**: Using `ROUND()` to round a price to two decimal places.

```sql
SELECT ROUND(Price, 2) AS RoundedPrice FROM Products;
```

**Date Functions**:

**Example 7**: Using `DATEDIFF()` to calculate the number of days between two dates.

```sql
SELECT DATEDIFF(NOW(), BirthDate) AS DaysSinceBirth FROM Customers;
```

### Best Practices for Using SQL Functions

1. **Use Functions Appropriately**: Choose the right type of function based on the requirement (aggregate vs. scalar).
2. **Optimize Performance**: Be mindful of performance when using functions on large datasets, as they can slow down queries.
3. **Test for Accuracy**: Ensure that the results returned by functions are accurate and meet business requirements.
4. **Document Usage**: Provide comments in your SQL code to explain the purpose of complex functions for future reference.
5. **Avoid Overuse**: While functions are powerful, overusing them in complex queries can lead to decreased readability and maintainability.


# Views, Stored Procedures, Triggers and Functions


Here’s a comprehensive table that illustrates the differences between Views, Stored Procedures, Triggers, and Functions in SQL, including their use cases, how and when to use them, and examples for each type.

| Feature/Aspect       | Views                                               | Stored Procedures                                   | Triggers                                             | Functions                                           |
|----------------------|-----------------------------------------------------|----------------------------------------------------|-----------------------------------------------------|----------------------------------------------------|
| **Definition**       | Virtual tables created from SQL queries.           | Precompiled SQL code that can perform actions.     | Code that automatically executes in response to events. | Reusable SQL code that returns a single value or table. |
| **Use Case**         | Simplifying complex queries, restricting data access. | Performing complex operations, batch processing, and encapsulating business logic. | Auditing changes, enforcing business rules, cascading actions. | Data transformation, calculations, and data validation. |
| **How**              | Created using `CREATE VIEW` statement.             | Created using `CREATE PROCEDURE` statement.       | Created using `CREATE TRIGGER` statement.           | Created using `CREATE FUNCTION` statement.         |
| **When**             | When you need a simplified representation of data. | When you need to encapsulate complex logic or operations. | When you need to automate actions based on data changes. | When you need to perform calculations or transformations. |
| **Execution**        | Executed when queried.                              | Executed explicitly using `CALL` or `EXEC`.       | Automatically executed when the triggering event occurs. | Executed within SQL statements, often in `SELECT`. |
| **Parameters**       | No parameters.                                      | Can accept input and output parameters.            | No parameters.                                       | Can accept parameters but cannot modify data.      |
| **Return Type**      | Returns a result set.                              | Can return multiple result sets or no result.      | Does not return a value.                             | Returns a single value or table.                    |
| **Performance**      | Can improve performance for complex queries.       | Generally faster due to precompilation.            | Can impact performance if not used judiciously.     | Can impact performance if used on large datasets.   |
| **Example**          | ```sql CREATE VIEW ActiveCustomers AS SELECT * FROM Customers WHERE IsActive = 1; ``` | ```sql CREATE PROCEDURE AddCustomer (IN Name VARCHAR(50), IN Email VARCHAR(50)) BEGIN INSERT INTO Customers (Name, Email) VALUES (Name, Email); END; ``` | ```sql CREATE TRIGGER LogCustomerChanges AFTER UPDATE ON Customers FOR EACH ROW BEGIN INSERT INTO ChangeLog (CustomerID, ChangeDate) VALUES (NEW.CustomerID, NOW()); END; ``` | ```sql CREATE FUNCTION CalculateDiscount (Price DECIMAL) RETURNS DECIMAL BEGIN RETURN Price * 0.10; END; ``` |

### Detailed Explanation of Each Feature

#### Views
- **Definition**: Views are virtual tables created based on the result of a `SELECT` query. They do not store data themselves but provide a way to simplify complex queries or restrict access to certain data.
- **Use Case**: For example, a view can be created to show only active customers, making it easier for users to query relevant data without needing to filter it each time.
- **Example**: 
  ```sql
  CREATE VIEW ActiveCustomers AS 
  SELECT * FROM Customers WHERE IsActive = 1;
  ```

#### Stored Procedures
- **Definition**: Stored procedures are precompiled collections of SQL statements that can be executed as a single unit. They can accept parameters and return results.
- **Use Case**: Useful for encapsulating complex business logic, such as adding a new customer while checking for existing entries.
- **Example**:
  ```sql
  CREATE PROCEDURE AddCustomer (IN Name VARCHAR(50), IN Email VARCHAR(50))
  BEGIN
      INSERT INTO Customers (Name, Email) VALUES (Name, Email);
  END;
  ```

#### Triggers
- **Definition**: Triggers are special types of stored procedures that automatically execute in response to certain events on a table, such as `INSERT`, `UPDATE`, or `DELETE`.
- **Use Case**: Ideal for auditing changes to critical data or enforcing business rules, such as preventing deletion of records that are referenced elsewhere.
- **Example**:
  ```sql
  CREATE TRIGGER LogCustomerChanges 
  AFTER UPDATE ON Customers 
  FOR EACH ROW 
  BEGIN 
      INSERT INTO ChangeLog (CustomerID, ChangeDate) 
      VALUES (NEW.CustomerID, NOW()); 
  END;
  ```

#### Functions
- **Definition**: Functions are reusable SQL code that can take parameters and return a single value or a table. They are often used for calculations or data transformations.
- **Use Case**: Useful for performing calculations, such as calculating discounts or formatting data.
- **Example**:
  ```sql
  CREATE FUNCTION CalculateDiscount (Price DECIMAL) 
  RETURNS DECIMAL 
  BEGIN 
      RETURN Price * 0.10; 
  END;
  ```

### Conclusion

This table and accompanying explanations provide a clear overview of Views, Stored Procedures, Triggers, and Functions in SQL. By understanding the differences and use cases for each, you can effectively leverage these tools to enhance the functionality and performance of your database applications.

Citations:
[1] https://www.slideshare.net/slideshow/views-triggers-functions-stored-procedures-indexing-and-joins/21228558
[2] https://www.usna.edu/Users/cs/pfau/IT360/calendar.php?event=16&type=class
[3] https://www.scholarhat.com/tutorial/sqlserver/difference-between-stored-procedure-and-function-in-sql-server
[4] https://eecs.csuohio.edu/~sschung/CIS408/ViewSPTriggerMySQL.pdf
[5] https://autosyncdb.com/en/docs/compare-and-synchronize-stored-procedures,-functions,-triggers,-and-user-types-of-sql-server-databases/
# Reference

![[Practical 3 ITM.pdf]]


![[Practical 4 ITM.pdf]]


![[SQL Triggers.pdf]]