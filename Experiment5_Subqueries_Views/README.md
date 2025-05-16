# Experiment 5: Subqueries and Views
## REG NO 212222060086

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
![image](https://github.com/user-attachments/assets/e9a72a41-7053-435d-a4dc-e04540f83550)


```sql
SELECT grade ,COUNT(*) 
FROM customer
GROUP BY grade
HAVING grade >(SELECT AVG(grade)
FROM customer
WHERE city = 'New York');

```

**Output:**

![image](https://github.com/user-attachments/assets/38f30979-1c23-47ad-abc7-5bc84e4130d8)


**Question 2**
---
![image](https://github.com/user-attachments/assets/44422299-908d-4c77-a622-ed557f8135c3)

```sql
SELECT department_id as depar, department_name
FROM departments
WHERE LENGTH(department_name) > (
    SELECT AVG(LENGTH(department_name)) FROM departments
);

```

**Output:**

![image](https://github.com/user-attachments/assets/5649da48-a4c4-40a0-86d5-6c4b6e88bf1a)


**Question 3**
---
![image](https://github.com/user-attachments/assets/57411d66-813c-4357-871a-12c7512ae60d)


```sql
SELECT * FROM GRADES g
WHERE g.grade=(SELECT MAX(grade)
               FROM GRADES
              WHERE subject=g.subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/bcdecc2d-bc08-47aa-8df4-0ec7d3c080da)

**Question 4**
---
![image](https://github.com/user-attachments/assets/d9e74360-e0eb-43c6-9046-5e68b97a054d)


```sql
SELECT * FROM Employee
WHERE age <(
SELECT AVG(age)
FROM Employee
WHERE income>1000000);
```

**Output:**

![image](https://github.com/user-attachments/assets/a5c17249-4ab4-4f95-8e07-1a18bbda8f59)


**Question 5**
---
![image](https://github.com/user-attachments/assets/0aeffc25-c9da-4542-9abc-45682193567b)


```sql
SELECT * FROM CUSTOMERS
WHERE ADDRESS ='Delhi';
```

**Output:**

![image](https://github.com/user-attachments/assets/12fb318b-03db-4b93-ab78-86cfd12f7d41)


**Question 6**
---
![image](https://github.com/user-attachments/assets/6fc4131d-f767-435e-ad19-dc30777848de)


```sql
SELECT o.ord_no,o.purch_amt,o.ord_date,o.customer_id,o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id=s.salesman_id
WHERE s.city = 'London';
```

**Output:**

![image](https://github.com/user-attachments/assets/065fd996-6ce9-4397-aa23-3a4dae997994)


**Question 7**
---
![image](https://github.com/user-attachments/assets/fec01f32-2c10-490f-848c-1d4c5445e8bd)


```sql
SELECT s.salesman_id,s.name
FROM salesman s
JOIN customer c ON s.salesman_id=c.salesman_id
GROUP BY s.salesman_id,s.name
HAVING COUNT(c.customer_id)>1;
```

**Output:**

![image](https://github.com/user-attachments/assets/ea8bb494-5685-4fb0-9566-39d6cff6c414)

**Question 8**
---
![image](https://github.com/user-attachments/assets/1a28747e-ee74-42ae-b4a5-052008a48c1e)


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.commission = (
    SELECT MAX(commission) FROM salesman
);

```

**Output:**

![image](https://github.com/user-attachments/assets/911f2bb7-dc33-4fd8-88b8-7865407eed46)


**Question 9**
---
![image](https://github.com/user-attachments/assets/535692be-5c2f-4181-8d8c-a94eef462e90)


```sql
SELECT * FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**

![image](https://github.com/user-attachments/assets/17e73b89-95e7-4906-97a9-ec76be7ddc05)


**Question 10**
---
![image](https://github.com/user-attachments/assets/1cededae-eeea-45c8-b2ee-0fd8741be5ba)


```sql
SELECT customer_id,cust_name,city,grade,salesman_id
FROM customer
WHERE customer_id = (SELECT salesman_id -2001
FROM salesman
WHERE name = 'Mc Lyon')
```

**Output:**

![image](https://github.com/user-attachments/assets/b82fa723-47bb-4a2e-bad1-f7743941bf43)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
