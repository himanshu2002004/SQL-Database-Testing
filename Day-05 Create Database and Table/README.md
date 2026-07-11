# Day 04 - Create Database and Insert Data into Tables

## 📌 Introduction

Before performing any SQL queries or database testing, we need a database that contains tables and data. Creating databases, designing tables, and inserting records are the first steps in SQL development and database testing.

In this chapter, we'll learn how to create a database, create tables, insert records, and verify the inserted data.

---

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

# Key Takeaways

- CREATE DATABASE creates a new database.
- USE selects the active database.
- CREATE TABLE creates tables.
- INSERT INTO adds records.
- SELECT verifies inserted data.
- Database testing ensures data integrity and accuracy.
