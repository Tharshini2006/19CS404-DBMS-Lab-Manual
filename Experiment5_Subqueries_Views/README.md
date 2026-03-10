# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="1088" height="331" alt="image" src="https://github.com/user-attachments/assets/705d1afb-f428-4785-85ac-b14365d6498b" />


```sql
select medication_id,medication_name,dosage
from medications
where dosage=(
      select max(dosage)
      from medications
);
```

**Output:**

<img width="1006" height="533" alt="image" src="https://github.com/user-attachments/assets/626f575f-45f7-4875-8108-d12085f25713" />


**Question 2**
---
<img width="1279" height="376" alt="image" src="https://github.com/user-attachments/assets/7edc2c32-31a0-4105-afbd-b5c60c98bc33" />


```sql
select *
from employee 
where age <(
    select avg(age)
    from employee
    where income > 250000
);
```

**Output:**

<img width="1266" height="646" alt="image" src="https://github.com/user-attachments/assets/8c41647b-1858-4714-84a5-18fcfde6b148" />


**Question 3**
---
<img width="1234" height="434" alt="image" src="https://github.com/user-attachments/assets/66694f37-3e38-4e7a-a179-49b811b2a74f" />


```sql
select *
from customers
where address='Delhi' and age < 30
order by id;
```

**Output:**

<img width="1252" height="510" alt="image" src="https://github.com/user-attachments/assets/aa860957-ef20-4c34-a601-ee72e414755c" />


**Question 4**
---
<img width="1210" height="564" alt="image" src="https://github.com/user-attachments/assets/f114787f-56e1-448a-97b4-e9f0d1546a01" />


```sql
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders
where salesman_id in (
    select salesman_id
    from salesman
    where city='New York'
);
```

**Output:**

<img width="1267" height="591" alt="image" src="https://github.com/user-attachments/assets/9274091d-9983-4db7-87be-7c790639b26c" />


**Question 5**
---
<img width="1178" height="305" alt="image" src="https://github.com/user-attachments/assets/fa24b9c7-d2ea-4d8e-aff2-a7e469faae05" />


```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT distinct phone
    FROM customer
    group by phone
    HAVING COUNT(*) = 1
   
);
```

**Output:**
<img width="895" height="594" alt="image" src="https://github.com/user-attachments/assets/6b466f29-12b6-4e26-8984-cbe042c868a4" />


**Question 6**
---
<img width="1241" height="389" alt="image" src="https://github.com/user-attachments/assets/ecdf4521-5b04-490c-af39-9b8c142216ae" />


```sql
select *
from orders
where purch_amt >(
select avg(purch_amt)
from orders
where ord_date='2012-10-10');
```

**Output:**

<img width="1257" height="591" alt="image" src="https://github.com/user-attachments/assets/71095907-eced-4062-ab3e-bb5f9031132a" />


**Question 7**
---
<img width="1050" height="440" alt="image" src="https://github.com/user-attachments/assets/57a04c32-19a1-497a-a0d4-fc1496cc6e90" />


```sql
select *
from customers
where address='Delhi'
```

**Output:**

<img width="1256" height="468" alt="image" src="https://github.com/user-attachments/assets/7229c7f7-595e-43cb-9a2f-2995e5820866" />


**Question 8**
---
<img width="1165" height="288" alt="image" src="https://github.com/user-attachments/assets/85e8f294-d2f3-4689-9995-dcd5d2ecda37" />


```sql
select name,city
from customer
where city in (
  select city
  from customer
  where id in (3,7));
```

**Output:**
<img width="901" height="606" alt="image" src="https://github.com/user-attachments/assets/21b093f0-a6ce-49f8-9347-5274c854d3f1" />


**Question 9**
---
<img width="1149" height="449" alt="image" src="https://github.com/user-attachments/assets/66bd58c9-f80f-499d-9505-452771d67620" />


```sql
select *
from customers
where salary > 1500;
```

**Output:**

<img width="1241" height="746" alt="image" src="https://github.com/user-attachments/assets/60d131d5-46f5-49fc-b382-3e9b85fc375c" />


**Question 10**
---
<img width="1239" height="442" alt="image" src="https://github.com/user-attachments/assets/84f347d0-f63a-4cb8-a010-6ca51827a28b" />


```sql
select student_name,grade
from grades g1
where grade=(
     select min(grade)
     from grades g2
     where g1.subject = g2.subject
);
```

**Output:**

<img width="903" height="570" alt="image" src="https://github.com/user-attachments/assets/3abd4e29-c1f5-4b84-b2ae-1f532f919a42" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
