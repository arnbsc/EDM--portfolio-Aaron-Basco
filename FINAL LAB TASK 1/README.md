# Final Lab Task 1. Multi Level Company Database 
This project contains a basic relational database design for managing employee-related information in a company.
It includes employees, departments, managers, and their relationships with projects and departments.
---

## Database: MultiLevel_company

### Employees Table

This table stores employee records and their managers.
```sql
CREATE TABLE employees_table (
    employee_id INT(5) UNIQUE AUTO_INCREMENT PRIMARY KEY,
    employee_name VARCHAR(255) NOT NULL,
    manager_id INT(5),
    FOREIGN KEY (manager_id) REFERENCES employees_table(employee_id)
);
```
### EMPLOYEES TABLE STRUCTURE

![sample Output](images/TASK1.2.PNG)

---

### Departments Table

This table contains information about each department within the company.
```sql
CREATE TABLE departments_table (
    department_id INT(5) UNIQUE AUTO_INCREMENT PRIMARY KEY,
    department_name VARCHAR(255) NOT NULL
);
```
### DEPARTMENTS TABLE STRUCTURE
![sample Output](images/TASK2.2.PNG)

---

### Employee_Departments Table

This table links employees to their departments, establishing many-to-many relationships.
```sql
CREATE TABLE employee_departments_table (
    employee_id INT,
    department_id INT,
    FOREIGN KEY (employee_id) REFERENCES employees_table(employee_id),
    FOREIGN KEY (department_id) REFERENCES departments_table(department_id)
);
```
### EMPLOYEES_DEPARTMENTS TABLE STRUCTURE
![sample Output](images/TASK3.2.PNG)

---

### Task 4: Employee_Projects Table
This table keeps track of projects assigned to each employee.
```sql
CREATE TABLE employee_projects_table (
    employee_id INT,
    project_name VARCHAR(255) NOT NULL,
    FOREIGN KEY (employee_id) REFERENCES employees_table(employee_id)
);
```
### EMPLOYEES_PROJECTS TABLE STRUCTURE
![sample Output](images/TASK4.2.PNG)

---

### Task 5: Managers Table
This table stores manager information, linking them back to employee records.
```sql
CREATE TABLE managers_table (
    manager_id INT UNIQUE AUTO_INCREMENT PRIMARY KEY,
    employee_id INT,
    FOREIGN KEY (employee_id) REFERENCES employees_table(employee_id)
);
```
### MANAGERS TABLE STRUCTURE
![sample Output](images/TASK5.2.PNG)

### EER Diagram
This diagram shows a visual representation of the relationships among the tables.
![sample Output](images/EER.2.PNG)
