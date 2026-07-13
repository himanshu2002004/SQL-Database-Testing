# Day 07 – SELECT Statement in SQL

The **SELECT** statement is one of the most frequently used SQL commands. 

It is used to retrieve data from one or more tables in a database.

---

# Learning Objectives

- Understand the SELECT statement
- Retrieve all records from a table
- Retrieve specific columns
- Remove duplicate records using DISTINCT
- Retrieve limited records using TOP and LIMIT
- Rename columns using Alias
- Verify data during Database Testing

---

### Syntax

```sql
SELECT column_name
FROM table_name;
```

---

# Sample Table

**Employees**

| EmployeeID | FirstName | LastName | Department | Salary | City |
|------------|-----------|----------|------------|---------|------|
|101|Rahul|Sharma|HR|35000|Bangalore|
|102|Aisha|Khan|Testing|45000|Mumbai|
|103|John|David|Developer|60000|Pune|
|104|Sneha|Patil|QA|48000|Bangalore|
|105|Arjun|Kumar|Developer|65000|Hyderabad|

---

# SELECT *

The `*` symbol retrieves **all columns** from a table.

### Syntax

```sql
SELECT *
FROM Employees;
```

### Output

Returns every column and every row from the Employees table.

| EmployeeID | FirstName | LastName | Department | Salary | City |
|------------|-----------|----------|------------|---------|------|
|101|Rahul|Sharma|HR|35000|Bangalore|
|102|Aisha|Khan|Testing|45000|Mumbai|
|103|John|David|Developer|60000|Pune|
|104|Sneha|Patil|QA|48000|Bangalore|
|105|Arjun|Kumar|Developer|65000|Hyderabad|

---

# SELECT Specific Columns

Retrieve only the required columns instead of all columns.

### Syntax

```sql
SELECT FirstName, Department
FROM Employees;
```

### Output

| FirstName | Department |
|------------|------------|
|Rahul|HR|
|Aisha|Testing|
|John|Developer|
|Sneha|QA|
|Arjun|Developer|

---

# DISTINCT

Sometimes a column contains duplicate values.

The **DISTINCT** keyword returns only unique values.

### Syntax

```sql
SELECT DISTINCT Department
FROM Employees;
```

### Output

| Department |
|------------|
|HR|
|Testing|
|Developer|
|QA|

Without DISTINCT

```sql
SELECT Department
FROM Employees;
```

Output

| Department |
|------------|
|HR|
|Testing|
|Developer|
|QA|
|Developer|

---
# TOP

The **TOP** clause returns only the specified number of records.

> Used mainly in **SQL Server**.

### Syntax

```sql
SELECT TOP 3 *
FROM Employees;
```

### Output

Returns the first three rows.

| EmployeeID | FirstName | Department |
|------------|-----------|------------|
|101|Rahul|HR|
|102|Aisha|Testing|
|103|John|Developer|

---

# LIMIT

The **LIMIT** clause is used to restrict the number of rows returned.

> Used in **MySQL** and **PostgreSQL**.

### Syntax

```sql
SELECT *
FROM Employees
LIMIT 3;
```

### Output

Returns only the first three records.

---

# Alias (AS)

An Alias gives a temporary name to a column.

### Syntax

```sql
SELECT FirstName AS Employee_Name,
Department AS Team
FROM Employees;
```

### Output

| Employee_Name | Team |
|---------------|------|
|Rahul|HR|
|Aisha|Testing|
|John|Developer|

---

# Examples

## Example 1

Display all employee records.

```sql
SELECT *
FROM Employees;
```

---

## Example 2

Display Employee Name and Salary.

```sql
SELECT FirstName, Salary
FROM Employees;
```

---

## Example 3

Display unique cities.

```sql
SELECT DISTINCT City
FROM Employees;
```

---

## Example 4

Display the first five employees.

(SQL Server)

```sql
SELECT TOP 5 *
FROM Employees;
```

(MySQL)

```sql
SELECT *
FROM Employees
LIMIT 5;
```

---

## Example 5

Rename column names.

```sql
SELECT
FirstName AS Name,
Salary AS Employee_Salary
FROM Employees;
```
---

# Best Practices

- Retrieve only the required columns.
- Avoid using `SELECT *` in production queries.
- Use DISTINCT only when necessary.
- Use aliases to improve readability.
- Verify retrieved data against application requirements.
- Use LIMIT or TOP while testing large datasets.

---

# Key Points

- SELECT retrieves data from a table.
- SELECT * retrieves all columns.
- SELECT Column retrieves only selected columns.
- DISTINCT removes duplicate values.
- TOP returns limited records in SQL Server.
- LIMIT returns limited records in MySQL and PostgreSQL.
- Alias provides temporary names to columns.

---

# Interview Questions

### Q1. What is the purpose of the SELECT statement?

---

### Q2. What does SELECT * do?

---

### Q3. What is the difference between SELECT * and SELECT column_name?

---

### Q4. Why is DISTINCT used?

---

### Q5. What is the difference between TOP and LIMIT?

---

### Q6. What is an Alias in SQL?

---

### Q7. Why should testers avoid using SELECT * in production?

---
