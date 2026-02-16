<p align="center">
  <img src="https://www.especial.gr/wp-content/uploads/2019/03/panepisthmio-dut-attikhs.png" alt="UNIWA" width="150"/>
</p>

<p align="center">
  <strong>UNIVERSITY OF WEST ATTICA</strong><br>
  SCHOOL OF ENGINEERING<br>
  DEPARTMENT OF COMPUTER ENGINEERING AND INFORMATICS
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

<p align="center">
  Supervisor: Periklis Andritsos, Professor
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

<p align="center">
  Athens, January 2024
</p>

---

# Project Overview

This laboratory exercise focuses on the implementation and testing of **SQL Triggers** within a MySQL environment. The project uses a sample database named `personnel` to demonstrate how triggers can automate data validation and updates.

---

## Table of Contents


| Section | Folder / File | Description |
|------:|---------------|-------------|
| 1 | `assign/` | Laboratory / Assignment material |
| 1.1 | `assign/laboratory_4.pdf` | Laboratory instructions (English) |
| 1.2 | `assign/εργαστήριο_4.pdf` | Laboratory instructions (Greek) |
| 2 | `docs/` | Theoretical documentation |
| 2.1 | `docs/Trigger.pdf` | Triggers theory (English) |
| 2.2 | `docs/Έναυσμα.pdf` | Triggers theory (Greek) |
| 3 | `queries/` | Visual query examples |
| 3.1 | `queries/query10a/b/c.png` | Stepwise trigger creation queries |
| 3.2 | `queries/query11a/b/c/d.png` | Trigger tests and multi-step operations |
| 3.3 | `queries/query12a.1/2.png` | Trigger with conditions / actions |
| 3.4 | `queries/query12b.png` | Another trigger example |
| 3.5 | `queries/query13.png` | Advanced trigger operations |
| 3.6 | `queries/query4a/b.png` | Triggering on different tables |
| 3.7 | `queries/query5-9.png` | Additional trigger examples |
| 4 | `src/` | SQL scripts and related images |
| 4.1 | `src/personnel.sql` | SQL script for personnel database demonstrating triggers |
| 4.2 | `src/personnel.png` | ER diagram / model image |
| 5 | `README.md` | Repository overview and instructions |

---

## Database Schema
The project utilizes the `personnel` database consisting of three primary tables:

1. **DEPT (Department)**  
   Stores department IDs (`DEPTNO`), names (`DNAME`), and locations (`LOC`).

2. **JOB**  
   Contains job codes, descriptions, and salary information.

3. **EMP (Employee)**  
   Manages employee records including IDs, names, job associations, and department assignments.

## Key Activities & Implementation

### 1. Environment Setup
- **Connection:** Accessing MySQL via the command line using root credentials.  
- **Database Creation:** Initializing the `personnel` database and populating it with provided SQL scripts.

### 2. Trigger Implementation
The main focus of the exercise is the creation of various triggers, including:

- **dept_update Trigger**  
  - **Event:** `BEFORE UPDATE` ON `dept`  
  - **Function:** Automatically converts the department name (`DNAME`) to uppercase letters before any update is finalized in the table.

- **Additional Triggers:**  
  Covers triggers awakened by `AFTER INSERT`, `AFTER DELETE`, and `AFTER UPDATE` events to manage related data or maintain logs.

## Project Structure
The documentation is organized into the following sections:

- **Work & Student Details:** Identification and administrative info.  
- **Contents Table:** A detailed roadmap of statements, results, and snapshots for each task.  
- **SQL Scripts:** Full code for table creation and data insertion.  
- **Activities:** Step-by-step execution of the laboratory tasks with screenshots.

---

# Installation & Setup Guide

This repository contains a **personnel database project with SQL triggers** developed for the **Databases II** course at the **University of West Attica (UNIWA)**.  
It demonstrates **table creation, sample data insertion, and the implementation of triggers** to automate data updates and validation.

---

## Prerequisites

Before starting, ensure the following software and knowledge are available:

### 1. Database Management System (DBMS)
- **MySQL 8.0** (recommended)
- Compatible alternatives:
  - MariaDB
  - PostgreSQL *(minor syntax adjustments may be required)*

### 2. SQL Client / Interface
A tool to execute `.sql` scripts and manage the database:
- **MySQL Workbench** (recommended)
- phpMyAdmin
- DBeaver
- Command-line MySQL client

### 3. Knowledge Requirements
- SQL basics: `CREATE DATABASE`, `CREATE TABLE`, `INSERT`, `SELECT`, `UPDATE`, `DELETE`
- Understanding of **primary keys, foreign keys, and data types**
- Familiarity with aggregate functions: `SUM()`, `AVG()`, `COUNT()`
- Basic understanding of **triggers** in SQL (BEFORE/AFTER, INSERT/UPDATE/DELETE)

---

## Installation

### 1. Clone the Repository

Open a terminal or command prompt and run:

```bash
git clone https://github.com/Data-Bases-2/Trigger.git
```

#### Alternative (Without Git)

- Open the repository URL in your browser
- Click Code → Download ZIP
- Extract the ZIP file to a local directory

### 2. Open SQL Client
- Launch your preferred SQL client (e.g., MySQL Workbench)
- Connect to your local or remote MySQL server

### 3. Create the Database
- Execute the following SQL command if the database does not exist:
```sql
CREATE DATABASE IF NOT EXISTS personnel;
USE personnel;
```

### 4. Create Tables
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

### 5. Insert Sample Data
Populate tables with example records using the `INSERT INTO` statements in `personnel.sql` or refer to images in `queries/` for visual guidance.

### 6. Create & Test Triggers
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

### 7. Verify Tables and Triggers
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

## Open the Documentation
1. Navigate to the `docs/` directory
2. Open the report corresponding to your preferred language:
    - English: `Trigger.pdf`
    - Greek: `Έναυσμα.pdf`