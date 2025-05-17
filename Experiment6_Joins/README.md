# Experiment 6: Joins
## REG NO 212222060086
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
![image](https://github.com/user-attachments/assets/1efa0642-545d-4d1d-aea9-7171946209a9)


```sql
SELECT t.*
FROM PATIENTS p
INNER JOIN test_results t ON p.patient_id=t.patient_id
WHERE p.first_name='Alice';
```

**Output:**

![image](https://github.com/user-attachments/assets/ceade5d4-f796-4149-bdae-e5397e2b7005)


**Question 2**
---
![image](https://github.com/user-attachments/assets/3fc146dc-4c70-47de-a6ed-f1d994e5070b)


```sql
SELECT s.name AS Salesman,c.cust_name,c.city
FROM salesman s
JOIN customer c on s.city=c.city;
```

**Output:**

![image](https://github.com/user-attachments/assets/1891cbe3-7c68-4c86-8091-b53522c26d2d)

**Question 3**
---
![image](https://github.com/user-attachments/assets/98ccf471-7dcf-497f-8a73-92372eaa05cf)


```sql
SELECT c.cust_name AS "Customer Name",c.city,s.name AS "Salesman",s.commission
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/99aed16f-dada-4be9-976d-6126d1ccf856)


**Question 4**
---
![image](https://github.com/user-attachments/assets/d195b2d2-d996-474d-8e6e-3cf289f5b91c)


```sql
SELECT c.cust_name,c.city,c.grade,s.name AS "Salesman",s.city
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id
ORDER BY c.customer_id ASC;
```

**Output:**

![image](https://github.com/user-attachments/assets/eca18e28-9e54-46a0-b5d7-d9f77d317da7)


**Question 5**
---
![image](https://github.com/user-attachments/assets/654f14d3-8157-47b1-9a96-bcb2fae10299)


```sql
SELECT o.ord_no,o.purch_amt,c.cust_name,c.city
FROM orders o
JOIN customer c ON o.customer_id=c.customer_id
WHERE o.purch_amt BETWEEN 500 and 2000;
```

**Output:**

![image](https://github.com/user-attachments/assets/575d4ebe-90e4-4f77-8b42-e85f6c17a747)


**Question 6**
---
![image](https://github.com/user-attachments/assets/cf819f89-d3d0-43bd-9832-70fc6c541fca)


```sql
SELECT p.date_of_birth,a.appointment_id,p.patient_id,p.doctor_id,a.appointment_date
FROM patients p
INNER JOIN appointments a ON p.patient_id=a.patient_id
WHERE p.first_name='Alice';
```

**Output:**

![image](https://github.com/user-attachments/assets/3c0c5fb1-483d-4911-845d-57bfa443ba4a)


**Question 7**
---
![image](https://github.com/user-attachments/assets/c39014db-9cbc-4310-9a70-e0fa81389030)


```sql
SELECT p.first_name,s.surgery_id,p.patient_id,s.surgeon_id,s.surgery_date
FROM patients p
INNER JOIN surgeries s ON p.patient_id=s.patient_id
WHERE p.date_of_birth >'1990-01-01';
```

**Output:**

![image](https://github.com/user-attachments/assets/d3807a5f-534d-4485-8087-ed7d9f18e801)


**Question 8**
---
![image](https://github.com/user-attachments/assets/eb3edea6-4878-400c-84d7-5ba67b5a1247)


```sql
SELECT c.cust_name FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/d43911a9-7c2a-435f-9a92-a6f3440882bd)

**Question 9**
---
![image](https://github.com/user-attachments/assets/e0473447-a5d7-4531-84b0-4eae8cce547c)


```sql
SELECT c.* FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id
WHERE o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';
```

**Output:**

![image](https://github.com/user-attachments/assets/c8744d7d-1c0a-4bd2-95d5-0975ce049817)


**Question 10**
---
![image](https://github.com/user-attachments/assets/67cc0e3f-d069-4ea6-8e06-4a107186b955)


```sql
SELECT c.cust_name FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id
WHERE o.purch_amt<100;
```

**Output:**
---
![Screenshot (106)](https://github.com/user-attachments/assets/3605dcd0-be68-4d8e-9cee-c9c8281a34de)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
