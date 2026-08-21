# Experiment 3: DML Commands
## NAME:MADHUSHRI 
## REG NO:212224040178
## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
Write a SQL query to remove rows from the table 'customer' with the following condition -

1. 'cust_country' must be 'India',

2. 'cus_city' must not be 'Chennai',
```sql
DELETE FROM Customer
WHERE cust_country ='India'
AND cust_city != 'Chennai';
```

**Output:**

<img width="1180" height="880" alt="image" src="https://github.com/user-attachments/assets/4df1af68-7edd-4b53-9bc7-b2b28109bff0" />


**Question 2**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_CITY' is not 'New York' and 'OUTSTANDING_AMT' is greater than 5000.

```sql
DELETE FROM customer
WHERE CUST_CITY != 'New York'
AND OUTSTANDING_AMT > 5000;
```

**Output:**
<img width="1182" height="582" alt="image" src="https://github.com/user-attachments/assets/69a40e06-88aa-401d-9bce-2564405d2e12" />


**Question 3**
---
Write a SQL query to calculate the discounted price for products where the discount percentage is greater than 0, and order the results by discounted_price in ascending order. Return product_id, original_price, discount_percentage, and discounted_price.

Sample table: Products

```sql
SELECT product_id,
original_price,discount_percentage,
original_price-(original_price*discount_percentage)AS discounted_price
FROM Products
WHERE discount_percentage > 0
ORDER BY discounted_price ASC;
```

**Output:**

<img width="1181" height="263" alt="image" src="https://github.com/user-attachments/assets/d958b8e6-db62-4afb-a9e0-98391d71dfec" />


**Question 4**
---
Write a SQL query to Get the employees whose name starts and ends with the same two characters:

Table name: emp

```sql
SELECT ename
FROM emp
WHERE LOWER(SUBSTR(ename,1,2))=LOWER(SUBSTR(ename,-2));
```

**Output:**

<img width="456" height="290" alt="image" src="https://github.com/user-attachments/assets/cb2df168-f0a6-4736-b9ec-a80c4b4f951b" />


**Question 5**
---
Write a SQL query to assess the performance of value2 as 'Poor', 'Average', or 'Excellent' based on whether it is less than 30, between 30 and 70, or greater than 70 in the Calculations table

```sql
SELECT id,
value2,
CASE 
WHEN value2<30 THEN 'Poor'
WHEN value2>=30 AND value2<70 THEN 'Average'
ELSE 'Excellent'
END AS performance
FROM Calculations;
```

**Output:**


<img width="814" height="416" alt="image" src="https://github.com/user-attachments/assets/fec30ca2-5ddc-4f02-8da5-1cec6adb2282" />

**Question 6**
---
Write a SQL query to display hire dates in the format "DD-MM-YYYY" from the emp table

```sql
SELECT ename,
strftime('%d-%m-%Y',hiredate)AS HireDateFormatted
FROM emp;
```

**Output:**

<img width="722" height="350" alt="image" src="https://github.com/user-attachments/assets/a042fa14-65e9-4278-87dd-56a718e01e21" />

**Question 7**
---

Write a SQL statement to Display names and city of salesman, who belongs to the city of London or Rome.
```sql
SELECT name,city
FROM salesman
WHERE city = 'London' 
OR city='Rome';

```

**Output:**


<img width="594" height="342" alt="image" src="https://github.com/user-attachments/assets/eabc6be0-a7aa-48d7-86fa-dc53196c3fcc" />



**Question 8**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_NAME' has exactly 6 characters.

```sql
DELETE FROM customer
WHERE LENGTH(CUST_NAME)=6;
```

**Output:**

<img width="1179" height="722" alt="image" src="https://github.com/user-attachments/assets/a1948272-ef02-481d-8e63-8b9512999c6c" />


**Question 9**
---
Write a SQL query to Delete all Doctors whose Specialization is either 'Pediatrics' or 'Cardiology' and Last Name is Brown.



```sql
DELETE FROM doctors
WHERE last_name='Brown'
AND specialization IN ('Pediatrics','Cardiology'); 
```

**Output:**

<img width="1183" height="923" alt="image" src="https://github.com/user-attachments/assets/5ae9cb31-8cc1-46bf-88fc-436f948f5d28" />


**Question 10**
---
Write a SQL query to calculate the discounted price for each product. Return product_id, original_price, discount_percentage, and discounted_price.
```sql
SELECT 
product_id,original_price,
discount_percentage,
original_price-(original_price*discount_percentage) AS discounted_price
FROM Products;
```

**Output:**

<img width="1176" height="432" alt="image" src="https://github.com/user-attachments/assets/f2d8ab73-73ef-4ca5-b3f6-3279ebe38b06" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
