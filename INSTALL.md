<p align="center">
  <img src="https://www.especial.gr/wp-content/uploads/2019/03/panepisthmio-dut-attikhs.png" alt="UNIWA" width="150"/>
</p>

<p align="center">
  <strong>UNIVERSITY OF WEST ATTICA</strong><br>
  SCHOOL OF ENGINEERING<br>
  DEPARTMENT OF COMPUTER ENGINEERING AND INFORMATICS
</p>

<p align="center">
  <a href="https://www.uniwa.gr" target="_blank">University of West Attica</a> ·
  <a href="https://ice.uniwa.gr" target="_blank">Department of Computer Engineering and Informatics</a>
</p>

---

<p align="center">
  <strong>Databases II</strong>
</p>

<h1 align="center">
  Trigger
</h1>

<p align="center">
  <strong>Vasileios Evangelos Athanasiou</strong><br>
  Student ID: 19390005
</p>

<p align="center">
  <a href="https://github.com/Ath21" target="_blank">GitHub</a> ·
  <a href="https://www.linkedin.com/in/vasilis-athanasiou-7036b53a4/" target="_blank">LinkedIn</a>
</p>

<hr>

<p align="center">
  <strong>Supervision</strong>
</p>

<p align="center">
  Supervisor: Periklis Andritsos, Associate Professor
</p>
<p align="center">
  <a href="https://ice.uniwa.gr/en/emd_person/periklis-andritsos/" target="_blank">UNIWA Profile</a> ·
  <a href="https://www.linkedin.com/in/periklisandritsos/" target="_blank">LinkedIn</a>
</p>

<p align="center">
  Co-supervisor: Rania Garofalaki, Laboratory Teaching Staff<br>
</p>

<p align="center">
  <a href="https://ice.uniwa.gr/en/emd_person/zacharenia-garofalaki/" target="_blank">UNIWA Profile</a> ·
  <a href="https://www.linkedin.com/in/rania-garofalaki-4761b071/" target="_blank">LinkedIn</a>
</p>

</hr>

---

<p align="center">
  Athens, January 2024
</p>

---

<p align="center">
  <img src="https://www.mysqltutorial.org/wp-content/uploads/2019/09/MySQL-Triggers.png" width="250"/>
</p>

---

# INSTALL

## Trigger

This repository contains a **personnel database project with SQL triggers** developed for the **Databases II** course at the **University of West Attica (UNIWA)**.  
It demonstrates **table creation, sample data insertion, and the implementation of triggers** to automate data updates and validation.

---

## 1. Prerequisites

Before starting, ensure the following software and knowledge are available:

### 1.1 Database Management System (DBMS)

- **MySQL 8.0** (recommended)
- Compatible alternatives:
  - MariaDB
  - PostgreSQL _(minor syntax adjustments may be required)_

### 1.2 SQL Client / Interface

A tool to execute `.sql` scripts and manage the database:

- **MySQL Workbench** (recommended)
- phpMyAdmin
- DBeaver
- Command-line MySQL client

### 1.3 Knowledge Requirements

- SQL basics: `CREATE DATABASE`, `CREATE TABLE`, `INSERT`, `SELECT`, `UPDATE`, `DELETE`
- Understanding of **primary keys, foreign keys, and data types**
- Familiarity with aggregate functions: `SUM()`, `AVG()`, `COUNT()`
- Basic understanding of **triggers** in SQL (BEFORE/AFTER, INSERT/UPDATE/DELETE)

---

## 2. Installation

### 2.1 Clone the Repository

Open a terminal or command prompt and run:

```bash
git clone https://github.com/Data-Bases-2/Trigger.git
```

### 2.2 Alternative (Without Git)

- Open the repository URL in your browser
- Click Code → Download ZIP
- Extract the ZIP file to a local directory

### 2.3 Open SQL Client

- Launch your preferred SQL client (e.g., MySQL Workbench)
- Connect to your local or remote MySQL server

### 2.4 Create the Database

- Execute the following SQL command if the database does not exist:

```sql
CREATE DATABASE IF NOT EXISTS personnel;
USE personnel;
```

### 2.5 Create Tables

Run the provided SQL script src/personnel.sql:

```sql
-- Example for DEPT table
CREATE TABLE DEPT (
    DEPTNO INT PRIMARY KEY,
    DNAME VARCHAR(50),
    LOC VARCHAR(50)
);

-- Example for JOB table
CREATE TABLE JOB (
    JOBCODE INT PRIMARY KEY,
    JOB_DESCR VARCHAR(50),
    SAL INT
);

-- Example for EMP table
CREATE TABLE EMP (
    EMPNO INT PRIMARY KEY,
    NAME VARCHAR(50),
    JOBNO INT,
    DEPTNO INT,
    COMM INT,
    FOREIGN KEY (DEPTNO) REFERENCES DEPT(DEPTNO),
    FOREIGN KEY (JOBNO) REFERENCES JOB(JOBCODE)
);
```

Tip: You can execute the full `personnel.sql` file in one step using your SQL client.

### 2.6 Insert Sample Data

Populate tables with example records using the `INSERT INTO` statements in `personnel.sql` or refer to images in `queries/` for visual guidance.

### 2.7 Create & Test Triggers

The repository includes multiple triggers such as:

- `dept_update` – converts department names to uppercase before updates (`BEFORE UPDATE`)
- Additional triggers for `AFTER INSERT`, `AFTER DELETE`, `AFTER UPDATE` to maintain consistency and logging

Test triggers by performing updates, inserts, or deletes on the corresponding tables.

Example:

```sql
UPDATE DEPT
SET DNAME = 'Accounting'
WHERE DEPTNO = 1;

-- Trigger will automatically convert DNAME to 'ACCOUNTING'
```

### 2.8 Verify Tables and Triggers

Check that tables, data, and triggers exist:

```sql
USE personnel;
SHOW TABLES;
SHOW TRIGGERS;

SELECT * FROM DEPT;
SELECT * FROM JOB;
SELECT * FROM EMP;
```

---

## 3. Open the Documentation

1. Navigate to the `docs/` directory
2. Open the report corresponding to your preferred language:
   - English: `Trigger.pdf`
   - Greek: `Έναυσμα.pdf`
