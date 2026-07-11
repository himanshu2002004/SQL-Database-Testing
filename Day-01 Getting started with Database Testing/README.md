# Day 01 – Getting Started with Database Testing

## Introduction

Database Testing is an important part of Software Testing that focuses on validating the data stored in the database. 

While the application's user interface (UI) ensures users can interact with the system, Database Testing ensures that the data behind the application is accurate, secure, consistent, and reliable.

As a QA Engineer, understanding Database Testing helps verify whether the application correctly stores, updates, retrieves, and deletes data according to business requirements.

---

# What is Database Testing?

**Database Testing** is the process of verifying the correctness, integrity, consistency, and performance of data stored in a database.

It involves checking whether the application performs database operations correctly whenever users interact with the application.

Database Testing mainly verifies:

- Data Accuracy
- Data Integrity
- Data Consistency
- Database Constraints
- CRUD Operations
- Relationships between Tables
- Stored Procedures
- Triggers

---

# Why is Database Testing Important?

Database Testing helps ensure that:

- Data is stored correctly.
- No duplicate or incorrect records exist.
- Data relationships remain valid.
- Business rules are correctly implemented.
- Backend data matches frontend data.
- Database performance remains efficient.
- Sensitive information remains secure.

---

# Example of Database Testing

### Scenario

A user registers on an e-commerce website.

### User enters

  - Name
  - Email
  - Password
  - Phone Number

↓
Application validates the details.

↓
Application sends the data to the database.

↓
Database stores the information.

↓
Tester verifies whether the entered information is correctly stored inside the Users table.

---

# Database Testing Workflow

```text
User Action
      │
      ▼
Application (Frontend)
      │
      ▼
Business Logic
      │
      ▼
Database
      │
      ▼
Database Validation by Tester
```

---

# Objectives of Database Testing

- Verify data accuracy.
- Validate CRUD operations.
- Verify database constraints.
- Check relationships between tables.
- Validate stored procedures.
- Validate triggers.
- Verify data consistency.
- Ensure data security.
- Detect backend defects.
- Improve application reliability.

---

# Types of Database Testing

## Structural Database Testing

Structural testing verifies the database structure.

Examples:

- Tables
- Columns
- Data Types
- Constraints
- Keys
- Indexes
- Stored Procedures
- Triggers

---

## Functional Database Testing

Functional testing validates whether business operations correctly interact with the database.

Examples:

- Registration
- Login
- Payment
- Order Placement
- Employee Management

---

## Non-Functional Database Testing

Non-functional testing verifies the performance and security of the database.

Examples:

- Performance Testing
- Load Testing
- Stress Testing
- Security Testing
- Scalability Testing

---

# Common Database Operations

The four basic database operations are known as **CRUD**.

| Operation | Description |
|------------|-------------|
| Create | Insert new data |
| Read | Retrieve existing data |
| Update | Modify existing data |
| Delete | Remove data |

---

# What Does a Database Tester Verify?

A Database Tester verifies:

- Correct data insertion.
- Correct data retrieval.
- Correct data updates.
- Correct data deletion.
- Duplicate records.
- Null values.
- Data integrity.
- Primary Key constraints.
- Foreign Key constraints.
- Data consistency.
- Stored Procedures.
- Triggers.
- Transactions.

---

# Popular Databases

- MySQL
- Microsoft SQL Server
- PostgreSQL
- Oracle Database
- SQLite
- MariaDB

---

# Real-Time Example

Suppose a customer places an order on Amazon.

The tester verifies:

✅ Order is created.

✅ Customer ID is correct.

✅ Product ID is correct.

✅ Payment details are stored.

✅ Inventory is updated.

✅ Order status is updated.

If any database operation fails, the tester reports it as a defect.

---

# Advantages of Database Testing

- Improves data quality
- Detects backend defects
- Prevents data corruption
- Ensures data consistency
- Improves application reliability
- Validates business rules
- Supports secure applications

---

# Key Takeaways

✔ Database Testing validates backend data.

✔ It ensures the database stores accurate and consistent information.

✔ It verifies CRUD operations, constraints, relationships, and business rules.

✔ It is essential for ensuring application reliability and data integrity.

---

# Summary

Database Testing is an essential part of Software Testing that focuses on validating backend data. It ensures that the application's data is accurate, complete, consistent, and secure. By verifying database operations and business rules, testers help deliver reliable and high-quality software.

---
