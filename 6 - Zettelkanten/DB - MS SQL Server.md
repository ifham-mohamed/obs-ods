
2024-08-11 12:40

Status:

Tags: #UOM #L2S2-S4 #DB 


# DB - MS SQL Server

- MS SQL Server is a database server
- Product of Microsoft
- Enables user to write queries and other SQL statements and execute them

**Consists of several features. A few are:**
1. Query Analyzer
2. Profiler
3. Service Manager
4. Bulk Copy Program (BCP)

## Profiler

- Monitoring tool
- Used for performance tuning 
- Uses traces –an event monitoring protocol 
- Event may be a query or a transaction like logins etc.

## Service Manager

- Helps us to manage services  
- More than one instance of SQL server can be installed in a machine  
- First Instance is called as default instance  
- Rest of the instances (16 max) are called as named instances  
- Service manager helps in starting or stopping the instances individually

## Instances

- Each instance is hidden from another instance
- Enhances security   
- Every instance has its own set of Users, Admins, Databases, Collations  

**Advantage of having multiple instance is**
- Multi company support (Each company can have its own instance and create databases on the same server, independent on each other)
- Server consolidation (Can host up to 10 server applications on a single machine)

## BCP

- Bulk Copy Program
- A powerful command line utility that enables us to transfer large number of records from a file to database
- Time taken for copying to and from database is very less
- Helps in back up and restoration


## Query Analyzer
 
- Allows us to write queries and SQL statements 
- Checks syntax of the SQL statement written 
- Executes the statements
- Store and reload statements
- Save the results in file
- View reports (either as grid or as a text)




# Reference

![[MSSQL - LAB 1 - Part 1.pdf]]