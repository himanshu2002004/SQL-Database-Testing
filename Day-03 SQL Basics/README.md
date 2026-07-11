# Day 03 - SQL Basics

# What is SQL?

**SQL (Structured Query Language)** is a standard programming language used to communicate with relational databases.

Using SQL, we can:

- Retrieve data
- Insert new records
- Update existing records
- Delete records
- Create database objects
- Manage database permissions
- Control transactions

SQL is supported by popular databases like:

- MySQL
- Microsoft SQL Server
- Oracle
- PostgreSQL
- SQLite
- MariaDB

---

# Why Should Testers Learn SQL?

Software testers frequently verify whether the data displayed in the application is correctly stored in the database.

Example:

User registers on a website.

  ↓

Application stores user details.

  ↓

Tester executes SQL queries.

  ↓

Tester verifies whether the stored data matches the application.

Database Testing becomes much easier with SQL knowledge.

---

# Categories of SQL Commands

SQL commands are divided into five categories.

## 1️. DDL (Data Definition Language)

Used to define or modify database objects.

Commands:

- CREATE
- ALTER
- DROP
- TRUNCATE
- RENAME

Example:

```sql
CREATE TABLE Employee (
    EmpID INT,
    Name VARCHAR(100)
);
```

---

## 2️. DML (Data Manipulation Language)

Used to manipulate data inside tables.

Commands:

- INSERT
- UPDATE
- DELETE

Example:

```sql
INSERT INTO Employee
VALUES (101,'John');
```

---

## 3️. DQL (Data Query Language)

Used to retrieve data.

Command:

- SELECT

Example:

```sql
SELECT * FROM Employee;
```

---

## 4️. DCL (Data Control Language)

Used to control database permissions.

Commands:

- GRANT
- REVOKE

Example:

```sql
GRANT SELECT ON Employee TO User1;
```

---

## 5️. TCL (Transaction Control Language)

Used to manage database transactions.

Commands:

- COMMIT
- ROLLBACK
- SAVEPOINT

Example:

```sql
COMMIT;
```

---

# SQL Command Categories

| Category | Purpose | Commands |
|----------|----------|----------|
| DDL | Defines database structure | CREATE, ALTER, DROP, TRUNCATE |
| DML | Manipulates table data | INSERT, UPDATE, DELETE |
| DQL | Retrieves data | SELECT |
| DCL | Controls user permissions | GRANT, REVOKE |
| TCL | Manages transactions | COMMIT, ROLLBACK, SAVEPOINT |

---

# Basic SQL Syntax

General syntax:

```sql
SELECT column_name
FROM table_name
WHERE condition;
```

Example:

```sql
SELECT Name
FROM Employee
WHERE EmpID = 101;
```

---

# Common SQL Keywords

Some commonly used SQL keywords are:

- SELECT
- FROM
- WHERE
- DISTINCT
- ORDER BY
- GROUP BY
- HAVING
- INSERT
- UPDATE
- DELETE
- CREATE
- DROP
- ALTER
- JOIN
- LIMIT
- TOP

---

# 💻 Sample Employee Table

| EmpID | Name | Department | Salary |
|--------|------|------------|--------|
| 101 | John | HR | 40000 |
| 102 | Alice | IT | 60000 |
| 103 | David | Finance | 55000 |
| 104 | Emma | Testing | 50000 |

---

# Advantages of SQL

- Easy to learn
- Standard language for relational databases
- Supports CRUD operations
- Helps validate backend data
- Used in almost every software application
- Essential skill for Manual and Automation Testers
- Improves database testing efficiency

---

# Key Takeaways

- SQL stands for Structured Query Language.
- SQL is used to communicate with relational databases.
- SQL has five main categories: DDL, DML, DQL, DCL, and TCL.
- The SELECT statement is used to retrieve data.
- SQL is a must-have skill for software testers to perform backend validation.

---

# Interview Questions

### Q1. What is SQL?

---

### Q2. What are the different categories of SQL?

---

### Q3. Which SQL command is most frequently used?

---

### Q4. What is the difference between DELETE and TRUNCATE?

---

### Q5. Why is SQL important for Software Testers?

---
