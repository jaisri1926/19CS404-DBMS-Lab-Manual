# Experiment 4: Aggregate Functions, Group By and Having Clause
## REG NO 212222060086
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
![image](https://github.com/user-attachments/assets/37756c5e-7687-46bf-b4df-38f120a0869d)

```sql
SELECT Address,COUNT(PatientID) AS TotalPatients
FROM Patients
GROUP BY Address;
```

**Output:**

![image](https://github.com/user-attachments/assets/b8111711-622a-44b9-9baf-1982769bec41)


**Question 2**
---
![image](https://github.com/user-attachments/assets/ca8e9d7f-15c1-4c09-871a-56b5efa93c9e)


```sql
SELECT Gender,COUNT(PatientID) AS TotalPatients
FROM Patients
GROUP BY Gender;
```

**Output:**

![image](https://github.com/user-attachments/assets/d8f9e13b-97a3-458a-9d05-2a67538eec8a)


**Question 3**
---
![image](https://github.com/user-attachments/assets/5b696745-9698-4129-834c-0e76b988ca0f)

```sql
SELECT COUNT(city) AS COUNT
FROM customer
WHERE city='Noida';
```

**Output:**

![image](https://github.com/user-attachments/assets/9deabcd6-0385-44b3-b7b2-a5e5c1183959)

**Question 4**
---
![image](https://github.com/user-attachments/assets/c021317c-b266-4f21-88a8-d82444011b5e)


```sql
SELECT COUNT( DISTINCT salesman_id) AS COUNT
FROM orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/2c56ef5c-d9a2-43ea-a541-09b291032c24)


**Question 5**
---
![image](https://github.com/user-attachments/assets/9c14c94a-6504-48bd-a4ce-eabf3be32bc2)

```sql
SELECT name,LENGTH(name) AS length
FROM customer
GROUP BY  length 
ORDER BY length DESC 
LIMIT 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/396bdc11-a18c-4f25-861e-05b0ac51a8da)


**Question 6**
---
![image](https://github.com/user-attachments/assets/6524f3f8-64f0-4c00-9b3b-2b1cf3c40b3c)


```sql
SELECT MAX(price)-MIN(price) AS price_diff
FROM fruits;
```

**Output:**

![image](https://github.com/user-attachments/assets/6b3ddfad-ffe6-4a97-89a0-f2b803ddd718)


**Question 7**
---
![image](https://github.com/user-attachments/assets/13356315-b299-420f-8d63-f98558b3a471)

```sql
SELECT jdate,MIN(workhour) AS 'MIN(workhour)'
FROM employee1
GROUP BY jdate
HAVING MIN(workhour)<10;
```

**Output:**

![image](https://github.com/user-attachments/assets/997f296e-04ad-491a-b3e2-4cc48fc30df4)

**Question 8**
---
![image](https://github.com/user-attachments/assets/0cb64f5c-f775-4f4b-b2ab-099c2c756508)

```sql
SELECT jdate,MAX(workhour) AS 'MAX(workhour)'
FROM employee1
GROUP BY jdate
HAVING MAX(workhour)>12;
```

**Output:**

![image](https://github.com/user-attachments/assets/cb1f3d0e-613e-4d7a-be3b-b44beab9eb21)


**Question 9**
---
![image](https://github.com/user-attachments/assets/cdb6d600-11f6-4da5-b5c7-cf37cade5d43)


```sql
SELECT age ,AVG(income) AS 'AVG(income)'
FROM employee
GROUP BY age
HAVING income BETWEEN 300000 AND 500000;
```

**Output:**

![image](https://github.com/user-attachments/assets/adc84741-0377-4e65-aa20-dc3abe953a69)


**Question 10**
---
![image](https://github.com/user-attachments/assets/154b2c82-1f16-427e-981d-912e5a874dcc)


```sql
SELECT PatientID ,COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID
HAVING TotalRecords>3;
```

**Output:**

![image](https://github.com/user-attachments/assets/f94cd074-7f85-4a96-9810-186d24e94b7b)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
