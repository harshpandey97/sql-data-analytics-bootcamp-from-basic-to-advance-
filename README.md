# SQL Learning Journey — 60 Day Bootcamp

Hands-on SQL practice repo built while learning SQL Server (SSMS) from scratch — covering database design, data manipulation, real-world CSV data import, and troubleshooting along the way. Part of my transition into Data Analytics.

## About This Repo

This repo documents my day-wise SQL learning journey — from creating my first database to importing and cleaning a real ~1 million row dataset. Every `.sql` file is actual, tested code that ran successfully in SQL Server Management Studio (SSMS).

## Tech Stack

- **Database:** Microsoft SQL Server (Express Edition)
- **Tool:** SQL Server Management Studio (SSMS)
- **Dataset used:** [Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+ii) (~1.06M rows)

## Progress Tracker

### ✅ Completed

- [x] Database & Table Design (DDL) — `CREATE DATABASE`, `CREATE TABLE`, `PRIMARY KEY`, `FOREIGN KEY`
- [x] Schema modification — `ALTER TABLE` (ADD / DROP COLUMN)
- [x] Data Manipulation (DML) — `INSERT`, `UPDATE`, `DELETE`
- [x] Filtering & Querying — `WHERE`, `DISTINCT`, `AND` / `OR` / `NOT`
- [x] Keys — Primary, Foreign, Candidate, Alternate, Composite, Unique, Super, Surrogate
- [x] SQL command categories — DDL, DML, DCL, TCL
- [x] Real-world data import — SQL Server Import/Export Wizard, ~1.06M row CSV
- [x] Data cleaning — fixing `varchar` vs numeric type mismatches (`CAST`, `TRY_CAST`)

### 🟡 In Progress / Next Up

- [ ] `ORDER BY` — sorting results
- [ ] Aggregate functions — `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`
- [ ] `GROUP BY` + `HAVING`
- [ ] `JOIN`s — INNER, LEFT, RIGHT, FULL
- [ ] `LIKE`, `IN`, `BETWEEN`, `NULL` handling
- [ ] `UNION` / `UNION ALL`

### 🔴 Planned (Advanced)

- [ ] Subqueries
- [ ] Views
- [ ] Stored Procedures & User-defined Functions
- [ ] Window Functions (`ROW_NUMBER()`, `RANK()`, `PARTITION BY`)
- [ ] CTEs (`WITH` clause)
- [ ] Indexes & query optimization
- [ ] Triggers
- [ ] TCL in practice — `BEGIN TRANSACTION`, `COMMIT`, `ROLLBACK`
- [ ] DCL in practice — `GRANT`, `REVOKE`

## Repo Structure

```
sql-bootcamp-journey/
├── README.md
├── Day01-05_DDL_Basics/
│   ├── 01_create_database.sql
│   ├── 02_create_tables.sql
│   ├── 03_primary_foreign_keys.sql
│   └── notes.md
├── Day06-10_DML_Basics/
│   ├── 04_insert_data.sql
│   ├── 05_update_delete.sql
│   └── notes.md
├── Day11-15_Filtering_Querying/
│   ├── 06_where_distinct.sql
│   ├── 07_logical_operators.sql
│   └── notes.md
├── Day16-20_Keys_Concepts/
│   ├── 08_types_of_keys.sql
│   └── notes.md
├── Day21-25_Real_Data_Import/
│   ├── 09_csv_import_project.sql
│   ├── 10_data_cleaning_cast.sql
│   └── notes.md
└── screenshots/
```

## Key Learnings & Challenges Solved

- **Database context errors** — learned to always run `USE [DatabaseName];` before querying, and to verify with `SELECT DB_NAME();` when hitting "Invalid object name" errors.
- **Duplicate object errors** — handled `CREATE DATABASE` / `CREATE TABLE` conflicts safely using `DROP ... IF EXISTS` and `ALTER DATABASE ... SET SINGLE_USER WITH ROLLBACK IMMEDIATE` to force-release locked databases.
- **Primary Key violations** — understood why duplicate key inserts fail and when to use `UPDATE` instead of `INSERT`.
- **CSV import type mismatches** — the Import/Export Wizard defaulted numeric columns to `varchar`, which broke `SUM`/aggregate queries; fixed using `CAST` and `TRY_CAST`.
- **Malformed CSV rows** — diagnosed column-shifting caused by unescaped commas inside quoted text fields, and learned to check the *Text Qualifier* setting in the Import Wizard.

## About Me

BCA graduate transitioning into Data Analytics / Data Science, building a portfolio project by project. Connect with me on [LinkedIn] or check out my other repos for BI, Python, and ML projects.

---

*This repo is updated as I progress through my SQL learning roadmap — Basic ✅ → Intermediate 🟡 → Advanced 🔴*
