# Day 02 - Database Basics

# What is a Database?

A **Database** is an organized collection of data that is stored electronically and can be easily accessed, managed, updated, and retrieved.

It helps organizations store large amounts of information efficiently.

### Example

An E-commerce application stores:

- Customer Information
- Product Details
- Orders
- Payments
- Delivery Information

All this information is stored inside a database.

---

# What is DBMS?

**DBMS (Database Management System)** is software that allows users to create, store, manage, update, and retrieve data from a database.

It acts as an interface between the user and the database.

### Features

- Data Storage
- Data Retrieval
- Data Manipulation
- Security
- Backup & Recovery
- Data Sharing

### Examples

- Microsoft Access
- File System
- IBM DB2

---

# What is RDBMS?

**RDBMS (Relational Database Management System)** is a type of DBMS that stores data in the form of **tables**.

The tables are related using **Primary Keys** and **Foreign Keys**.

RDBMS follows the relational model introduced by E. F. Codd.

### Features

- Stores data in tables
- Supports relationships
- Maintains data integrity
- Supports SQL
- Reduces data redundancy

### Examples

- MySQL
- PostgreSQL
- Oracle Database
- Microsoft SQL Server
- MariaDB
- SQLite

---

# DBMS vs RDBMS

| Feature | DBMS | RDBMS |
|----------|------|--------|
| Storage | Files or Tables | Tables |
| Relationship | Not Supported | Supported |
| Normalization | Limited | Supported |
| Data Redundancy | High | Low |
| Security | Basic | Advanced |
| SQL Support | Limited | Full |
| Multi-user Access | Limited | Supported |
| Examples | MS Access | MySQL, Oracle, SQL Server |

---

# Popular Databases

| Database | Description |
|----------|-------------|
| MySQL | Open-source relational database widely used in web applications. |
| PostgreSQL | Advanced open-source relational database with powerful features. |
| Oracle Database | Enterprise-level relational database used by large organizations. |
| Microsoft SQL Server | Popular RDBMS developed by Microsoft. |
| SQLite | Lightweight database commonly used in mobile and embedded applications. |
| MariaDB | Community-developed fork of MySQL with enhanced performance. |

---

# What is a Table?

A **Table** is a collection of related data organized into rows and columns.

Example:

| Employee_ID | Name | Department | Salary |
|-------------|------|------------|---------|
| 101 | Rahul | HR | 40000 |
| 102 | Priya | IT | 55000 |
| 103 | Aman | Finance | 50000 |

---

# What is a Row?

A **Row** (also called a Record) represents one complete set of information in a table.

Example

| Employee_ID | Name |
|-------------|------|
| 101 | Rahul |

This single record is one row.

---

# What is a Column?

A **Column** represents a single attribute of the data.

Example

| Employee_ID | Name | Department |
|-------------|------|------------|

Each heading is called a column.

---

# Primary Key

A **Primary Key** uniquely identifies each record in a table.

### Characteristics

- Unique
- Cannot be NULL
- Only one Primary Key per table

Example

| Employee_ID | Name |
|-------------|------|
| 101 | Rahul |
| 102 | Priya |

Here, **Employee_ID** is the Primary Key.

---

# Foreign Key

A **Foreign Key** is a column that creates a relationship between two tables.

It references the Primary Key of another table.

### Example

### Employee Table

| Employee_ID | Name |
|-------------|------|
| 101 | Rahul |
| 102 | Priya |

### Salary Table

| Salary_ID | Employee_ID | Salary |
|------------|-------------|---------|
| 1 | 101 | 40000 |
| 2 | 102 | 50000 |

Here,

**Employee_ID** in the Salary table is the Foreign Key.

---

# Relationship Between Tables

```
Employees
------------------------
Employee_ID (PK)
Name
Department

        │

        ▼

Salary
------------------------
Salary_ID (PK)
Employee_ID (FK)
Salary
```

The Foreign Key connects both tables.

---

# Importance in Database Testing

As a Software Tester, understanding databases helps you:

- Verify data stored in the backend.
- Validate CRUD operations.
- Check data integrity.
- Verify relationships between tables.
- Ensure data consistency.
- Validate business rules.

---

# Real-World Example

Scenario:

A customer places an order on an E-commerce website.

The application stores information in multiple tables:

- Customers
- Orders
- Payments
- Order Items

A tester verifies that:

- Customer details are saved correctly.
- Order information is created.
- Payment records are generated.
- Relationships between tables remain accurate.

---

# Key Takeaways

- A Database stores organized data.
- DBMS manages databases.
- RDBMS stores data in related tables.
- Tables contain rows and columns.
- Primary Keys uniquely identify records.
- Foreign Keys create relationships between tables.
- Understanding database basics is essential for Database Testing.

---

