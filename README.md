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

# README

## Trigger

This laboratory exercise focuses on the implementation and testing of **SQL Triggers** within a MySQL environment. The project uses a sample database named `personnel` to demonstrate how triggers can automate data validation and updates.

---

## Table of Contents

| Section | Folder / File                | Description                                              |
| ------: | ---------------------------- | -------------------------------------------------------- |
|       1 | `assign/`                    | Laboratory / Assignment material                         |
|     1.1 | `assign/laboratory_4.pdf`    | Laboratory instructions (English)                        |
|     1.2 | `assign/εργαστήριο_4.pdf`    | Laboratory instructions (Greek)                          |
|       2 | `docs/`                      | Theoretical documentation                                |
|     2.1 | `docs/Trigger.pdf`           | Triggers theory (English)                                |
|     2.2 | `docs/Έναυσμα.pdf`           | Triggers theory (Greek)                                  |
|       3 | `queries/`                   | Visual query examples                                    |
|     3.1 | `queries/query10a/b/c.png`   | Stepwise trigger creation queries                        |
|     3.2 | `queries/query11a/b/c/d.png` | Trigger tests and multi-step operations                  |
|     3.3 | `queries/query12a.1/2.png`   | Trigger with conditions / actions                        |
|     3.4 | `queries/query12b.png`       | Another trigger example                                  |
|     3.5 | `queries/query13.png`        | Advanced trigger operations                              |
|     3.6 | `queries/query4a/b.png`      | Triggering on different tables                           |
|     3.7 | `queries/query5-9.png`       | Additional trigger examples                              |
|       4 | `src/`                       | SQL scripts and related images                           |
|     4.1 | `src/personnel.sql`          | SQL script for personnel database demonstrating triggers |
|     4.2 | `src/personnel.png`          | ER diagram / model image                                 |
|       5 | `README.md`                  | Project documentation                                    |
|       6 | `INSTALL.md`                 | Usage instructions                                       |

---

## 1. Database Schema

The project utilizes the `personnel` database consisting of three primary tables:

1. **DEPT (Department)**  
   Stores department IDs (`DEPTNO`), names (`DNAME`), and locations (`LOC`).

2. **JOB**  
   Contains job codes, descriptions, and salary information.

3. **EMP (Employee)**  
   Manages employee records including IDs, names, job associations, and department assignments.

## Key Activities & Implementation

### 1.1 Environment Setup

- **Connection:** Accessing MySQL via the command line using root credentials.
- **Database Creation:** Initializing the `personnel` database and populating it with provided SQL scripts.

### 1.2 Trigger Implementation

The main focus of the exercise is the creation of various triggers, including:

- **dept_update Trigger**
  - **Event:** `BEFORE UPDATE` ON `dept`
  - **Function:** Automatically converts the department name (`DNAME`) to uppercase letters before any update is finalized in the table.

- **Additional Triggers:**  
  Covers triggers awakened by `AFTER INSERT`, `AFTER DELETE`, and `AFTER UPDATE` events to manage related data or maintain logs.

---

## 2. Project Structure

The documentation is organized into the following sections:

- **Work & Student Details:** Identification and administrative info.
- **Contents Table:** A detailed roadmap of statements, results, and snapshots for each task.
- **SQL Scripts:** Full code for table creation and data insertion.
- **Activities:** Step-by-step execution of the laboratory tasks with screenshots.
