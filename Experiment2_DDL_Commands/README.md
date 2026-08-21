# Experiment 2: DDL Commands
## NAME:MADHUSHRI
## REG NO:212224040178
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
Create a table named Products with the following columns:

ProductID as INTEGER
ProductName as TEXT
Price as REAL
Stock as INTEGER

```sql
CREATE TABLE Products(
ProductID INTEGER,
ProductName TEXT,
Price REAL,
Stock INTEGER
);
```
**Output:**
<img width="1187" height="299" alt="image" src="https://github.com/user-attachments/assets/9072db1c-a9fe-4b1e-a264-970a4e2fe61b" />



**Question 2**
---
Insert all customers from Old_customers into Customers

Table attributes are CustomerID, Name, Address, Email

```sql
INSERT INTO Customers(CustomerID, Name, Address, Email)
SELECT CustomerID, Name, Address, Email
FROM Old_customers
```

**Output:**

<img width="1177" height="271" alt="image" src="https://github.com/user-attachments/assets/4e06706a-bf0a-4e6a-b1cb-0bc57e282457" />


**Question 3**
---
Write a SQL query to Add a new ParentsNumber column  as number and Adhar_Number as Number in the Student_details table.

```sql
ALTER TABLE Student_details ADD ParentsNumber number;
ALTER TABLE Student_details ADD Adhar_Number number;

```

**Output:**


<img width="1181" height="369" alt="image" src="https://github.com/user-attachments/assets/5e51962e-22d2-4a45-8cb5-a3079d76da43" />


**Question 4**
---

Write a SQL query to Add a new column Country as text in the Student_details table.

```sql

ALTER TABLE Student_details ADD Country TEXT;
```

**Output:**

<img width="1175" height="350" alt="image" src="https://github.com/user-attachments/assets/bd5480e9-e80d-40ef-89e0-8d4e3e9beb38" />



**Question 5**
---
Create a table named Attendance with the following constraints:
AttendanceID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
AttendanceDate as DATE.
Status as TEXT should be one of 'Present', 'Absent', 'Leave'.

```sql
CREATE TABLE Attendance(
AttendanceID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
AttendanceDate DATE,
Status TEXT CHECK (Status IN('Present','Absent','Leave')),
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

<img width="1187" height="269" alt="image" src="https://github.com/user-attachments/assets/0840cf6a-867e-4b4a-b5c3-50fbcf336d19" />



**Question 6**
---
Insert a product with ProductID 104, Name Tablet, and Category Electronics into the Products table, where Price and Stock should use default values.

```sql
INSERT INTO Products (ProductID,Name,Category)
VALUES(104,'Tablet','Electronics');```

**Output:**


<img width="1177" height="226" alt="image" src="https://github.com/user-attachments/assets/0bcbc500-3f46-41f6-b8bc-88188cb0d2a5" />


**Question 7**
---
Create a table named Tasks with the following columns:

TaskID as INTEGER
TaskName as TEXT
DueDate as DATE

```sql
CREATE TABLE Tasks(
TaskID INTEGER,
TaskName TEXT,
DueDate DATE
);
```

**Output:**

<img width="1179" height="359" alt="image" src="https://github.com/user-attachments/assets/c11afacd-90bc-4885-a15d-18dbc98337e1" />


**Question 8**
---
Insert a new product with ProductID 101, Name Laptop, Category Electronics, Price 1500, and Stock 50 into the Products table.

```sql
INSERT INTO Products (ProductID,Name,Category,Price,Stock)
VALUES(101,'Laptop','Electronics',1500,50);
```

**Output:**


<img width="1181" height="216" alt="image" src="https://github.com/user-attachments/assets/d6810f55-1e1b-4356-acd7-d1934d0d528b" />


**Question 9**
---
Create a table named Shipments with the following constraints:
ShipmentID as INTEGER should be the primary key.
ShipmentDate as DATE.
SupplierID as INTEGER should be a foreign key referencing Suppliers(SupplierID).
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).

```sql
CREATE TABLE Shipments(
ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderId INTEGER,
FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierId),
FOREIGN KEY (OrderId)REFERENCES Orders(OrderID)

);
```

**Output:**


<img width="1186" height="215" alt="image" src="https://github.com/user-attachments/assets/c79f6409-ba3f-40fe-9baf-0caf04d92142" />


**Question 10**
---
Create a table named Bonuses with the following constraints:
BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.

```sql
CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
BonusAmount REAL CHECK (BonusAmount>0),
BonusDate DATE,
Reason TEXT NOT NULL,
FOREIGN KEY (EmployeeID)REFERENCES
Employees(EmployeeID)
);
```

**Output:**



<img width="1186" height="259" alt="image" src="https://github.com/user-attachments/assets/0c702860-ea95-4cf3-b8ef-d5cebd486fe8" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
