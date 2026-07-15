# Day 07 – Aggregate Functions in SQL

Aggregate Functions are built-in SQL functions used to perform calculations on multiple rows of data and return a **single summarized result**.

These functions are widely used in **Database Testing** to validate business data, generate reports, verify calculations, and ensure data accuracy.

For example:

- Count total users registered.
- Calculate total sales.
- Find average employee salary.
- Determine highest and lowest product prices.

---

# Learning Objectives

- Understand Aggregate Functions
- Learn COUNT()
- Learn SUM()
- Learn AVG()
- Learn MIN()
- Learn MAX()
- Understand GROUP BY
- Learn HAVING clause
- Apply Aggregate Functions in Database Testing

---

# Sample Table

```sql
CREATE TABLE Employees
(
    EmployeeID INT PRIMARY KEY,
    EmployeeName VARCHAR(50),
    Department VARCHAR(30),
    Salary DECIMAL(10,2),
    City VARCHAR(30)
);
```

### Sample Data

| EmployeeID | EmployeeName | Department | Salary | City |
|------------|--------------|------------|---------|------|
|101|Rahul|HR|35000|Bangalore|
|102|Aisha|QA|45000|Pune|
|103|John|Developer|60000|Mumbai|
|104|Sneha|QA|42000|Pune|
|105|Arjun|Support|28000|Hyderabad|

---

# Aggregate Functions

Aggregate Functions perform calculations on a group of rows and return a **single value**.

Common Aggregate Functions are:

- COUNT()
- SUM()
- AVG()
- MIN()
- MAX()

---

# 🔹 COUNT()

The **COUNT()** function returns the total number of records.

## Syntax

```sql
SELECT COUNT(*)
FROM Employees;
```

### Output

| COUNT(*) |
|-----------|
|5|

---

## Count Employees in QA Department

```sql
SELECT COUNT(*)
FROM Employees
WHERE Department='QA';
```

### Output

| COUNT(*) |
|-----------|
|2|

---

# 🔹 SUM()

The **SUM()** function calculates the total of a numeric column.

## Syntax

```sql
SELECT SUM(Salary)
FROM Employees;
```

### Output

| SUM(Salary) |
|-------------|
|210000|

---

## Calculate Total Salary of QA Employees

```sql
SELECT SUM(Salary)
FROM Employees
WHERE Department='QA';
```

### Output

| SUM(Salary) |
|-------------|
|87000|

---

# 🔹 AVG()

The **AVG()** function calculates the average value.

## Syntax

```sql
SELECT AVG(Salary)
FROM Employees;
```

### Output

| AVG(Salary) |
|-------------|

---

## Average Salary of QA Employees

```sql
SELECT AVG(Salary)
FROM Employees
WHERE Department='QA';
```

### Output

| AVG(Salary) |
|-------------|
|43500|

---

# 🔹 MIN()

The **MIN()** function returns the smallest value.

## Syntax

```sql
SELECT MIN(Salary)
FROM Employees;
```

### Output

| MIN(Salary) |
|-------------|
|28000|

---

# 🔹 MAX()

The **MAX()** function returns the largest value.

## Syntax

```sql
SELECT MAX(Salary)
FROM Employees;
```

### Output

| MAX(Salary) |
|-------------|
|60000|

---

# 🔹 GROUP BY

The **GROUP BY** clause groups rows that have the same values into summary rows.

It is commonly used with Aggregate Functions.

## Syntax

```sql
SELECT Department,
COUNT(*)
FROM Employees
GROUP BY Department;
```

### Output

| Department | COUNT |
|------------|-------|
|Developer|1|
|HR|1|
|QA|2|
|Support|1|

---

## Total Salary by Department

```sql
SELECT Department,
SUM(Salary)
FROM Employees
GROUP BY Department;
```

### Output

| Department | Total Salary |
|------------|--------------|
|Developer|60000|
|HR|35000|
|QA|87000|
|Support|28000|

---

## Average Salary by Department

```sql
SELECT Department,
AVG(Salary)
FROM Employees
GROUP BY Department;
```

---

# 🔹 HAVING

The **HAVING** clause filters grouped records.

Unlike **WHERE**, which filters individual rows before grouping, **HAVING** filters groups after aggregation.

## Syntax

```sql
SELECT Department,
COUNT(*)
FROM Employees
GROUP BY Department
HAVING COUNT(*) > 1;
```

### Output

| Department | COUNT |
|------------|-------|
|QA|2|

---

## Departments with Average Salary Greater than 40000

```sql
SELECT Department,
AVG(Salary)
FROM Employees
GROUP BY Department
HAVING AVG(Salary) > 40000;
```

### Output

| Department | AVG(Salary) |
|------------|-------------|
|Developer|60000|
|QA|43500|

---

# Best Practices

- Use Aggregate Functions only on numeric data where applicable.
- Combine GROUP BY with Aggregate Functions for meaningful reports.
- Use HAVING to filter grouped results.
- Use WHERE before GROUP BY to reduce unnecessary records.
- Always validate aggregate results against expected business values.

---

# ⚠ Common Mistakes

### Using WHERE with Aggregate Functions

❌ Incorrect

```sql
SELECT Department,
COUNT(*)
FROM Employees
WHERE COUNT(*) > 1;
```

✅ Correct

```sql
SELECT Department,
COUNT(*)
FROM Employees
GROUP BY Department
HAVING COUNT(*) > 1;
```

---

### Forgetting GROUP BY

❌ Incorrect

```sql
SELECT Department,
COUNT(*)
FROM Employees;
```

This causes an error because Department is not grouped.

---

# Difference Between WHERE and HAVING

| WHERE | HAVING |
|--------|---------|
| Filters rows | Filters groups |
| Used before GROUP BY | Used after GROUP BY |
| Cannot use Aggregate Functions directly | Used with Aggregate Functions |

---

# Key Points

- COUNT() counts records.
- SUM() calculates the total.
- AVG() calculates the average.
- MIN() returns the smallest value.
- MAX() returns the largest value.
- GROUP BY groups similar records.
- HAVING filters grouped records.
- Aggregate Functions are heavily used in reporting and database testing.

---

# Interview Questions

### Q1. What are Aggregate Functions?

---

### Q2. Name five Aggregate Functions.

---

### Q3. What is the difference between COUNT(*) and COUNT(column_name)?

---

### Q4. What is GROUP BY?

---

### Q5. What is HAVING?

---

### Q6. Difference between WHERE and HAVING?

---

### Q7. Can Aggregate Functions be used without GROUP BY?

---

|42000|

---
