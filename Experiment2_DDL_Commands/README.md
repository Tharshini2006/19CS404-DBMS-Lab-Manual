# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="1241" height="347" alt="image" src="https://github.com/user-attachments/assets/4ecc53e5-fa75-41a5-b0b6-56eef2bbf0c4" />


```sql
INSERT INTO Books(ISBN,Title,Author,Publisher,YearPublished)
select * from Out_of_print_books;
```

**Output:**

<img width="1238" height="373" alt="image" src="https://github.com/user-attachments/assets/dfcc7d65-4768-44d0-894e-58bfd125c9be" />


**Question 2**
---
<img width="1232" height="404" alt="image" src="https://github.com/user-attachments/assets/0b5bdd4b-612a-4172-9ef8-1a4066b4c124" />


```sql
CREATE TABLE Products(
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT UNIQUE NOT NULL,
    Price REAL CHECK (Price > 0),
    StockQuantity INTEGER CHECK (StockQuantity > 0)
);
```

**Output:**

<img width="1250" height="360" alt="image" src="https://github.com/user-attachments/assets/13736b35-5449-4921-b695-b63812c113df" />


**Question 3**
---
<img width="1240" height="374" alt="image" src="https://github.com/user-attachments/assets/386b81c6-c72d-4774-bebc-16a166b653b1" />


```sql
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
VALUES
(2,'John Smith','Developer','IT',75000),
(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="1243" height="430" alt="image" src="https://github.com/user-attachments/assets/e2d97db1-09f4-4015-9587-508b7b3de8bc" />


**Question 4**
---
<img width="1228" height="477" alt="image" src="https://github.com/user-attachments/assets/24c7eab8-207c-4da4-bf03-0df47a1bea5e" />


```sql
INSERT INTO Student_details(RollNo,Name,Gender)
VALUES(204,'Samuel Black','M');
```

**Output:**

<img width="1248" height="389" alt="image" src="https://github.com/user-attachments/assets/bfa69548-6c0d-403e-97e0-46a45653b9b5" />


**Question 5**
---
<img width="1242" height="470" alt="image" src="https://github.com/user-attachments/assets/0dbc490c-8aeb-4434-a348-400b08383078" />


```sql
CREATE TABLE Invoices(
    InvoiceID INTEGER PRIMARY KEY,
    InvoiceDate DATE,
    Amount REAL CHECK (Amount > 0),
    DueDate DATE CHECK (DueDate > InvoiceDate),
    OrderID INTEGER ,
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**

<img width="1244" height="365" alt="image" src="https://github.com/user-attachments/assets/aebae5c1-6a3b-4ed7-8c6a-64cdf47cfaef" />


**Question 6**
---
<img width="1197" height="470" alt="image" src="https://github.com/user-attachments/assets/f3f5be9a-0409-41aa-9008-fff8d9fd5e8d" />


```sql
ALTER TABLE books
ADD COLUMN ISBN varchar(30);
ALTER TABLE books
ADD COLUMN domain_dept varchar(30);
```

**Output:**

<img width="1250" height="465" alt="image" src="https://github.com/user-attachments/assets/efcc39fa-d1b9-40fa-bcf8-1c469a83d3dc" />


**Question 7**
---
<img width="1218" height="303" alt="image" src="https://github.com/user-attachments/assets/a959bd67-7b83-48d7-9fa3-8065011dd492" />


```sql
ALTER TABLE employee
ADD COLUMN designation varchar(50);
```

**Output:**

<img width="1240" height="352" alt="image" src="https://github.com/user-attachments/assets/9e9210d2-41f7-4913-b1df-9ef323284d3c" />


**Question 8**
---
<img width="1260" height="426" alt="image" src="https://github.com/user-attachments/assets/0a05ac97-72ce-4632-acc8-7e46bdb6e128" />


```sql
CREATE TABLE Bonuses(
    BonusID INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    BonusAmount REAL CHECK (BonusAmount > 0),
    BonusDate DATE,
    Reason TEXT NOT NULL,
    FOREIGN KEY(EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

<img width="1238" height="362" alt="image" src="https://github.com/user-attachments/assets/83545994-5028-41a5-a54d-7b827d6465b8" />


**Question 9**
---
<img width="1166" height="453" alt="image" src="https://github.com/user-attachments/assets/d4f6b4a2-ae19-4c82-8232-b3c2216e9d2a" />


```sql
CREATE TABLE Products(
    ProductID INTEGER,
    ProductName TEXT,
    Price REAL,
    Stock INTEGER
);
```

**Output:**

<img width="1225" height="377" alt="image" src="https://github.com/user-attachments/assets/bc1e8e86-0013-4a2c-8b47-573728c018de" />


**Question 10**
---
<img width="1251" height="444" alt="image" src="https://github.com/user-attachments/assets/f7ef15d2-254b-4dd9-97ba-1fdf01c39fb8" />


```sql
CREATE TABLE Employees(
    EmployeeID PRIMARY KEY,
    FirstName NOT NULL,
    LastName NOT NULL,
    Email UNIQUE,
    Salary INTEGER CHECK (Salary > 0),
    DepartmentID INT,
    FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**

<img width="1247" height="519" alt="image" src="https://github.com/user-attachments/assets/6f773baa-2eb1-4ffd-af96-c03955246c50" />




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
