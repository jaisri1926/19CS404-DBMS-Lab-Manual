# Experiment 2: DDL Commands
## REG NO 212222060086
## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/50a8b6dd-34ae-4631-ade6-80f98bd9aea9)

```sqlCREATE TABLE Locations(
LocationID INTEGER,
LocationName TEXT ,
Address TEXT
)
```

**Output:**

![image](https://github.com/user-attachments/assets/b3f636fd-8ed1-4fca-b15a-16ec5afbd7af)


**Question 2**
---
![image](https://github.com/user-attachments/assets/84952341-ee4a-4254-a1b8-b9e48be3ffdc)

```sql
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
VALUES('001','Sarah Parker','Manager','HR',60000)
```

**Output:**

![image](https://github.com/user-attachments/assets/0cfda077-4fd0-4a30-80c5-edd38986b385)


**Question 3**
---
![image](https://github.com/user-attachments/assets/57eaf5e1-a73b-42ed-a6d5-a71668088223)


```sql
CREATE TABLE Products(
ProductID PRIMARY KEY,
ProductName NOT NULL,
Price REAL CHECK(Price>0),
Stock INTEGER CHECK(Stock>0)
)
```

**Output:**

![image](https://github.com/user-attachments/assets/daaaa50a-6d61-4d9e-acbc-bde9abbd33b6)


**Question 4**
---
![image](https://github.com/user-attachments/assets/68f1e30e-d807-4098-ba56-dbd897e8e1fe)

```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),

FOREIGN KEY  (icom_id) REFERENCES company(com_id)
    ON UPDATE SET NULL
    ON DELETE SET NULL
)
```

**Output:**

![image](https://github.com/user-attachments/assets/0b965b37-76a0-42de-aa53-998cbf84736f)

**Question 5**
---
![image](https://github.com/user-attachments/assets/ccbc362a-6316-42ce-bb57-718c367d9505)


```sql
INSERT INTO Books(ISBN,Title,Author,Publisher,YearPublished)
SELECT ISBN,Title,Author,Publisher,YearPublished
FROM Out_of_print_books
```

**Output:**

![image](https://github.com/user-attachments/assets/a13df169-60e6-47a6-8e4e-eac507128817)

**Question 6**
---
![image](https://github.com/user-attachments/assets/09c4277b-71f4-4d8c-89d0-e7150dc1802f)


```sql
ALTER TABLE customer
ADD COLUMN birth_date timestamp
```

**Output:**

![image](https://github.com/user-attachments/assets/14af2e3f-a7f7-4857-b95f-0fd6663007d3)


**Question 7**
---
![image](https://github.com/user-attachments/assets/4c1c7cd1-8953-4c22-b827-ce2e1cef2825)


```sql
ALTER TABLE Companies
ADD COLUMN designation varchar(50);

ALTER TABLE Companies
ADD COLUMN net_salary number;

ALTER TABLE Companies
ADD COLUMN dob date;
```

**Output:**

![image](https://github.com/user-attachments/assets/af8ef81e-ea00-400b-9481-3e969a0e7e92)


**Question 8**
---
![image](https://github.com/user-attachments/assets/022d2ddb-6f73-440e-a73b-5efd42ce4800)


```sql
CREATE TABLE products(
product_id INTEGER PRIMARY KEY,
product_name TEXT NOT NULL,
list_price DECIMAL(10 ,2) NOT NULL,
discount DECIMAL(10,2) NOT NULL DEFAULT 0,
CHECK(list_price>=discount and discount>=0 and list_price >=0)
)
```

**Output:**

![image](https://github.com/user-attachments/assets/7ec2928e-86e2-45e0-b628-6d4d6ee2aff2)


**Question 9**
---
![image](https://github.com/user-attachments/assets/9fa7c934-b779-4935-ae97-c0f568a9b5be)


```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY (icom_id) REFERENCES company(com_id)
    ON UPDATE CASCADE
    ON DELETE CASCADE
)
```

**Output:**

![image](https://github.com/user-attachments/assets/6c26658c-0894-4532-ba81-5bc2407760e0)


**Question 10**
---
![image](https://github.com/user-attachments/assets/58f100bc-d374-4256-83a3-cb7dd8d5e0f5)


```sql
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE
)
```

**Output:**

![image](https://github.com/user-attachments/assets/6e42dfc9-b494-497f-a9fc-73afa502bf53)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
