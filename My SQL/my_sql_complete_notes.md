# MySQL Complete Notes

## 1. Introduction to MySQL
- MySQL is an open-source Relational Database Management System (RDBMS).
- Uses Structured Query Language (SQL).
- Developed by Oracle Corporation.

## 2. Features
- Open-source and free
- High performance
- Scalable
- Secure
- Supports transactions

## 3. Database Basics
- Database: Collection of data
- Table: Structure to store data in rows and columns
- Row: Record
- Column: Field/Attribute

## 4. Data Types
### Numeric
- INT
- FLOAT
- DOUBLE

### String
- CHAR
- VARCHAR
- TEXT

### Date & Time
- DATE
- TIME
- DATETIME

## 5. SQL Commands Categories
### DDL (Data Definition Language)
- CREATE
- ALTER
- DROP

### DML (Data Manipulation Language)
- INSERT
- UPDATE
- DELETE

### DQL (Data Query Language)
- SELECT

### TCL (Transaction Control Language)
- COMMIT
- ROLLBACK

## 6. Database Operations
### Create Database
```sql
CREATE DATABASE db_name;
```

### Use Database
```sql
USE db_name;
```

### Drop Database
```sql
DROP DATABASE db_name;
```

## 7. Table Operations
### Create Table
```sql
CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  age INT
);
```

### Describe Table
```sql
DESC students;
```

### Drop Table
```sql
DROP TABLE students;
```

## 8. Constraints
- PRIMARY KEY
- FOREIGN KEY
- UNIQUE
- NOT NULL
- DEFAULT

## 9. Insert Data
```sql
INSERT INTO students VALUES (1, 'Vijay', 22);
```

## 10. Select Data
```sql
SELECT * FROM students;
SELECT name FROM students;
```

## 11. Where Clause
```sql
SELECT * FROM students WHERE age > 20;
```

## 12. Update Data
```sql
UPDATE students SET age = 23 WHERE id = 1;
```

## 13. Delete Data
```sql
DELETE FROM students WHERE id = 1;
```

## 14. Aggregate Functions
- COUNT()
- SUM()
- AVG()
- MAX()
- MIN()

```sql
SELECT COUNT(*) FROM students;
```

## 15. GROUP BY
```sql
SELECT age, COUNT(*) FROM students GROUP BY age;
```

## 16. ORDER BY
```sql
SELECT * FROM students ORDER BY age DESC;
```

## 17. Joins
### Types of Joins
- INNER JOIN
- LEFT JOIN
- RIGHT JOIN

```sql
SELECT s.name, c.course_name
FROM students s
INNER JOIN courses c ON s.id = c.student_id;
```

## 18. Indexes
- Improve query performance

```sql
CREATE INDEX idx_name ON students(name);
```

## 19. Views
```sql
CREATE VIEW student_view AS
SELECT name FROM students;
```

## 20. Stored Procedures
```sql
DELIMITER //
CREATE PROCEDURE GetStudents()
BEGIN
  SELECT * FROM students;
END //
DELIMITER ;
```

## 21. Triggers
```sql
CREATE TRIGGER before_insert
BEFORE INSERT ON students
FOR EACH ROW
SET NEW.name = UPPER(NEW.name);
```

## 22. Transactions
```sql
START TRANSACTION;
UPDATE students SET age = 25 WHERE id = 1;
COMMIT;
```

## 23. Normalization
- 1NF: No repeating groups
- 2NF: No partial dependency
- 3NF: No transitive dependency

## 24. Keys
- Primary Key
- Foreign Key
- Candidate Key
- Super Key

## 25. Practice Queries
```sql
-- Find students older than 20
SELECT * FROM students WHERE age > 20;

-- Count students
SELECT COUNT(*) FROM students;

-- Join example
SELECT * FROM students s JOIN courses c ON s.id = c.student_id;
```

---

## Bonus: Interview Questions
1. What is MySQL?
2. Difference between DELETE and TRUNCATE?
3. What are joins?
4. What is normalization?
5. What are indexes?

---

## End of Notes

