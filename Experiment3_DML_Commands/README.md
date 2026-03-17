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
**Question 1**
--
Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.
```
Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id
```
```sql
update Products
set product_name='Premium Bread'
where product_id=5;
```

**Output:**

![image](https://github.com/user-attachments/assets/50f94cb4-a7a0-4644-b789-bc2870890d42)

**Question 2**
---
Write a SQL statement to Increase the salary by 500 and email as 'updated' for employees with job ID 'SA_REP' and commission percentage greater than 0.15
```
Employees table

---------------
employee_id
first_name
last_name
email
phone_number
hire_date
job_id
salary
commission_pct
manager_id
department_id
```
```sql
update Employees 
set salary=salary+500 , email="updated"
where job_id='SA_REP' and commission_pct>0.15;
```

**Output:**

![image](https://github.com/user-attachments/assets/4d129003-6999-4d65-bea2-6d24cbdb3892)


**Question 3**
---
Write a SQL statement to Increase quantity of all products by 10% to adjust for surplus stock counted
```
Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id
```
```sql
update Products 
set quantity =quantity*1.10;
```

**Output:**


![image](https://github.com/user-attachments/assets/89c3534c-b9cb-4d8f-83b5-69145b67f2b7)


**Question 4**
---
Update the 'Selling_Price' to add 10% extra margin for all products supplied by the supplier with id 6.
```
PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT
```
```sql
update PRODUCTS 
set sell_price= ROUND(sell_price*1.10)
where supplier_id=6;
```

**Output:**


![image](https://github.com/user-attachments/assets/e8609d3e-a2ac-40b4-8c9b-87419fa09547)


**Question 5**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.

```sql
delete from Customer 
where grade!=3;
```

**Output:**


![image](https://github.com/user-attachments/assets/8915b676-d031-4a66-9a74-1c88d30c598c)


**Question 6**
---
Write a SQL query to Delete customers from 'customer' table where 'AGENT_CODE' is either 'A003' or 'A008'.

```sql
delete from Customer 
where agent_code IN ('A003','A008');
```

**Output:**


![image](https://github.com/user-attachments/assets/a76d8ac6-326e-49e9-8558-d0e667f8b7d7)

**Question 7**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is greater than or equal to 2.

```sql
DELETE from Customer 
where grade>=2;
```

**Output:**


![image](https://github.com/user-attachments/assets/ca5f7d2f-d198-48f6-a44f-78759d0d9720)


**Question 8**
---
Write a SQL statement to Display the order number, orderdate and the purchase amount of
orders table which will be delivered by the salesman with ID 5001.
```
orders table

name                 type
---------------     ---------------
order_no            int
purch_amt         real
order_date        text
customer_id      int
salesman_id      int
```
```sql
select order_no,order_date,purch_amt from orders
where salesman_id=5001;
```

**Output:**


![image](https://github.com/user-attachments/assets/d8a1972f-2831-45f7-85f8-b9e331489bc5)


**Question 9**
---
Write a SQL query to retrieve all orders where the purchase amount is between 500 and 4000 but exclude orders with purchase amounts of 948.50 and 1983.43. The query should return the columns: ord_no, purch_amt, ord_date, customer_id, and salesman_id.

```sql
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders 
where purch_amt between 500 and 4000 and 
purch_amt not in (948.50,1983.43) ;
```

**Output:**


![image](https://github.com/user-attachments/assets/70485493-8fa3-422f-bea8-c471aa187dda)


**Question 10**
---
Write a SQL query to find employees who were hired after January 1, 2020.
```
emp table

cid         name        type        
----------  ----------  ---------- 
0           empno       INT         
1           ename       VARCHAR(100)
2           job         VARCHAR(50)
3           mgr         INT        
4           hiredate    DATE        
5           sal         DECIMAL(10,2)  
6           comm        DECIMAL(10,2)  
7           deptno      INT  
```
```sql
select * from emp 
where hiredate>'2020-01-01';
```

**Output:**


![image](https://github.com/user-attachments/assets/968426ef-b104-470c-98f5-7610d8db80b0)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.


![image](https://github.com/user-attachments/assets/b8cfa823-6981-459a-814a-c8a408cb0191)

