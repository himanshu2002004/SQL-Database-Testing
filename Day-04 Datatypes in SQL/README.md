# Day 04 - SQL Data Types

## Introduction

Data Types define the type of data that can be stored in a table column. Choosing the correct data type is important because it helps maintain data accuracy, improves storage efficiency, and enhances database performance.

For example:
- Employee Name → Text
- Employee Age → Number
- Salary → Decimal
- Date of Joining → Date
- Is Active → Boolean

---

# What are SQL Data Types?

A SQL Data Type specifies the kind of value a column can store. Every column in a database table must have a data type assigned.

Example:

| Column Name | Data Type |
|-------------|-----------|
| EmployeeID | INT |
| EmployeeName | VARCHAR(100) |
| Salary | DECIMAL(10,2) |
| JoiningDate | DATE |
| IsActive | BOOLEAN |

---

# Why are Data Types Important?

Using appropriate data types provides several benefits:

- Ensures data integrity
- Prevents invalid data entry
- Optimizes database storage
- Improves query performance
- Makes database design efficient
- Supports accurate calculations

---

# Categories of SQL Data Types

SQL Data Types are generally divided into the following categories:

1. Numeric Data Types
2. Character/String Data Types
3. Date and Time Data Types
4. Boolean Data Type
5. Binary Data Types

---

# 1. Numeric Data Types

Numeric data types are used to store numbers.

| Data Type | Description |
|-----------|-------------|
| INT | Stores whole numbers |
| BIGINT | Stores very large integers |
| SMALLINT | Stores small integers |
| TINYINT | Stores very small integers |
| DECIMAL(p,s) | Stores exact decimal values |
| NUMERIC(p,s) | Similar to DECIMAL |
| FLOAT | Stores approximate decimal numbers |
| REAL | Stores floating-point values |

Example:

```sql
Salary DECIMAL(10,2),
Bonus FLOAT
);
```

---

# 2. Character (String) Data Types

Used to store text values.

| Data Type | Description |
|-----------|-------------|
| CHAR(n) | Fixed-length string |
| VARCHAR(n) | Variable-length string |
| TEXT | Stores long text |
| NCHAR | Fixed-length Unicode string |
| NVARCHAR | Variable-length Unicode string |

Example:

```sql
Name VARCHAR(100),
Department CHAR(20),
Address TEXT
```

---

# CHAR vs VARCHAR

| CHAR | VARCHAR |
|------|----------|
| Fixed Length | Variable Length |
| Faster for fixed-size values | Saves storage |
| Stores blank spaces | No extra blank spaces |

Example:

```sql
CHAR(10)
```

Value:

```
John______
```

Example:

```sql
VARCHAR(10)
```

Value:

```
John
```

---

# 4. Boolean Data Type

Stores only TRUE or FALSE values.

Example:

```sql
IsActive BOOLEAN
```

Possible values:

```
TRUE
FALSE
```

Some databases use:

```
1 = TRUE

0 = FALSE
```

---

# 5. Binary Data Types

Used to store images, files, videos, or binary information.

| Data Type | Description |
|-----------|-------------|
| BINARY | Fixed binary data |
| VARBINARY | Variable binary data |
| BLOB | Large binary object |

Example:

```sql
DocumentFile BLOB
```

---

# Common SQL Data Types

| Data Type | Example |
|-----------|----------|
| INT | 101 |
| VARCHAR(50) | John |
| CHAR(5) | ABCDE |
| DECIMAL(8,2) | 25000.75 |
| DATE | 2026-07-11 |
| TIME | 10:30:45 |
| DATETIME | 2026-07-11 10:30:45 |
| BOOLEAN | TRUE |

---

---

# Interview Questions

### 1. What is a SQL Data Type?

---

### 2. What is the difference between CHAR and VARCHAR?

---

### 3. Which data type should be used for salary?

---

### 4. Which data type stores only date?

---

### 5. Which data type stores TRUE or FALSE?

--- 
