# Day 05 - Create Database Tables

# What is a Database?

A database is an organized collection of related data that allows users to efficiently store, retrieve, update, and manage information.

### Examples

- Student Management System
- Employee Management System
- Banking System
- Hospital Management System
- E-Commerce Website

---

# CREATE DATABASE Statement

The `CREATE DATABASE` statement is used to create a new database.

## Syntax

```sql
CREATE DATABASE database_name;
```

## Example

```sql
CREATE DATABASE CompanyDB;
```

After executing the command, a new database named **CompanyDB** will be created.

---

# Selecting the Database

Before creating tables, select the database.

## SQL Server

```sql
USE CompanyDB;
```

---

# CREATE TABLE Statement

The `CREATE TABLE` statement is used to create a new table inside a database.

## Syntax

```sql
CREATE TABLE table_name
(
    column_name datatype constraints
);
```

---

# Example: Employee Table

```sql
CREATE TABLE Employee
(
    EmpID INT PRIMARY KEY,
    EmpName VARCHAR(100),
    Department VARCHAR(50),
    Salary DECIMAL(10,2),
    City VARCHAR(50)
);
```

### Output

Employee table created successfully.

---

# Column in a table 

A column represents a specific attribute of the data.

Example:

| EmpID | EmpName | Salary |
|-------|----------|---------|

Each heading is a column.

---

# 16. What is a Row?

A row represents one complete record in a table.

Example:

| EmpID | EmpName | Salary |
|-------|----------|---------|
|101|Rahul|35000|

This entire entry is one row.

---

# Best practices while creating tables

- Use meaningful table names.
- Define appropriate data types.
- Add a Primary Key.
- Use constraints where required.
- Avoid duplicate column names.
- Follow consistent naming conventions.
- Keep the table design normalized when possible.

---

# Difference Between Database and Table

| Database | Table |
|----------|--------|
| Collection of tables | Stores actual data |
| Can contain multiple tables | Exists inside a database |
| Created using `CREATE DATABASE` | Created using `CREATE TABLE` |

---

# Interview Questions


# 1. What is a Database?

---

# 2. What is the SQL command to create a database?

---

# 3. Which command is used to select a database in SQL Server?

---

# 4. What is a Table?

---

# 5. Which SQL command is used to create a table?

---

# 6. What is the difference between a Database and a Table?

---

# 7. Can we create multiple tables inside one database?

---

# 8. What happens if you try to create a database with an existing name?

---

# 9. Can a table exist without a Primary Key?

---

# 10. Which SQL statement is executed first: CREATE DATABASE or CREATE TABLE?

---

# 20. What are the best practices while creating tables?

---
