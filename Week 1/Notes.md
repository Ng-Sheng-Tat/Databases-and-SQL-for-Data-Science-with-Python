## Week 1
- data is stored in a tabular format (Relational Database)
- Basics SQL Commands
  1. Create a table
  2. Insert
  3. Select
  4. Update
  5. Delete
---
**SELECT** statement
- retrieve the stored data for more information
```
Select statement: Query
Select * from <tablename>
Select <column(s),> from <tablename> WHERE column name = "somethings"
```
---
- **Count** functions
```
Select COUNT(column) from tablename where column="Canada"
```
---
- **DISTINCT** functions - used to remove duplicate values from a result set
```
select DISTINCT columnname from tablename where condition
```
---
- **LIMIT** functions - used to restrict the number of rows retrieved from the database
```
select * from tablename LIMIT 10
```
---
- **Insert** Statement
```
INSERT INTO tablename
  <columnname(s),>
VALUES([Value(s),])
```
---
- **UPDATE** Statement
```
UPDATE [Tablename]
SET [[Columnname]=[Value]]
<WHERE [Condition]>
```
- if there is no WHERE clause, all values will change accordingly
---
- **DELETE** Statement
```
DELETE from tablename where [Condition]
```
---
- **Create** statement
```
CREATE TABLE table_name(
  col1 datatype, like int, datetime, varchar(40)...
  col2 datatype,

  ...,
  PRIMARY KEY(column)
);
```
