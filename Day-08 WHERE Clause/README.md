# Day 08 – WHERE Clause in SQL

The **WHERE** clause is one of the most frequently used SQL clauses. 

It is used to filter records based on one or more conditions. 

Instead of retrieving all the data from a table, the WHERE clause allows us to retrieve only the records that satisfy specific criteria.

---

# Learning Objectives

- Understand the WHERE clause
- Use comparison operators with WHERE
- Learn AND, OR, and NOT operators
- Use IN operator
- Filter data using BETWEEN
- Search records using LIKE
- Understand NULL values
- Use IS NULL and IS NOT NULL
- Apply these concepts in Database Testing

---

## Syntax

```sql
SELECT column_name
FROM table_name
WHERE condition;
```

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

Sample Data

| EmployeeID | EmployeeName | Department | Salary | City | ManagerID |
|------------|--------------|------------|---------|------|-----------|
|101|Rahul|HR|35000|Bangalore|201|
|102|Aisha|QA|45000|Pune|202|
|103|John|Developer|60000|Mumbai|203|
|104|Sneha|QA|42000|Pune|NULL|
|105|Arjun|Support|28000|Hyderabad|NULL|

---

# WHERE Clause Example

Retrieve employees working in the QA department.

```sql
SELECT *
FROM Employees
WHERE Department = 'QA';
```

### Output

| EmployeeID | EmployeeName | Department |
|------------|--------------|------------|
|102|Aisha|QA|
|104|Sneha|QA|

---

# AND Operator

The **AND** operator returns records only if **all conditions are true**.

## Syntax

```sql
SELECT *
FROM Employees
WHERE Department = 'QA'
AND City = 'Pune';
```

### Output

| EmployeeName | Department | City |
|--------------|------------|------|
|Aisha|QA|Pune|
|Sneha|QA|Pune|

---

# OR Operator

The **OR** operator returns records if **any one condition is true**.

```sql
SELECT *
FROM Employees
WHERE Department = 'HR'
OR Department = 'Support';
```

### Output

| EmployeeName | Department |
|--------------|------------|
|Rahul|HR|
|Arjun|Support|

---

# NOT Operator

The **NOT** operator excludes records that satisfy the specified condition.

```sql
SELECT *
FROM Employees
WHERE NOT Department = 'QA';
```

### Output

| EmployeeName | Department |
|--------------|------------|
|Rahul|HR|
|John|Developer|
|Arjun|Support|

---

# IN Operator

The **IN** operator allows multiple values in a WHERE clause.

Instead of writing multiple OR conditions, IN makes the query shorter and easier to read.

```sql
SELECT *
FROM Employees
WHERE Department IN ('QA','HR');
```

### Output

| EmployeeName | Department |
|--------------|------------|
|Rahul|HR|
|Aisha|QA|
|Sneha|QA|

---

# BETWEEN Operator

The **BETWEEN** operator filters records within a specified range.

```sql
SELECT *
FROM Employees
WHERE Salary BETWEEN 30000 AND 50000;
```

### Output

| EmployeeName | Salary |
|--------------|--------|
|Rahul|35000|
|Aisha|45000|
|Sneha|42000|

---

# LIKE Operator

The **LIKE** operator is used for pattern matching.

## Starts with "A"

```sql
SELECT *
FROM Employees
WHERE EmployeeName LIKE 'A%';
```

Output

| EmployeeName |
|--------------|
|Aisha|
|Arjun|

---

## Ends with "a"

```sql
SELECT *
FROM Employees
WHERE EmployeeName LIKE '%a';
```

---

## Contains "hn"

```sql
SELECT *
FROM Employees
WHERE EmployeeName LIKE '%hn%';
```

Output

| EmployeeName |
|--------------|
|John|

---

# IS NULL

The **IS NULL** operator retrieves records where a column has no value.

```sql
SELECT *
FROM Employees
WHERE ManagerID IS NULL;
```

### Output

| EmployeeName | ManagerID |
|--------------|-----------|
|Sneha|NULL|
|Arjun|NULL|

---

# IS NOT NULL

The **IS NOT NULL** operator retrieves records that contain values.

```sql
SELECT *
FROM Employees
WHERE ManagerID IS NOT NULL;
```

### Output

| EmployeeName | ManagerID |
|--------------|-----------|
|Rahul|201|
|Aisha|202|
|John|203|

---

# Best Practices

- Always use the WHERE clause to retrieve only required records.
- Use AND when all conditions must be true.
- Use OR when any condition can be true.
- Use IN instead of multiple OR conditions for readability.
- Use BETWEEN for numeric and date ranges.
- Use LIKE for partial text searches.
- Never compare NULL using '='; always use IS NULL or IS NOT NULL.
- Verify query results before performing UPDATE or DELETE operations.

---

# ⚠ Common Mistakes

❌ Using '=' with NULL

```sql
SELECT *
FROM Employees
WHERE ManagerID = NULL;
```

Correct

```sql
SELECT *
FROM Employees
WHERE ManagerID IS NULL;
```

---

❌ Forgetting the WHERE clause in UPDATE or DELETE statements.

Example

```sql
UPDATE Employees
SET Salary=50000;
```

This updates every row in the table.

---

# Key Points

- WHERE filters records based on conditions.
- AND requires all conditions to be true.
- OR requires at least one condition to be true.
- NOT excludes matching records.
- IN checks multiple values.
- BETWEEN filters records within a range.
- LIKE performs pattern matching.
- IS NULL checks for missing values.
- IS NOT NULL checks for existing values.

---

# Interview Questions

### Q1. What is the purpose of the WHERE clause?

---

### Q2. What is the difference between AND and OR?

---

### Q3. Why is the IN operator used?

---

### Q4. What is the BETWEEN operator used for?

---

### Q5. Why can't we use '=' with NULL?

---
