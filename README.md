#  Employee Database SQL Project

##  Project Overview
This project demonstrates SQL skills including database creation, table relationships, and data management using constraints.

---

##  Tools Used
- MySQL

---

##  Database Creation

```sql
CREATE DATABASE employee;
USE employee;
```

---

##  Table Creation

### Departments Table
```sql
CREATE TABLE DEPARTMENTS (
    DEPARTMENT_ID INT AUTO_INCREMENT PRIMARY KEY,
    DEPARTMENT_NAME VARCHAR(50) NOT NULL UNIQUE
);
```

### Locations Table
```sql
CREATE TABLE LOCATIONS (
    LOCATION_ID INT AUTO_INCREMENT PRIMARY KEY,
    LOCATION_NAME VARCHAR(50) NOT NULL UNIQUE
);
```

### Employees Table
```sql
CREATE TABLE EMPLOYEES (
    EMPLOYEE_ID INT AUTO_INCREMENT PRIMARY KEY,
    EMPLOYEE_NAME VARCHAR(50) NOT NULL,
    GENDER CHAR(1),
    AGE INT,
    HIRE_DATE DATE DEFAULT (CURRENT_DATE),
    DESIGNATION VARCHAR(50),
    SALARY INT,
    DEPARTMENT_ID INT,
    LOCATION_ID INT,
    CHECK (GENDER IN ('M','F')),
    CHECK (AGE >= 18),
    FOREIGN KEY (DEPARTMENT_ID) REFERENCES DEPARTMENTS(DEPARTMENT_ID),
    FOREIGN KEY (LOCATION_ID) REFERENCES LOCATIONS(LOCATION_ID)
);
```

---

##  Table Alter Operations

```sql
ALTER TABLE EMPLOYEES ADD EMAIL VARCHAR(50);
ALTER TABLE EMPLOYEES MODIFY DESIGNATION VARCHAR(50);
ALTER TABLE EMPLOYEES DROP COLUMN AGE;
ALTER TABLE EMPLOYEES RENAME COLUMN HIRE_DATE TO DATE_OF_JOINING;
```

---

##  Table Management

```sql
RENAME TABLE Department TO Departments_Info;
RENAME TABLE Location TO Locations;
TRUNCATE TABLE EMPLOYEES;
DROP TABLE EMPLOYEES;
```

---

##  Database Management

```sql
DROP DATABASE IF EXISTS employee;
CREATE DATABASE employee;
```

---

##  Key Features
- Database creation and management  
- Table relationships using Foreign Keys  
- Data validation using CHECK constraints  
- Table modification using ALTER commands  

---

##  Learning Outcomes
- Strong understanding of SQL DDL commands  
- Hands-on experience with constraints and relationships  
- Database design fundamentals  

![Alt text] ()
