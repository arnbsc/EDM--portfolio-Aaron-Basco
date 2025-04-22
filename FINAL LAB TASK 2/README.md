# Finals Lab Task 2. Transforming ER Model to Relational Tables
For this task, we are given an ER diagram representing student assignment submissions, which we need to convert into MySQL tables.

Here’s the Query Statements

Fisrt, a command that create a database as the active database, so subsequent SQL operations will be performed within that specific database.
```sql
CREATE DATABASE student_submissions_db;
USE student_submissions_db;
```
### Student Query Statements
```sql
CREATE TABLE student_table (
    username VARCHAR(50) PRIMARY KEY
);
```
### Assignment Query Statements
```sql
CREATE TABLE assignment_table (
    shortname VARCHAR(50) PRIMARY KEY,
    due_date DATE NOT NULL,
    url VARCHAR(255)
);
```
### Submission Query Statements
```sql
CREATE TABLE submission_table (
    username VARCHAR(50),
    shortname VARCHAR(50),
    version INT,
    submit_date DATE NOT NULL,
    data TEXT,
    PRIMARY KEY (username, shortname, version),
    FOREIGN KEY (username) REFERENCES student_table(username),
    FOREIGN KEY (shortname) REFERENCES assignment_table(shortname)
);
```

Here's the screenshot of Table Structure (See screenshots)

### Student table

  
![Sample Output](images/PRODUCTSSS.PNG)

### Assignment table

  
![Sample Output](images/ASSIGNMENTS.2.PNG)

### Submission table

  
![Sample Output](images/SUBMISSION.2.PNG)

Here's the ER Diagram or Relational Schema

![Sample Output](images/DIAGRAM.2.PNG)
