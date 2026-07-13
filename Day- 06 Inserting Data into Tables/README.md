# Day 06 – Inserting Data into Tables (SQL)

After creating a database and tables, the next step is to populate them with data. SQL provides the **INSERT INTO** statement to add new records into a table.

In Database Testing, validating data insertion is one of the most common backend testing activities. Testers verify that the data entered through the application's UI or API is correctly stored in the database.

---

# Learning Objectives

- Understand the INSERT INTO statement
- Insert single and multiple records
- Insert data into specific columns
- Insert NULL values
- Understand default values
- Verify inserted data using SELECT
- Learn best practices while inserting data

---

# INSERT INTO Syntax

### Insert values into all columns

```sql
INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

---

### Insert values into selected columns

```sql
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);
```

---

# Sample Table

```sql
CREATE TABLE Employees
(
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Department VARCHAR(50),
    Salary DECIMAL(10,2),
    City VARCHAR(50)
);
```

---

# Insert a Single Record

```sql
INSERT INTO Employees
VALUES
(101, 'Rahul', 'Sharma', 'HR', 35000, 'Bangalore');
```

### Output

| EmployeeID | FirstName | LastName | Department | Salary | City |
|------------|-----------|----------|------------|---------|------|
|101|Rahul|Sharma|HR|35000|Bangalore|

---

# Insert Data into Specific Columns

```sql
INSERT INTO Employees
(EmployeeID, FirstName, Department)
VALUES
(102, 'Aisha', 'Testing');
```

### Result

Remaining columns become **NULL** (unless a default value is defined).

| EmployeeID | FirstName | LastName | Department | Salary | City |
|------------|-----------|----------|------------|---------|------|
|102|Aisha|NULL|Testing|NULL|NULL|

---

# Insert Multiple Records

```sql
INSERT INTO Employees
VALUES
(103, 'John', 'David', 'Developer', 55000, 'Mumbai'),
(104, 'Sneha', 'Patil', 'QA', 45000, 'Pune'),
(105, 'Arjun', 'Kumar', 'Support', 30000, 'Hyderabad');
```

---

# Verify Inserted Data

```sql
SELECT *
FROM Employees;
```

---

# Insert NULL Values

```sql
INSERT INTO Employees
VALUES
(106, 'Priya', NULL, 'HR', NULL, 'Delhi');
```

### Output

| EmployeeID | FirstName | LastName | Department | Salary | City |
|------------|-----------|----------|------------|---------|------|
|106|Priya|NULL|HR|NULL|Delhi|

---

# Insert Using Current Date

Suppose we have another table.

```sql
CREATE TABLE Orders
(
    OrderID INT,
    CustomerName VARCHAR(50),
    OrderDate DATE
);
```

Insert today's date.

```sql
INSERT INTO Orders
VALUES
(1001, 'Amit', CURRENT_DATE);
```

> Some databases use **GETDATE()** or **NOW()** instead of **CURRENT_DATE**.

---

# Insert Default Values

Example table

```sql
CREATE TABLE Students
(
    StudentID INT,
    StudentName VARCHAR(50),
    Country VARCHAR(50) DEFAULT 'India'
);
```

Insert data

```sql
INSERT INTO Students
(StudentID, StudentName)
VALUES
(1, 'Mohit');
```

### Result

| StudentID | StudentName | Country |
|------------|-------------|---------|
|1|Mohit|India|

---

# ⚠ Common Errors

## Duplicate Primary Key

```sql
INSERT INTO Employees
VALUES
(101, 'Ravi', 'Kumar', 'QA', 35000, 'Delhi');
```

**Error**

Primary Key already exists.

---

## Incorrect Number of Values

```sql
INSERT INTO Employees
VALUES
(107, 'Rohit');
```

**Error**

Column count does not match value count.

---

## Wrong Data Type

```sql
INSERT INTO Employees
VALUES
('ABC', 'Rahul', 'Sharma', 'HR', 40000, 'Pune');
```

**Error**

EmployeeID expects an integer.

---

# Best Practices

- Always specify column names while inserting data.
- Verify inserted records using the SELECT statement.
- Validate data types before insertion.
- Avoid duplicate primary keys.
- Insert only valid business data.
- Use transactions when inserting multiple records.
- Validate constraints after insertion.

---

# Key Points

- INSERT INTO is used to add new records.
- Data can be inserted into all columns or selected columns.
- Multiple rows can be inserted using a single query.
- NULL values can be inserted where allowed.
- DEFAULT values are automatically assigned if configured.
- Database testers verify that inserted data is accurate, complete, and consistent.

---


# 🎯 Interview Questions

### Q1. Which SQL statement is used to insert data into a table?

---

### Q2. Can multiple records be inserted using one INSERT statement?

---

### Q3. Why should column names be specified in an INSERT statement?

---

### Q4. What happens if you insert a duplicate Primary Key?

---

### Q5. How do you verify that data has been inserted successfully?

---
