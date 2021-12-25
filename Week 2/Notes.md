## Week 2
- entities/instances are table representations
- attributes of the instances will be the columns of the table
- each table has unique primary keys which identify the specific rows and prevents duplication of data
- each foreign keys provide a link to which tables can be related to each others
- Types of SQL Statements
  1. **Data Definition Language (DDL)** is used to define, change, and drop data
  - Common DDL includes **CREATE, ALTER, TRUNCATE, DROP**
  2. **Data Manipulation Language (DML)** is used to read and modify data, they do the **CRUD** operations
    - **CREATE, READ, UPDATE, DELETE rows**
- **CREATE** table
```
CREATE TABLE table_name
  (
    column_name_1 datatype optional_parameters,
    column_name_2 datatype,
    ...
    column_name_n datatype
    )
(PRIMARY KEY) NOT NULL - as the parameters to ensure unique for primary keys
examples include
char(n)
varchar(n)
```
---
- **ALTER** and **DROP** Statement
  - used to add or remove columns
  - modify the data type of columns
  - add or remove keys
  - add or remove constraints
```
ALTER TABLE <tablename>
  ADD COLUMN <column_name_1> datatype

  ADD COLUMN <column_name_2> SET DATA TYPE
CHAR(n);

  DROP COLUMN column_name_3

  DROP TABLE tablename
  ...
  ADD COLUMN <column_name_n> datatype
```
- **TRUNCATE** statement - removes all the data inside a table except column names
```
TRUNCATE TABLE tablename
  IMMEDIATE;
```
