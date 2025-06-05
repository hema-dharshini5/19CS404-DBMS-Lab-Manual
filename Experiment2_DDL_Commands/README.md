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

Question 1

Write a SQL query to modify the Student_details table by adding a new column Email of type VARCHAR(50) and updating the column MARKS to have a default value of 0.

ALTER TABLE Student_details ADD COLUMN Email VARCHAR(50); ALTER TABLE Student_details ADD COLUMN MARKS DEFAULT '0';

## Output:
![image](https://github.com/user-attachments/assets/eccda2cc-71ec-4a1d-936c-5f0c60a7a733)


Question 2

Create a new table named contacts with the following specifications: contact_id as INTEGER and primary key. first_name as TEXT and not NULL. last_name as TEXT and not NULL. email as TEXT. phone as TEXT and not NULL with a check constraint to ensure the length of phone is at least 10 characters.

CREATE TABLE contacts ( contact_id INT PRIMARY KEY, first_name TEXT NOT NULL, last_name TEXT NOT NULL, email TEXT, phone TEXT NOT NULL, CHECK (LENGTH(phone)>=10) );

## Output:
![image](https://github.com/user-attachments/assets/f28966ff-bae6-4687-a445-d00c60675e88)


Question 3

Insert all books from Out_of_print_books into Books

Table attributes are ISBN, Title, Author, Publisher, YearPublished

INSERT INTO Books(ISBN, Title, Author, Publisher, YearPublished) SELECT ISBN, Title, Author, Publisher, YearPublished FROM Out_of_print_books;

## Output:
![image](https://github.com/user-attachments/assets/c04509c8-39c6-4a68-927f-9509effc72d0)


Question 4
Create a table named Departments with the following columns:

DepartmentID as INTEGER DepartmentName as TEXT

CREATE TABLE Departments( DepartmentID INTEGER, DepartmentName TEXT);

## Output:
![image](https://github.com/user-attachments/assets/99f55c04-d8f3-49a8-ab0c-29d3900191b9)


Question 5

Write an SQL query to add two new columns, department_id and manager_id, to the table employee with datatype of INTEGER. The manager_id column should have a default value of NULL.

ALTER TABLE employee ADD COLUMN department_id INTEGER; ALTER TABLE employee ADD COLUMN manager_id INTEGER DEFAULT NULL;

## Output:
![image](https://github.com/user-attachments/assets/76979743-2bd7-4360-a2b9-6dc2f3abfe54)


Question 6
Insert all customers from Old_customers into Customers

Table attributes are CustomerID, Name, Address, Email

INSERT INTO Customers(CustomerID, Name, Address, Email) SELECT CustomerID, Name, Address, Email FROM Old_customers;6

## Output:
![image](https://github.com/user-attachments/assets/9cf20062-df49-42c7-b0fe-b411cfdfb05e)


Question 7
---Write a SQL query to Add a new column named "discount" with the data type DECIMAL(5,2) to the "customer" table.

Sample table: customer

customer_id | cust_name | city | grade | salesman_id -------------+----------------+------------+-------+------------- 3002 | Nick Rimando | New York | 100 | 5001 3007 | Brad Davis | New York | 200 | 5001 3005 | Graham Zusi | California | 200 | 5002

ALTER TABLE customer ADD COLUMN discount DECIMAL(5,2);

## Output:
![image](https://github.com/user-attachments/assets/0d1222d4-3e7f-4f4d-b71f-f57b3e78f03f)


Question 8
Create a table named Members with the following columns:

MemberID as INTEGER MemberName as TEXT JoinDate as DATE

create table Members( MemberID INTEGER, MemberName TEXT, JoinDate DATE );

## Output:
![image](https://github.com/user-attachments/assets/06250af9-46a4-437f-acfb-618055ac8a65)


Question 9
Write a SQL query to add birth_date attribute as timestamp (datatype) in the table customer

Sample table: customer

customer_id | cust_name | city | grade | salesman_id -------------+----------------+------------+-------+------------- 3002 | Nick Rimando | New York | 100 | 5001 3007 | Brad Davis | New York | 200 | 5001 3005 | Graham Zusi | California | 200 | 5002

alter table customer add column birth_date timestamp;

## Output:
![image](https://github.com/user-attachments/assets/5b83ac6e-6eef-42b8-b285-af87ff211d38)


Question 10
Insert the below data into the Student_details table, allowing the Subject and MARKS columns to take their default values.

RollNo Name Gender

204 Samuel Black M

Note: The Subject and MARKS columns will use their default values.

insert into Student_details(RollNo,Name,Gender) values(204,"Samuel Black","M");

## Output:
![image](https://github.com/user-attachments/assets/795d1abe-e335-464a-b7e8-e3d002e20c43)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

