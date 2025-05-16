# Experiment 3: DML Commands
## REG NO 212222060086
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
![image](https://github.com/user-attachments/assets/77e7c180-15d5-4a17-bfe0-cd8826a1311e)


```sql
UPDATE products
SET availability=availability*2
WHERE product_id=1;
```

**Output:**

![image](https://github.com/user-attachments/assets/5dcf14cf-51f1-4733-adbb-2a611cd5371c)

**Question 2**
---
![image](https://github.com/user-attachments/assets/d297f706-21ab-4513-b0bb-4245be275006)


```sql
UPDATE Employees
SET SALARY = SALARY * 2
WHERE job_id ='MK_MAN' and department_id=20;
```

**Output:**

![image](https://github.com/user-attachments/assets/4af1e624-2e53-4e21-af37-04d06e26d18a)


**Question 3**
---
![image](https://github.com/user-attachments/assets/b48a0c3a-0a6a-416b-9527-af44958705f2)


```sql
UPDATE suppliers
SET supplier_name=UPPER(supplier_name)
WHERE contact_person LIKE '%Singh%'
```

**Output:**

![image](https://github.com/user-attachments/assets/1b306d7f-36b9-4619-964e-787e0ed48438)


**Question 4**
---
![image](https://github.com/user-attachments/assets/5082d2df-9bb1-46f3-94b0-f05b3ceb9ff8)

```sql
UPDATE Products
SET sell_price=CAST(cost_price*1.35 AS INTEGER)
WHERE((sell_price-cost_price)/sell_price)<0.30;
```

**Output:**

![image](https://github.com/user-attachments/assets/71742fa9-7c2c-4307-b754-46185a0adcd1)


**Question 5**
---
![image](https://github.com/user-attachments/assets/db0d1f5c-cf63-402e-b1a2-5ccb146aaeed)

```sql
DELETE FROM Customer
WHERE (GRADE IS '2' AND CUST_NAME LIKE 'M%') AND PAYMENT_AMT <5000;
```

**Output:**

![image](https://github.com/user-attachments/assets/b4467cc8-d4ed-46b9-89bb-2b1c1b07cc5a)


**Question 6**
---
![image](https://github.com/user-attachments/assets/5afe1ca2-552f-40e8-907f-a7f19043c5ce)


```sql
DELETE FROM Customer
WHERE CUST_COUNTRY NOT IN ('UK','USA','Canada') AND GRADE >=3;
```

**Output:**

![image](https://github.com/user-attachments/assets/4151936f-8796-4ed8-93bb-354f15e6fbb4)


**Question 7**
---
![image](https://github.com/user-attachments/assets/ae221a67-c027-48a1-9193-2b84721a13db)


```sql
DELETE FROM Doctors
WHERE doctor_id =1;
```

**Output:**

![image](https://github.com/user-attachments/assets/6ab91afd-ffca-46b0-875b-a3414146ca71)

**Question 8**

---![image](https://github.com/user-attachments/assets/b507383c-b0c9-4442-9197-82aeccf245f6)


```sql
DELETE FROM Customer
WHERE CUST_CITY <> 'New York' AND OUTSTANDING_AMT>5000;
```

**Output:**

![image](https://github.com/user-attachments/assets/ead903a4-acbc-4aab-8f89-7f054b21eccc)


**Question 9**
---
![image](https://github.com/user-attachments/assets/57c2b5ae-7888-4d7e-9f68-de24751191d8)


```sql
SELECT EmpID, EmpFname,EmpLname,Department,Project,Address,DOB,Gender
FROM EmployeeInfo
WHERE EmpLname LIKE '____A'  ;
```

**Output:**

![image](https://github.com/user-attachments/assets/a26a1f94-67e0-4983-8f79-1f6d5e045051)


**Question 10**
---
![image](https://github.com/user-attachments/assets/314db1a1-7f93-48a0-b7d8-39db74270529)


```sql
SELECT salesman_id,name,city,commission
FROM salesman
WHERE commission BETWEEN 0.12 AND 0.14;
```

**Output:**

![image](https://github.com/user-attachments/assets/ea0e58f6-0c26-447f-8c26-ed1121d67303)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
