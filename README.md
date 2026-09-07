# emp_dept_practice.s

# SQL EMP/DEPT Practice

A collection of 100+ SQL practice queries built on the classic **EMP** (employees) and **DEPT** (departments) schema — the same dataset widely used in Oracle/SQL tutorials, adapted here for MySQL.

## Schema

**EMP**
| Column   | Type          | Description                |
|----------|---------------|-----------------------------|
| EMPNO    | INT (PK)      | Employee number             |
| ENAME    | VARCHAR(10)   | Employee name                |
| JOB      | VARCHAR(9)    | Job title                    |
| MGR      | INT           | Manager's EMPNO              |
| HIREDATE | DATE          | Date of hire                 |
| SAL      | INT           | Monthly salary               |
| COMM     | INT           | Commission (nullable)        |
| DEPTNO   | INT           | Department number (FK)       |

**DEPT**
| Column | Type          | Description        |
|--------|---------------|---------------------|
| DEPTNO | INT (PK)      | Department number   |
| DNAME  | VARCHAR(14)   | Department name     |
| LOC    | VARCHAR(13)   | Department location |

14 employees across 3 departments (ACCOUNTING, RESEARCH, SALES) in NEW YORK, DALLAS, and CHICAGO.

## What's covered

- **Basic selection & filtering** — `WHERE`, `BETWEEN`, `IN`, comparisons
- **Sorting & string functions** — `ORDER BY`, `LIKE`, `SUBSTR`, `LENGTH`, `INITCAP`
- **NULLs & arithmetic** — `COALESCE`/`NVL`-style handling, computed columns
- **Aggregate functions & `GROUP BY`** — `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`
- **Group filtering with `HAVING`**
- **Joins & self-joins** — manager/employee relationships, peer comparisons
- **Subqueries** — single-row, multi-row (`IN`, `ALL`, `ANY`), correlated, `EXISTS`/`NOT EXISTS`
- **Date & time functions** — `EXTRACT`, `DATEDIFF`, leap years, day-of-week
- **Window functions** — `RANK`, `DENSE_RANK`, `ROW_NUMBER`, `LEAD`/`LAG`, `NTILE`, running totals
- **Multi-table (EMP + DEPT) queries** — inner/outer joins, correlated subqueries across tables, payroll analytics

Roughly split into two parts: single-table queries against `EMP`, and multi-table relational queries joining `EMP` and `DEPT`.

## How to run it

1. Install MySQL (5.7+ recommended for window function support, use 8.0+ for full compatibility).
2. Run the script top to bottom:
   ```bash
   mysql -u root -p < emp_dept_practice.sql
   ```
   or paste it into MySQL Workbench / your client of choice.
3. The script creates the `employees` database, builds `EMP` and `DEPT`, seeds sample data, then runs through all the practice queries.

> **Note:** A few queries use Oracle-style syntax (e.g. `e.DEPTNO(+)` for outer joins) alongside MySQL equivalents (`LEFT JOIN`/`RIGHT JOIN`). If running strictly on MySQL, prefer the ANSI-join versions.

## Why this exists

Useful as a self-study reference or interview-prep resource for practicing SQL fundamentals through advanced analytics (window functions, correlated subqueries) on a small, well-known dataset.
