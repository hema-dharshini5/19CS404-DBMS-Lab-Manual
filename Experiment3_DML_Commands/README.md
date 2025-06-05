# Experiment 3: DML Commands

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


Question 1
Write a SQL statement to update the product_name as 'Grapefruit' whose product_id is 4 in the products table.

update products
set product_name='Grapefruit'
where product_id=4;

## Output:
![image](https://github.com/user-attachments/assets/4d2534ab-7446-4405-960d-7765406df49f)


Question 2
Write a SQL query to reduce the reorder level by 30% where cost price is more than 50 and quantity in stock is less than 100 in the products table.

update Products
set reorder_lvl=reorder_lvl*0.7
where cost_price>50 and quantity<100;

## Output:
![image](https://github.com/user-attachments/assets/8b416d0c-dbbd-41af-8c80-ea594f7e49a6)


Question 3
Write a SQL query to Delete a Specific Surgery which was made on 28th Feb 2024.

delete from Surgeries 
where surgery_date='2024-02-28';

## Output:
![image](https://github.com/user-attachments/assets/bae9dbf7-2c92-44df-832a-39dbf8abbfb4)

Question 4
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.

delete from customer
where GRADE!=3;

## Output:
![image](https://github.com/user-attachments/assets/75d2e18f-a81e-4ac8-a796-020917adfd7e)


Question 5
Write a query to fetch details of employees whose EmpLname ends with an alphabet ‘A’ and contains five alphabets.

select * from EmployeeInfo 
where EmpLname like '%A' and length(EmpLname)=5;

## Output:
![image](https://github.com/user-attachments/assets/a15fb95d-6743-4981-9014-0be76035db44)


Question 6
Write a SQL query to classify base in the Calculations table as 'Provided' if it is not NULL, otherwise 'Not Provided'.

select id,base,
case when base is not NULL then 'Provided'
else 'Not Provided'
end as base_status
from Calculations;

## Output:
![image](https://github.com/user-attachments/assets/4387bbce-385d-4310-805e-02615d16ecb3)


Question 7
Write a SQL query to calculate the final price after applying both the discount and the tax. Return product_id, original_price, discount_percentage, tax_rate, and final_price.

select product_id,original_price,discount_percentage,tax_rate,(original_price*(1-discount_percentage))*(1+tax_rate) as final_price
from products;

## Output:
![image](https://github.com/user-attachments/assets/7a6b02c7-1d2c-43cd-bc25-32703c525786)


Question 8
Create a report that shows the capitalized FirstName and capitalized LastName renamed as FirstName and Lastname respectively and EmployeeId from the employees table sorted by EmployeeId in descending order.

select upper(FirstName) AS FirstName,upper(LastName) AS LastName,EmployeeId
from employees
order by EmployeeID desc;

## Output:
![image](https://github.com/user-attachments/assets/f6ca425e-359a-4bb1-b953-b14f5edecbcf)


Question 9
Write a SQL statement to retrieve city(column name) of all customers from customers table without any repeats.

select distinct city from customers;

## Output:
![image](https://github.com/user-attachments/assets/f7c9016f-37a3-46b4-837e-a340d8bc3912)

Question 10
Write a SQL statement to Double the salary for employees in department 20 who have a job_id ending with 'MAN'

update EMPLOYEES
SET SALARY= SALARY *2
WHERE JOB_ID like'%MAN';

## Output:
![image](https://github.com/user-attachments/assets/848a5e53-571f-4896-b2d0-01e997732aa8)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
