# Day 12 – ALTER Statement in SQL

The **ALTER** statement in SQL is a **Data Definition Language (DDL)** command used to modify the structure of an existing table without deleting the table or its data.

Using the `ALTER` statement, we can:

- Add new columns
- Modify existing columns
- Rename columns
- Rename tables
- Drop unwanted columns
- Add or remove constraints

The ALTER statement is commonly used when business requirements change and the database schema needs to be updated.

---

# Learning Objectives

- Understand the ALTER Statement
- Add a New Column
- Modify an Existing Column
- Rename a Column
- Rename a Table
- Drop a Column
- Add Constraints
- Drop Constraints
- Understand real-time Database Testing scenarios

---

# Syntax

```sql
ALTER TABLE table_name
operation;
```

---

# Sample Table

```sql
CREATE TABLE EMPLOYEE(
    EMPID VARCHAR(10) PRIMARY KEY,
    EMPNAME VARCHAR(20),
    EMP_AGE INT UNSIGNED,
    EMP_SALARY DECIMAL(10,2),
    EMP_DEPARTMENT VARCHAR(20)
);
```

---

# 1. Add a New Column

Suppose the company wants to store employee email addresses.

### Syntax

```sql
ALTER TABLE EMPLOYEE
ADD EMAIL VARCHAR(50);
```

---

### Output Structure

| EMPID | EMPNAME | EMP_AGE | EMP_SALARY | EMP_DEPARTMENT | EMAIL |
|-------|----------|----------|------------|----------------|-------|

---

# 2. Add Multiple Columns

```sql
ALTER TABLE EMPLOYEE
ADD PHONE VARCHAR(15),
ADD CITY VARCHAR(30);
```

---

# Modify a Column

Suppose the company decides that employee names should allow up to 50 characters.

```sql
ALTER TABLE EMPLOYEE
MODIFY EMPNAME VARCHAR(50);
```

---

Another Example

Increase salary precision.

```sql
ALTER TABLE EMPLOYEE
MODIFY EMP_SALARY DECIMAL(12,2);
```

---

# 4. Rename a Column (MySQL 8.0+)

Suppose EMPNAME should be renamed to EMPLOYEE_NAME.

```sql
ALTER TABLE EMPLOYEE
RENAME COLUMN EMPNAME TO EMPLOYEE_NAME;
```

---

## Alternative (Older MySQL Versions)

```sql
ALTER TABLE EMPLOYEE
CHANGE EMPNAME EMPLOYEE_NAME VARCHAR(50);
```

---

# 5. Rename the Table

Suppose EMPLOYEE should be renamed to STAFF.

```sql
ALTER TABLE EMPLOYEE
RENAME TO STAFF;
```

---

# 6. Drop a Column

Suppose the EMAIL column is no longer required.

```sql
ALTER TABLE EMPLOYEE
DROP COLUMN EMAIL;
```

---

# 7. Add a Constraint

Add a UNIQUE constraint on Email.

```sql
ALTER TABLE EMPLOYEE
ADD CONSTRAINT UK_EMAIL UNIQUE(EMAIL);
```

---

Add CHECK Constraint.

```sql
ALTER TABLE EMPLOYEE
ADD CONSTRAINT CHK_SALARY
CHECK(EMP_SALARY > 0);
```

---

# 8. Drop a Constraint

Drop the UNIQUE constraint.

```sql
ALTER TABLE EMPLOYEE
DROP INDEX UK_EMAIL;
```

---

# Common ALTER Operations

| Operation | SQL Statement |
|------------|---------------|
| Add Column | `ADD` |
| Modify Column | `MODIFY` |
| Rename Column | `RENAME COLUMN` |
| Rename Table | `RENAME TO` |
| Drop Column | `DROP COLUMN` |
| Add Constraint | `ADD CONSTRAINT` |
| Drop Constraint | `DROP INDEX` / `DROP CONSTRAINT` |

---

#  Real-Time Examples

## Example 1

Company starts collecting employee email addresses.

```sql
ALTER TABLE EMPLOYEE
ADD EMAIL VARCHAR(100);
```

---

## Example 2

Salary column needs higher precision.

```sql
ALTER TABLE EMPLOYEE
MODIFY EMP_SALARY DECIMAL(12,2);
```

---

## Example 3

Department name length should be increased.

```sql
ALTER TABLE EMPLOYEE
MODIFY EMP_DEPARTMENT VARCHAR(50);
```

---

## Example 4

Rename EMPNAME to EMPLOYEE_NAME.

```sql
ALTER TABLE EMPLOYEE
RENAME COLUMN EMPNAME TO EMPLOYEE_NAME;
```

---

## Example 5

Remove an unused PHONE column.

```sql
ALTER TABLE EMPLOYEE
DROP COLUMN PHONE;
```

---

# Database Testing Scenarios

### Scenario 1

Verify a newly added column exists after executing the ALTER statement.

---

### Scenario 2

Verify old data remains unchanged after adding a new column.

---

### Scenario 3

Verify data is not lost after modifying a column's size.

---

### Scenario 4

Verify inserting new records works after altering the table.

---

### Scenario 5

Verify renamed columns are reflected correctly in the application.

---

### Scenario 6

Verify dropped columns are no longer accessible.

---

### Scenario 7

Verify constraints added using ALTER are enforced correctly.

---

# Best Practices

- Take a database backup before altering production tables.
- Verify dependencies such as views, stored procedures, and applications before renaming or dropping columns.
- Use meaningful column names.
- Test ALTER statements in a development environment before production deployment.
- Validate existing data after every schema modification.

---

# ⚠ Common Mistakes

## Forgetting to Backup Data

Always take a backup before modifying production tables.

---

## Modifying a Column to a Smaller Size

This may truncate existing data.

Example:

```sql
ALTER TABLE EMPLOYEE
MODIFY EMPNAME VARCHAR(5);
```

---

## Dropping Important Columns

Once dropped, the column and its data are lost unless restored from backup.

---

## Renaming Columns Without Updating Application Code

---

# Interview Questions

## Q1. What is the ALTER statement?

---

## Q2. Is ALTER a DDL or DML command?

---

## Q3. Can ALTER delete data?

---

## Q4. Difference between ALTER and UPDATE?

---

## Q5. Difference between ADD and MODIFY?

---

## Q6. Can we rename a column using ALTER?

---

## Q7. What precautions should be taken before using ALTER?

---

The application may fail if it still references the old column na
---
