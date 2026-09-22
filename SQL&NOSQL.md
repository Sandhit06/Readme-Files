 # SQL vs NoSQL Databases: System Design & Interview Handbook

> A comprehensive guide to understanding SQL and NoSQL databases from a System Design perspective. This document covers architectural differences, scalability patterns, consistency models, database selection strategies, real-world use cases, interview frameworks, and best practices.

---

# Table of Contents

- [Introduction
- [What is SQL?](#what-is NoSQL?- [SQL vs NoSQL: Complete Comparison](#sql-vs-nosql-completes-base)
ability](#databasedelling Approaches](#data-modellingL Databases](#types-of-nosql-databases)
n to Choose NoSQL](#when-to Design Decision Framework
- [Real-World Use Cases](#real-worldtabase Architecture
- [CAP Theorem and Database Selection](#[Interview Answer Framework](#interview-answeresign-scenarios
- [Interview Questions and Answers](#interview-ision Cheat Sheet](#quick-revision-cheat-sheetroduction

One of the most common questions in System Design interviews is:

> Should we use SQL or NoSQL?

The answer is:

> There is no universally better database. The right choice depends on business requirements, consistency expectations, scalability requirements, query complexity, traffic volume, and data access patterns.

Modern large-scale systems rarely depend on a single database technology. Most production-grade architectures use a combination of SQL and NoSQL databases to satisfy different requirements.

Database selection should be considered a design decision rather than a technology preference.

---

# What is SQL?

SQL (Structured Query Language) databases are relational databases that store data in tables comprising rows and columns.

Examples:

- PostgreSQL
- MySQL
- Oracle
- Microsoft SQL Server
- MariaDB

Example:

## Users Table

| UserId | Name | Email |
|---------|---------|---------|
| 1 | Sandhit | sandhit@example.com |
| 2 | Rahul | rahul@example.com |

## Orders Table

| OrderId | UserId | Amount |
|---------|---------|---------|
| 101 | 1 | 500 |

Relationship:

```text
Users.UserId = Orders.UserId
```

Characteristics:

- Structured schema
- Relationships through foreign keys
- ACID compliance
- Strong consistency
- Support for joins
- Excellent query capabilities

---

# What is NoSQL?

NoSQL stands for "Not Only SQL".

NoSQL databases are non-relational databases designed to solve scalability and flexibility challenges.

Examples:

- MongoDB
- Cassandra
- DynamoDB
- Redis
- Couchbase
- Neo4j

MongoDB Example:

```json
{
  "userId": 1,
  "name": "Sandhit",
  "email": "sandhit@example.com",
  "orders": [
    {
      "orderId": 101,
      "amount": 500
    }
  ]
}
```

Characteristics:

- Flexible schema
- Horizontal scalability
- High availability
- High throughput
- Optimised for distributed systems
- Suitable for semi-structured and unstructured data

---

# SQL vs NoSQL: Complete Comparison

| Feature | SQL Database | NoSQL Database |
|----------|-------------|--------------|
| Type | Relational | Non-relational |
| Schema | Fixed | Flexible |
| Data Storage | Tables | Documents, Key-Value, Graph, Columns |
| Consistency | Strong | Eventual (usually) |
| Transactions | ACID | BASE |
| Scaling | Vertical | Horizontal |
| Joins | Supported | Generally Avoided |
| Query Complexity | Excellent | Limited |
| Data Relationships | Strong | Weak |
| Write Throughput | Moderate | High |
| Read Throughput | High | Very High |
| Suitability | Structured Data | Dynamic Data |
| Examples | PostgreSQL, MySQL | MongoDB, Cassandra |

---

# ACID vs BASE

Database consistency is one of the most important factors in system design.

## ACID Properties

Used by most SQL databases.

### Atomicity

Everything succeeds or everything fails.

Example:

```text
Transfer ₹1000

Debit Account A
Credit Account B
```

If one operation fails:

```text
Rollback Entire Transaction
```

---

### Consistency

Database always remains valid.

Rules:

```text
Balance cannot become negative
Primary keys remain unique
Foreign keys remain valid
```

---

### Isolation

Concurrent transactions do not affect each other.

---

### Durability

Once data is committed:

```text
Data survives crashes
```

---

# BASE Properties

Common in distributed NoSQL systems.

## Basically Available

System remains operational.

---

## Soft State

State can evolve over time.

---

## Eventually Consistent

All replicas eventually become consistent.

Example:

Instagram Like Count

```text
User A sees 100 likes
User B sees 101 likes
```

A short inconsistency is acceptable.

---

# Database Scalability

## SQL Scaling

Traditional SQL databases scale vertically.

```text
Server

8 Core
 ↓
16 Core
 ↓
32 Core
```

Advantages:

- Easier architecture
- Strong consistency

Limitations:

- Hardware limits
- Expensive upgrades

---

## NoSQL Scaling

NoSQL databases scale horizontally.

```text
Node 1
Node 2
Node 3
Node 4
Node 5
```

Advantages:

- Near-infinite scaling
- Better fault tolerance
- High availability

Ideal for:

- Social media
- Messaging systems
- Analytics platforms
- IoT systems

---

# Data Modelling Approaches

## SQL Normalization

Example:

```text
Users
Orders
Payments
Products
```

Relationships maintained via:

```text
Primary Keys
Foreign Keys
```

Benefits:

- No Data Duplication
- Data Integrity
- Easy Updates

Drawbacks:

- Complex Joins
- Higher Query Cost

---

## NoSQL Denormalization

Example:

```json
{
  "userId": 1,
  "orders": [
    {},
    {},
    {}
  ]
}
```

Benefits:

- Faster Reads
- Reduced Joins
- Better Performance

Drawbacks:

- Data Duplication
- Difficult Updates

---

# Types of NoSQL Databases

## 1. Document Databases

Examples:

```text
MongoDB
Couchbase
```

Data Format:

```json
{
  "name": "Sandhit"
}
```

Use Cases:

- User Profiles
- Product Catalogues
- CMS Systems

---

## 2. Key-Value Databases

Examples:

```text
Redis
DynamoDB
```

Format:

```text
Key → Value
```

Example:

```text
session:12345 → user data
```

Use Cases:

- Caching
- Session Management
- Authentication Tokens

---

## 3. Wide Column Databases

Examples:

```text
Cassandra
HBase
```

Use Cases:

- Analytics
- Logging
- Event Streaming
- Time Series Data

---

## 4. Graph Databases

Examples:

```text
Neo4j
Amazon Neptune
```

Use Cases:

- Social Networks
- Recommendation Engines
- Fraud Detection

---

# When to Choose SQL

Choose SQL when:

✅ Strong Consistency Required

✅ Financial Transactions

✅ Banking Systems

✅ Inventory Management

✅ Order Processing

✅ Multi-row Transactions

✅ Complex Joins

✅ Fixed Schema

✅ Data Integrity is Critical

Examples:

```text
Banking Application
Payment Gateway
ERP System
CRM
Accounting Software
Hospital Management System
```

---

# When to Choose NoSQL

Choose NoSQL when:

✅ Massive Scale Required

✅ Billions of Records

✅ Frequent Schema Changes

✅ High Write Throughput

✅ Distributed Systems

✅ Real-time Data

✅ Event-Based Systems

Examples:

```text
Instagram
Facebook
WhatsApp
Netflix
Uber
Twitter
Gaming Systems
IoT Applications
```

---

# System Design Decision Framework

Whenever the interviewer asks:

> Which database would you choose?

Follow this process.

## Step 1

Is strict consistency required?

```text
Yes → SQL
No → Go To Step 2
```

---

## Step 2

Will the system handle extremely large traffic?

```text
Yes → NoSQL
No → Go To Step 3
```

---

## Step 3

Are relationships complex?

```text
Yes → SQL
No → Go To Step 4
```

---

## Step 4

Does schema change frequently?

```text
Yes → NoSQL
No → SQL
```

---

# Real-World Use Cases

## Banking System

Use:

```text
PostgreSQL / Oracle
```

Reason:

```text
ACID Transactions
Strong Consistency
Data Integrity
```

---

## Instagram Feed

Use:

```text
Cassandra
MongoDB
```

Reason:

```text
Massive Scale
Fast Reads
Distributed Infrastructure
```

---

## WhatsApp

Use:

```text
Cassandra
```

Reason:

```text
High Write Throughput
Global Distribution
```

---

## E-Commerce Platform

Use Both.

SQL:

```text
Orders
Payments
Invoices
Inventory
```

NoSQL:

```text
Product Catalogues
Search
Recommendations
Reviews
```

---

# Hybrid Database Architecture

Modern Systems Typically Use Multiple Databases.

```text
                    Users
                      |
                      ▼

                API Gateway
                      |
          ------------------------
          |                      |
          ▼                      ▼

      PostgreSQL           MongoDB
      Orders               Profiles

          ▼                      ▼

       Redis               Cassandra
       Cache               Analytics

          ▼
       Elasticsearch
       Search Engine
```

Database Selection:

| Component | Database |
|------------|----------|
| Orders | PostgreSQL |
| Payments | PostgreSQL |
| Search | Elasticsearch |
| Sessions | Redis |
| Product Metadata | MongoDB |
| Activity Logs | Cassandra |

---

# CAP Theorem and Database Selection

CAP Theorem states that distributed systems can provide only two of the following three guarantees simultaneously:

## Consistency (C)

All nodes see same data.

---

## Availability (A)

Every request gets response.

---

## Partition Tolerance (P)

System continues functioning despite network failures.

---

Examples:

### Banking

Prefer:

```text
Consistency + Partition Tolerance
```

---

### Social Media

Prefer:

```text
Availability + Partition Tolerance
```

---

# Interview Answer Framework

## Why SQL?

Sample Answer:

> I would choose SQL because the system requires strong consistency, ACID transactions, and complex relational queries. Data integrity is critical, and the schema is relatively stable.

---

## Why NoSQL?

Sample Answer:

> I would choose NoSQL because the system expects massive scale, high read and write throughput, flexible schemas, and horizontal scalability across multiple regions.

---

## Best Senior-Level Answer

> I would first analyse consistency requirements, traffic patterns, query complexity, scaling expectations, and data relationships. If transactional integrity is critical, I would choose SQL. If scalability and flexibility are primary concerns, I would choose NoSQL. In large-scale production systems, I would most likely use both.

---

# Interview Questions and Answers

## SQL or NoSQL for Banking?

Answer:

```text
SQL
```

Reason:

```text
ACID + Consistency
```

---

## SQL or NoSQL for Ride Sharing?

Answer:

```text
Hybrid
```

SQL:

```text
Payments
Trips
Invoices
```

NoSQL:

```text
Driver Location
Analytics
Real-Time Tracking
```

---

## SQL or NoSQL for Chat Application?

Answer:

```text
NoSQL
```

Reason:

```text
Massive Write Volume
Horizontal Scalability
```

---

## SQL or NoSQL for E-Commerce?

Answer:

```text
Hybrid
```

Reason:

```text
Orders need SQL.
Catalogue and Search need NoSQL.
```

---

# Quick Revision Cheat Sheet

```text
SQL

✓ ACID
✓ Strong Consistency
✓ Relational
✓ Joins
✓ Transactions
✓ Banking
✓ Payments
✓ Inventory

NoSQL

✓ BASE
✓ Eventual Consistency
✓ Flexible Schema
✓ Horizontal Scaling
✓ Fast Reads/Writes
✓ Social Media
✓ Messaging
✓ Analytics
✓ Logging

Golden Rule

Consistency → SQL

Scalability → NoSQL

Enterprise Systems → Hybrid
```

---

# Key Takeaways

1. SQL is preferred when consistency and transactions are critical.
2. NoSQL is preferred when scalability and flexibility are more important.
3. ACID is strongest in SQL systems.
4. BASE is commonly used in NoSQL systems.
5. SQL uses normalised relational models.
6. NoSQL often uses denormalised models.
7. Modern architectures almost always use multiple databases.
8. Database choice should always be driven by system requirements, not technology popularity.
9. In interviews, explain trade-offs instead of simply naming a database.
10. The strongest system design answer is usually a hybrid architecture justified by business requirements.

---

## Interview Golden Statement

> SQL and NoSQL are not competitors. They solve different problems. SQL excels in consistency, transactions, and relational modelling, while NoSQL excels in scalability, flexibility, and distributed workloads. The best database choice is the one that aligns with the system's access patterns, consistency requirements, and scalability goals.