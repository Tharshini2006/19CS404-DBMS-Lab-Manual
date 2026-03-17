# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1278" height="694" alt="image" src="https://github.com/user-attachments/assets/8c1644db-791d-456e-b181-cee63b1ae98e" />

```sql
SELECT p.*
FROM patients p
INNER JOIN appointments a
ON p.patient_id = a.patient_id
WHERE a.appointment_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

<img width="1287" height="529" alt="image" src="https://github.com/user-attachments/assets/49e124cd-a99f-4f9d-ab7e-c5ea636424bd" />

**Question 2**
---
<img width="1278" height="431" alt="image" src="https://github.com/user-attachments/assets/764172d6-ad52-451d-a9f8-31367e01eb1c" />

```sql
SELECT s.name,
       c.cust_name,
       c.city,
       c.grade,
       c.salesman_id
FROM salesman s
LEFT JOIN customer c
ON s.salesman_id = c.salesman_id
WHERE c.grade <= 100;
```

**Output:**

<img width="1288" height="656" alt="image" src="https://github.com/user-attachments/assets/15ab819a-f026-4137-a35c-a1b25f4fc754" />

**Question 3**
---
<img width="1277" height="738" alt="image" src="https://github.com/user-attachments/assets/3153f48d-8586-4278-85c3-fcdf64710893" />

```sql
SELECT p.date_of_birth, a.*
FROM patients p
INNER JOIN appointments a
ON p.patient_id = a.patient_id
WHERE p.first_name = 'Alice';
```

**Output:**

<img width="1289" height="507" alt="image" src="https://github.com/user-attachments/assets/4d261778-7ae2-49fa-b71f-b4a2b06a41af" />

**Question 4**
---
<img width="1273" height="893" alt="image" src="https://github.com/user-attachments/assets/30d0244b-5a16-445d-b879-7a574427cf85" />

```sql
SELECT s.name AS Salesman,
       c.cust_name,
       s.city
FROM salesman s
JOIN customer c
ON s.city = c.city;
```

**Output:**

  <img width="1287" height="788" alt="image" src="https://github.com/user-attachments/assets/f43cbae1-b990-436b-be2e-b5c5d7da4bad" />

**Question 5**
---
<img width="1266" height="356" alt="image" src="https://github.com/user-attachments/assets/d5827b88-6909-4677-84a4-30f0d113c425" />

```sql
SELECT s.name
FROM salesman s
LEFT JOIN customer c
ON s.salesman_id = c.salesman_id
WHERE c.city = 'New York';
```

**Output:**

<img width="1296" height="489" alt="image" src="https://github.com/user-attachments/assets/7c956bad-3995-4d61-b321-fb862a051153" />

**Question 6**
---
<img width="1313" height="779" alt="image" src="https://github.com/user-attachments/assets/d0b62de2-8645-42b6-add8-a183e0f9fe58" />

```sql
SELECT o.ord_no,
       o.purch_amt,
       c.cust_name,
       c.city
FROM orders o
JOIN customer c
ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

<img width="1304" height="502" alt="image" src="https://github.com/user-attachments/assets/9300d72f-354e-49ae-b967-ecffa419db98" />

**Question 7**
---
<img width="1317" height="816" alt="image" src="https://github.com/user-attachments/assets/9b99ca46-765f-48af-871e-8770f6457ae7" />

```sql
SELECT c.cust_name AS "Customer Name",
       c.city,
       s.name AS "Salesman",
       s.city,
       s.commission
FROM customer c
JOIN salesman s
ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
AND s.commission > 0.12;
```

**Output:**

<img width="1297" height="649" alt="image" src="https://github.com/user-attachments/assets/d69c2662-7b00-4222-8aab-1ea7fa6c1a81" />

**Question 8**
---
<img width="1320" height="902" alt="image" src="https://github.com/user-attachments/assets/780f50aa-33ff-48e4-89e4-eab081cd91a5" />

```sql
SELECT c.cust_name,
       c.city,
       o.ord_no,
       o.ord_date,
       o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;
```

**Output:**

<img width="1314" height="929" alt="image" src="https://github.com/user-attachments/assets/b2fea17b-efe6-4cc5-b413-a982c6c59467" />

**Question 9**
---
<img width="1323" height="595" alt="image" src="https://github.com/user-attachments/assets/c26630d0-e000-48ab-b71f-fcc6df5a5b48" />

```sql
SELECT p.first_name AS patient_name,
       t.*
FROM patients p
INNER JOIN test_results t
ON p.patient_id = t.patient_id;
```

**Output:**

<img width="1328" height="522" alt="image" src="https://github.com/user-attachments/assets/01b69d0f-fbb2-4a8f-a9ce-5313287d5cf3" />

**Question 10**
---
<img width="1328" height="750" alt="image" src="https://github.com/user-attachments/assets/1606a337-ec8a-4547-baf8-cb552064c8df" />

```sql
SELECT c.cust_name AS "Customer Name",
       c.city,
       s.name AS "Salesman",
       s.commission
FROM customer c
JOIN salesman s
ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;
```

**Output:**

<img width="1332" height="683" alt="image" src="https://github.com/user-attachments/assets/2dd3d576-7246-4a54-8d82-1c85abe06f28" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
