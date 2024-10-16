# 0x00. MySQL Advanced

## Description
This project focuses on advanced SQL concepts using **MySQL**. You will learn to create tables with constraints, optimize queries by adding indexes, implement stored procedures, functions, views, and triggers in MySQL. These are crucial concepts for managing efficient, complex databases in the backend of applications.

---

## Learning Objectives
By the end of this project, you will be able to:
- Create tables with constraints in MySQL.
- Optimize queries using indexes.
- Implement stored procedures and functions in MySQL.
- Create and use views in MySQL.
- Understand and create triggers in MySQL.

---

## Concepts & Resources

- [MySQL cheatsheet](https://dev.mysql.com/doc/refman/8.0/en/cheatsheet.html)
- [MySQL Performance: How To Leverage MySQL Database Indexing](https://dev.mysql.com/doc/refman/8.0/en/optimization-indexes.html)
- [Stored Procedure](https://dev.mysql.com/doc/refman/8.0/en/stored-programs.html)
- [Triggers](https://dev.mysql.com/doc/refman/8.0/en/triggers.html)
- [Views](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)
- [Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/functions.html)
- [CREATE TABLE Statement](https://dev.mysql.com/doc/refman/8.0/en/create-table.html)
- [CREATE PROCEDURE and CREATE FUNCTION Statements](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html)
- [CREATE INDEX Statement](https://dev.mysql.com/doc/refman/8.0/en/create-index.html)
- [CREATE VIEW Statement](https://dev.mysql.com/doc/refman/8.0/en/create-view.html)

---

## Requirements

- **MySQL Version**: All queries must run on **MySQL 5.7 (version 5.7.30)** on **Ubuntu 18.04 LTS**.
- **File Format**: Each SQL file should start with a comment describing the task and should end with a new line.
- **SQL Keywords**: Use uppercase for SQL keywords (e.g., `SELECT`, `WHERE`).
- **File Testing**: The length of your SQL files will be tested using `wc`.

---

## Instructions

### Setting Up MySQL in a Container

1. Request a container running **Ubuntu 18.04** with **Python 3.7**.
2. Connect via SSH or WebTerminal.
3. Start MySQL:
   ```bash
   $ service mysql start
   * MySQL Community Server 5.7.30 is started
   ```

### Running SQL Queries

- To execute SQL scripts, pipe the file into MySQL as follows:
  ```bash
  $ cat <filename.sql> | mysql -uroot -p
  Enter password:
  ```

### Importing a SQL Dump
- You can create a database and import an SQL dump as follows:
  ```bash
  $ echo "CREATE DATABASE my_database;" | mysql -uroot -p
  Enter password:
  
  $ curl "<SQL_DUMP_URL>" -s | mysql -uroot -p my_database
  Enter password:
  ```

---

## Example SQL Query Format

```sql
-- List all databases in the MySQL server
SELECT schema_name 
FROM information_schema.schemata;
```

---

## Tasks Overview

1. **Create Tables with Constraints**:
   - Learn how to define **primary keys**, **foreign keys**, **unique constraints**, and **NOT NULL** constraints.
   
2. **Optimize Queries with Indexes**:
   - Add **indexes** to improve query performance and speed up searches.
   
3. **Stored Procedures**:
   - Write procedures to encapsulate frequently used SQL logic.
   
4. **Views**:
   - Implement views to simplify complex queries.
   
5. **Triggers**:
   - Use triggers to automatically execute code in response to certain events in the database.

---

## How to Test

To check your queries, simply run:

```bash
$ mysql -uroot -p <database_name>
```

You can also pipe your SQL files into the MySQL command:

```bash
$ cat <task.sql> | mysql -uroot -p <database_name>
```
