## Introduction

SQL Operators are special symbols or keywords used to perform operations on data stored in a database. They help filter records, compare values, perform calculations, and combine multiple conditions in SQL queries.

In Database Testing, SQL operators are frequently used to validate backend data, verify business rules, and retrieve specific records from the database.

---

# Learning Objectives

- Understand SQL Operators
- Learn Arithmetic Operators
- Learn Comparison Operators
- Learn Logical Operators
- Learn IN Operator
- Learn BETWEEN Operator
- Learn LIKE Operator
- Learn IS NULL and IS NOT NULL
- Apply SQL Operators in Database Testing

---

# Sample Table

```sql
CREATE TABLE Employees
(
    EmployeeID INT PRIMARY KEY,
    EmployeeName VARCHAR(50),
    Department VARCHAR(30),
    Salary DECIMAL(10,2),
    Age INT,
    City VARCHAR(30),
    ManagerID INT
);
```

### Sample Data

| EmployeeID | EmployeeName | Department | Salary | Age | City | ManagerID |
|------------|--------------|------------|---------|-----|------|-----------|
|101|Rahul|HR|35000|25|Bangalore|201|
|102|Aisha|QA|45000|28|Pune|202|
|103|John|Developer|60000|30|Mumbai|203|
|104|Sneha|QA|42000|27|Pune|NULL|
|105|Arjun|Support|28000|24|Hyderabad|NULL|

---

# Types of SQL Operators

SQL Operators are classified into:

- Arithmetic Operators
- Comparison Operators
- Logical Operators
- Special Operators

---

# 🔹 Arithmetic Operators

Arithmetic operators perform mathematical calculations.

| Operator | Description |
|----------|-------------|
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| / | Division |
| % | Modulus (Remainder) |

### Example

```sql
SELECT Salary + 5000 AS UpdatedSalary
FROM Employees;
```

---

```sql
SELECT Salary * 12 AS AnnualSalary
FROM Employees;
```

---

# 🔹 Comparison Operators

Comparison operators compare two values.

| Operator | Description |
|----------|-------------|
| = | Equal To |
| != or <> | Not Equal To |
| > | Greater Than |
| < | Less Than |
| >= | Greater Than or Equal To |
| <= | Less Than or Equal To |

### Example

Employees earning more than ₹40,000.

```sql
SELECT *
FROM Employees
WHERE Salary > 40000;
```

---

Employees whose department is QA.

```sql
SELECT *
FROM Employees
WHERE Department = 'QA';
```

---

Employees whose age is not 25.

```sql
SELECT *
FROM Employees
WHERE Age <> 25;
```

---

# 🔹 Logical Operators

Logical operators combine multiple conditions.

## AND

Returns records only if all conditions are true.

```sql
SELECT *
FROM Employees
WHERE Department='QA'
AND Salary>40000;
```

---

## OR

Returns records if at least one condition is true.

```sql
SELECT *
FROM Employees
WHERE Department='HR'
OR Department='Support';
```

---

## NOT

Excludes records matching a condition.

```sql
SELECT *
FROM Employees
WHERE NOT Department='QA';
```

---

# 🔹 IN Operator

The IN operator checks multiple values.

Instead of writing several OR conditions, IN makes the query cleaner.

```sql
SELECT *
FROM Employees
WHERE Department IN ('QA','HR');
```

---

# 🔹 BETWEEN Operator

The BETWEEN operator retrieves values within a range.

```sql
SELECT *
FROM Employees
WHERE Salary BETWEEN 30000 AND 50000;
```

---

Retrieve employees between age 25 and 30.

```sql
SELECT *
FROM Employees
WHERE Age BETWEEN 25 AND 30;
```

---

# 🔹 LIKE Operator

The LIKE operator searches for patterns.

## Starts with

```sql
SELECT *
FROM Employees
WHERE EmployeeName LIKE 'A%';
```

---

## Ends with

```sql
SELECT *
FROM Employees
WHERE EmployeeName LIKE '%a';
```

---

## Contains

```sql
SELECT *
FROM Employees
WHERE EmployeeName LIKE '%hn%';
```

---

# Wildcards

| Wildcard | Meaning |
|----------|---------|
| % | Zero or more characters |
| _ | Exactly one character |

Example

```sql
SELECT *
FROM Employees
WHERE EmployeeName LIKE '_a%';
```

---

# 🔹 IS NULL

Returns records where the value is NULL.

```sql
SELECT *
FROM Employees
WHERE ManagerID IS NULL;
```

---

# 🔹 IS NOT NULL

Returns records where values exist.

```sql
SELECT *
FROM Employees
WHERE ManagerID IS NOT NULL;
```

---

# 🧪 Real-Time Database Testing Scenarios

## Scenario 1

Verify customers from Bangalore.

```sql
SELECT *
FROM Customers
WHERE City='Bangalore';
```

---

## Scenario 2

Verify products priced above ₹1,000.

```sql
SELECT *
FROM Products
WHERE Price>1000;
```

---

## Scenario 3

Verify users aged between 18 and 60.

```sql
SELECT *
FROM Users
WHERE Age BETWEEN 18 AND 60;
```

---

## Scenario 4

Verify orders in Pending or Processing status.

```sql
SELECT *
FROM Orders
WHERE Status IN ('Pending','Processing');
```

---

## Scenario 5

Verify customers whose names start with "S".

```sql
SELECT *
FROM Customers
WHERE CustomerName LIKE 'S%';
```
---

## Scenario 6

Verify employees without managers.

```sql
SELECT *
FROM Employees
WHERE ManagerID IS NULL;
```

---

## Scenario 7

Verify employees working in QA with salary greater than ₹40,000.

```sql
SELECT *
FROM Employees
WHERE Department='QA'
AND Salary>40000;
```

---

# Best Practices

- Use operators to filter only required records.
- Use IN instead of multiple OR conditions.
- Use BETWEEN for ranges.
- Use LIKE for text searches.
- Never compare NULL using '='.
- Use IS NULL or IS NOT NULL for NULL values.
- Combine operators carefully to avoid incorrect results.

---

# ⚠ Common Mistakes

### Comparing NULL with '='

❌ Incorrect

```sql
SELECT *
FROM Employees
WHERE ManagerID = NULL;
```

✅ Correct

```sql
SELECT *
FROM Employees
WHERE ManagerID IS NULL;
```

---

### Using Multiple OR Instead of IN

❌

```sql
WHERE Department='QA'
OR Department='HR'
OR Department='Support'
```

✅

```sql
WHERE Department IN ('QA','HR','Support')
```

---

# Key Points

- Arithmetic Operators perform calculations.
- Comparison Operators compare values.
- Logical Operators combine conditions.
- IN simplifies multiple comparisons.
- BETWEEN retrieves values within a range.
- LIKE performs pattern matching.
- IS NULL checks missing values.
- IS NOT NULL checks existing values.

---

# Interview Questions

### Q1. What are SQL Operators?

---

### Q2. Name the types of SQL Operators.

---

### Q3. What is the difference between = and <>?

---

### Q4. Difference between AND and OR?

---

### Q5. What is the purpose of the IN operator?

---

### Q6. What is BETWEEN used for?

---

### Q7. What are the wildcard characters used with LIKE?

---

### Q8. Why do we use IS NULL instead of = NULL?

---
