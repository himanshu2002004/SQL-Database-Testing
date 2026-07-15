# Day 06 – ORDER BY and Sorting in SQL

When retrieving data from a database, the records are not always displayed in a meaningful order. The **ORDER BY** clause is used to sort the result set in ascending or descending order based on one or more columns.

In Database Testing, sorting is commonly verified to ensure that records displayed in an application (such as product lists, employee records, or reports) are ordered correctly according to business requirements.

---

# Learning Objectives

- Understand the ORDER BY clause
- Learn Ascending (ASC) sorting
- Learn Descending (DESC) sorting
- Sort data using multiple columns
- Understand NULL value sorting
- Apply ORDER BY in real-world database testing

---

# ORDER BY Clause

The **ORDER BY** clause sorts the records returned by a SQL query.

## Syntax

```sql
SELECT column_name
FROM table_name
ORDER BY column_name;
```

By default, records are sorted in **Ascending (ASC)** order.

---

# Sample Table

```sql
CREATE TABLE Employees
(
    EmployeeID INT PRIMARY KEY,
    EmployeeName VARCHAR(50),
    Department VARCHAR(30),
    Salary DECIMAL(10,2),
    City VARCHAR(30),
    ManagerID INT
);
```

### Sample Data

| EmployeeID | EmployeeName | Department | Salary | City | ManagerID |
|------------|--------------|------------|---------|------|-----------|
|101|Rahul|HR|35000|Bangalore|201|
|102|Aisha|QA|45000|Pune|202|
|103|John|Developer|60000|Mumbai|203|
|104|Sneha|QA|42000|Pune|NULL|
|105|Arjun|Support|28000|Hyderabad|NULL|

---

# 🔹 ASC (Ascending Order)

The **ASC** keyword sorts records in ascending order.

- Numbers → Smallest to Largest
- Text → A to Z
- Dates → Oldest to Newest

## Syntax

```sql
SELECT *
FROM Employees
ORDER BY Salary ASC;
```

### Output

| EmployeeName | Salary |
|--------------|--------|
|Arjun|28000|
|Rahul|35000|
|Sneha|42000|
|Aisha|45000|
|John|60000|

> **Note:** ASC is the default sorting order. You can omit it if you want ascending order.

Example:

```sql
SELECT *
FROM Employees
ORDER BY Salary;
```

---

# 🔹 DESC (Descending Order)

The **DESC** keyword sorts records in descending order.

- Numbers → Largest to Smallest
- Text → Z to A
- Dates → Newest to Oldest

## Syntax

```sql
SELECT *
FROM Employees
ORDER BY Salary DESC;
```

### Output

| EmployeeName | Salary |
|--------------|--------|
|John|60000|
|Aisha|45000|
|Sneha|42000|
|Rahul|35000|
|Arjun|28000|

---

# 🔹 ORDER BY Multiple Columns

You can sort records using more than one column.

The second column is used when values in the first column are the same.

## Syntax

```sql
SELECT *
FROM Employees
ORDER BY Department ASC, Salary DESC;
```

### Output

| EmployeeName | Department | Salary |
|--------------|------------|--------|
|John|Developer|60000|
|Rahul|HR|35000|
|Aisha|QA|45000|
|Sneha|QA|42000|
|Arjun|Support|28000|

In this example:

- First sorted by **Department (A-Z)**
- Then sorted by **Salary (Highest to Lowest)** within each department

---

# 🔹 NULL Sorting

Some columns may contain **NULL** values.

Different databases handle NULL values differently.

Example:

```sql
SELECT *
FROM Employees
ORDER BY ManagerID;
```

Possible Output

| EmployeeName | ManagerID |
|--------------|-----------|
|Sneha|NULL|
|Arjun|NULL|
|Rahul|201|
|Aisha|202|
|John|203|

Some databases display NULL values first, while others display them last.

---

# Sorting NULL Values Explicitly

## NULLS FIRST

```sql
SELECT *
FROM Employees
ORDER BY ManagerID NULLS FIRST;
```

---

## NULLS LAST

```sql
SELECT *
FROM Employees
ORDER BY ManagerID NULLS LAST;
```

> **Note:** `NULLS FIRST` and `NULLS LAST` are supported in databases like PostgreSQL and Oracle. MySQL and SQL Server handle NULL sorting differently.

---

# Best Practices

- Always use ORDER BY when the display order matters.
- Specify ASC or DESC for better readability.
- Use multiple columns when one column is insufficient.
- Understand how your database handles NULL values.
- Verify sorting in both the database and application UI.

---

# ⚠ Common Mistakes

### Forgetting DESC

```sql
SELECT *
FROM Employees
ORDER BY Salary;
```

This sorts in ascending order by default.

---

### Incorrect Column Name

```sql
SELECT *
FROM Employees
ORDER BY Salaries;
```

**Error:** Column does not exist.

---

### Sorting by Wrong Data Type

Sorting numbers stored as text can produce incorrect results.

Example:

```
100
20
3
```

Instead of:

```
3
20
100
```

Always use the correct numeric data type.

---

# Key Points

- ORDER BY sorts query results.
- ASC sorts data in ascending order.
- DESC sorts data in descending order.
- Multiple columns can be used for sorting.
- NULL values can also be sorted.
- ORDER BY improves readability and reporting.
- Sorting validation is an important part of database testing.


---
