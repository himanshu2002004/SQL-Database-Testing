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

# Clause in SQL

A **clause** is a part of an SQL statement that performs a specific task. Multiple clauses are combined to form a complete SQL query.

Think of a clause as a **building block** of an SQL statement. Each clause has a specific purpose, such as selecting data, filtering records, grouping rows, or sorting results.

### Example SQL Query

```sql
SELECT Name, Salary
FROM Employee
WHERE Department = 'IT'
ORDER BY Salary DESC;
```

This query consists of four clauses:

| Clause | Purpose |
|---------|---------|
| **SELECT** | Specifies the column(s) to retrieve from the table. |
| **FROM** | Specifies the table from which the data will be retrieved. |
| **WHERE** | Filters the rows based on a condition. |
| **ORDER BY** | Sorts the result in ascending (`ASC`) or descending (`DESC`) order. |

---

# SQL Query Execution Order

When writing a SQL query, we usually type the clauses in the following order:

```sql
SELECT column_name
FROM table_name
WHERE condition
GROUP BY column_name
HAVING condition
ORDER BY column_name;
```

However, SQL does **not** execute the query in the same order. The database processes the clauses in the following logical execution order:

| Execution Order | Clause | Purpose |
|----------------:|--------|---------|
| 1 | FROM | Identifies the table(s) from which data will be retrieved. |
| 2 | WHERE | Filters rows based on the specified condition. |
| 3 | GROUP BY | Groups rows that have the same values into summary rows. |
| 4 | HAVING | Filters the grouped data based on aggregate conditions. |
| 5 | SELECT | Chooses the columns or expressions to return in the result set. |
| 6 | DISTINCT | Removes duplicate rows from the selected result (if used). |
| 7 | ORDER BY | Sorts the final result set in ascending or descending order. |
| 8 | LIMIT / TOP / FETCH | Restricts the number of rows returned (syntax depends on the database). |

---

#  Sample Employee Table

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
