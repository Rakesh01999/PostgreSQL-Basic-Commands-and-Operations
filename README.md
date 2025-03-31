# PostgreSQL Basic Commands and Operations

## **Introduction**
PostgreSQL is a powerful, open-source relational database management system. This document provides a reference for basic PostgreSQL commands, including version checking, database listing, table creation, schema management, and connection information.

---

## **1. Checking PostgreSQL Version**
To check the installed PostgreSQL version, use:
```sql
SELECT version();
```
**Output Example:**
```
 PostgreSQL 17.4 on x86_64-windows, compiled by msvc-19.42.34436, 64-bit
(1 row)
```
---

## **2. Listing Available Databases**
To list all databases in your PostgreSQL instance, use:
```sql
\l
```
**Output Example:**
```
    Name    |  Owner   | Encoding | Locale Provider | Collate | Ctype | Locale | ICU Rules | Access privileges
-----------+----------+----------+-----------------+---------+-------+--------+-----------+-----------------------
 postgres  | postgres | UTF8     | libc            | en-US   | en-US |        |           |
 template0 | postgres | UTF8     | libc            | en-US   | en-US |        |           | =c/postgres          +
           |          |          |                 |         |       |        |           | postgres=CTc/postgres
 template1 | postgres | UTF8     | libc            | en-US   | en-US |        |           | =c/postgres          +
           |          |          |                 |         |       |        |           | postgres=CTc/postgres
(3 rows)
```
---

## **3. Switching Databases**
To switch to another database, use:
```sql
\c database_name;
```
Example:
```sql
\c template1;
```
**Output:**
```
You are now connected to database "template1" as user "postgres".
```
---

## **4. Listing Tables in a Database**
To see all tables within a database:
```sql
\d
```
If no tables exist, you will get:
```
Did not find any relations.
```
---

## **5. Creating a Table**
To create a table, use the `CREATE TABLE` statement:
```sql
CREATE TABLE test_table(name VARCHAR(50));
```
After creating the table, list tables again using:
```sql
\d
```
**Output Example:**
```
           List of relations
 Schema |    Name    | Type  |  Owner  
--------+------------+-------+---------
 public | test_table | table | postgres
(1 row)
```
---

## **6. Listing Schemas**
To view available schemas:
```sql
\dn
```
**Output Example:**
```
      List of schemas
  Name  |       Owner       
--------+-------------------
 public | pg_database_owner
(1 row)
```
---

## **7. Checking Table Details**
To get detailed information about tables:
```sql
\d+
```
**Output Example:**
```
                                      List of relations
 Schema |    Name    | Type  |  Owner   | Persistence | Access method |  Size   | Description
--------+------------+-------+----------+-------------+---------------+---------+-------------
 public | test_table | table | postgres | permanent   | heap          | 0 bytes |
(1 row)
```
---

## **8. Checking Connection Information**
To check database connection details, use:
```sql
\conninfo
```
**Output Example:**
```
You are connected to database "postgres" as user "postgres" on host "localhost" (address "::1") at port "5432".
```
This confirms the active database, user, host, and port information.

---

## **Conclusion**
This document provides essential PostgreSQL commands to manage databases, schemas, tables, and connections effectively. Use these commands as a reference while working with PostgreSQL on your local or production environments.

