# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="923" height="603" alt="image" src="https://github.com/user-attachments/assets/0eff21da-a4c8-4de5-aa6c-5dd345b4eeab" />


```sql
select strftime('%H',AppointmentDateTime) as HourOfDay,count(*) as TotalAppointments
from Appointments 
group by HourOfDay;

```

**Output:**

<img width="1164" height="605" alt="image" src="https://github.com/user-attachments/assets/5085013f-91d5-4924-94a4-719d3ec4f19d" />


**Question 2**
---
<img width="1042" height="553" alt="image" src="https://github.com/user-attachments/assets/eb55404c-93a4-4b10-9a6a-9ab6d32df1db" />


```sql
select DoctorID,count(*) as TotalAppointments
from Appointments
group by DoctorID;
```

**Output:**

<img width="1118" height="700" alt="image" src="https://github.com/user-attachments/assets/a6ed48bd-3d10-46b4-b866-2c6719d694ad" />


**Question 3**
---
<img width="1066" height="457" alt="image" src="https://github.com/user-attachments/assets/a594b200-fa18-4d2d-b75f-c0eff8e706ac" />


```sql
select Gender,count(*) as TotalPatients
from Patients
group by Gender;
```

**Output:**
<img width="1187" height="428" alt="image" src="https://github.com/user-attachments/assets/560b0810-276a-4610-8deb-9281b887c19f" />


**Question 4**
---
<img width="1097" height="495" alt="image" src="https://github.com/user-attachments/assets/f5bbbe35-bb7b-4e1d-b7a2-eb7ea1ef5427" />


```sql
select count(*) as employees_in_california
from employee
where city='California';
```

**Output:**

<img width="1178" height="393" alt="image" src="https://github.com/user-attachments/assets/5d9d43ef-e941-4a8d-a082-12382e6fa2b6" />


**Question 5**
---
<img width="1058" height="462" alt="image" src="https://github.com/user-attachments/assets/a5927cf9-5199-4817-a2c0-6ca18874abba" />


```sql
select name,email,min(length(email)) as min_email_length
from customer

```

**Output:**

<img width="1148" height="389" alt="image" src="https://github.com/user-attachments/assets/fe60cf22-40ff-48db-82cd-a94feed12da8" />


**Question 6**
---
<img width="1018" height="453" alt="image" src="https://github.com/user-attachments/assets/d591a648-b95e-4d5c-8cfe-6d2ddfd43e70" />


```sql
select avg(length(email)) as avg_email_length_below_30
from customer
where city='Mumbai';
```

**Output:**

<img width="1112" height="379" alt="image" src="https://github.com/user-attachments/assets/a5db837d-7984-49ab-ac6b-e9a8e124de81" />


**Question 7**
---
<img width="978" height="491" alt="image" src="https://github.com/user-attachments/assets/593f3d91-60cc-4873-a5a8-f47a5ac4bcfc" />


```sql
select count(*) as COUNT
from customer

```

**Output:**

<img width="1152" height="388" alt="image" src="https://github.com/user-attachments/assets/35a4ce8f-b8ab-4339-b1ec-a453179e03b2" />


**Question 8**
---
<img width="1216" height="465" alt="image" src="https://github.com/user-attachments/assets/3cb9a8ec-4b81-4c25-bcd2-aa09f59f6144" />


```sql
select age,avg(income) as 'AVG(income)'
from employee
group by age
having AVG(income) between 300000 and 500000;
```

**Output:**

<img width="1193" height="394" alt="image" src="https://github.com/user-attachments/assets/09174f33-641e-47b1-ab3a-a4e56e6a717a" />


**Question 9**
---
<img width="1206" height="552" alt="image" src="https://github.com/user-attachments/assets/8aafc204-0fc0-4385-95d2-1a2e5bcf2eba" />


```sql
select (age/5)*5 as age_group,max(salary) as 'MAX(salary)'
from customer1
group by age_group
having MAX(salary) > 8000;
```

**Output:**

<img width="994" height="432" alt="image" src="https://github.com/user-attachments/assets/89970286-3f7d-4a85-8261-694a453e910d" />


**Question 10**
---
<img width="1222" height="451" alt="image" src="https://github.com/user-attachments/assets/dceb7a24-8cb1-40b6-8c59-d0659b8168bb" />


```sql
select (age/5)*5 as age_group,avg(age) as 'AVG(age)'
from customer1
group by age_group
having AVG(age) < 24;
```

**Output:**

<img width="1192" height="384" alt="image" src="https://github.com/user-attachments/assets/dd36e989-5c4f-47de-b3e2-224a9483b02e" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
