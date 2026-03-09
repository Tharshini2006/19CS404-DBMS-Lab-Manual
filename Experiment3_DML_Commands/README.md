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
<img width="1137" height="646" alt="image" src="https://github.com/user-attachments/assets/2988aa34-e72c-4925-89b6-8216afb4b348" />


```sql
update employees
set email='Unavailable'
```

**Output:**

<img width="1241" height="518" alt="image" src="https://github.com/user-attachments/assets/115a30f2-89da-45e5-9a54-a221b81ed6cf" />


**Question 2**
---
<img width="978" height="540" alt="image" src="https://github.com/user-attachments/assets/05db9ec9-b659-469f-b719-f8263fcfeb12" />


```sql
update products
set reorder_lvl=40
where category='Grocery';
```

**Output:**
<img width="1246" height="471" alt="image" src="https://github.com/user-attachments/assets/f24aa036-5362-4c51-b4b2-528b3d8d3649" />


**Question 3**
---
<img width="1050" height="487" alt="image" src="https://github.com/user-attachments/assets/ba79236f-8b89-443c-af89-5a8a7b29ba0f" />


```sql
update suppliers
set address='58 Lakeview, Magnolia' 
where supplier_id=5;
```

**Output:**
<img width="1238" height="476" alt="image" src="https://github.com/user-attachments/assets/21c0f8e6-8b68-40c1-b066-b6d5d1c6dc34" />


**Question 4**
---
<img width="1058" height="289" alt="image" src="https://github.com/user-attachments/assets/608d8b79-200d-4866-a1cd-491157acc93e" />


```sql
update sales
set sell_price=sell_price*1.05
where sale_date='2023-01-31' and product_id=15;
```

**Output:**

<img width="1247" height="529" alt="image" src="https://github.com/user-attachments/assets/1712e993-943a-4e6c-bd1a-0b152dc95530" />


**Question 5**
---
<img width="1236" height="599" alt="image" src="https://github.com/user-attachments/assets/d0d44374-fce8-4249-a8d0-b7073b4b8679" />


```sql
update products
set reorder_lvl=reorder_lvl*0.7
where product_name like '%cream%' and quantity > reorder_lvl;
```

**Output:**

<img width="1222" height="551" alt="image" src="https://github.com/user-attachments/assets/118f138b-aca3-4b17-9ec0-a42e3994bf9b" />


**Question 6**
---
<img width="1242" height="484" alt="image" src="https://github.com/user-attachments/assets/8b4109c3-9793-4b5e-bf28-3945b79c1b3e" />


```sql
delete from customer
where CUST_COUNTRY='UK' and WORKING_AREA= 'London' and GRADE < 3;
```

**Output:**

<img width="1218" height="544" alt="image" src="https://github.com/user-attachments/assets/fe8bea82-ce84-418e-95b7-77dc5b59453d" />


**Question 7**
---
<img width="925" height="655" alt="image" src="https://github.com/user-attachments/assets/3c3633a1-f5cd-447e-a07c-ae2037dc37e1" />


```sql
delete from surgeries
where surgery_id=3 or surgeon_id =4;
```

**Output:**

<img width="1212" height="885" alt="image" src="https://github.com/user-attachments/assets/127d05d4-c078-4cfb-ae65-a47eff5a2dda" />


**Question 8**
---
<img width="957" height="421" alt="image" src="https://github.com/user-attachments/assets/33d92c1a-d413-4e2a-bec5-2d4529612747" />


```sql
select COUNT(*)
from employeeinfo
where Department='HR';
```

**Output:**

<img width="1122" height="293" alt="image" src="https://github.com/user-attachments/assets/4676411b-b14f-4379-a517-9844fc3d5c7c" />


**Question 9**
---
<img width="1005" height="604" alt="image" src="https://github.com/user-attachments/assets/89027323-5132-4d82-95a0-20c93f9236cd" />


```sql
select id,value1,abs(value1)as absolute_value
from calculations;
```

**Output:**

<img width="929" height="365" alt="image" src="https://github.com/user-attachments/assets/8bb3439a-a245-4ebe-9645-eece0bd08b5b" />


**Question 10**
---
<img width="1168" height="586" alt="image" src="https://github.com/user-attachments/assets/b5d90b31-f483-40f1-ac67-fb00af53d975" />


```sql
select  product_id, original_price, discount_percentage, original_price *(1-discount_percentage) as discounted_price
from products
where discount_percentage > 0
order by discounted_price asc;
```

**Output:**

<img width="1236" height="358" alt="image" src="https://github.com/user-attachments/assets/42b7a49b-da27-417b-ba1f-81bbf324e853" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
