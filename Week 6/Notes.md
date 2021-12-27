## Week 6
- **views** is a subset of tables that is light-weight
- syntax is as follows
```
CREATE VIEW <VIEWNAME> (<column_alias_1>, ... <column_alias_n) AS SELECT <column_1>, <column_2>, ...<column_n> FROM <tablename> WHERE <predicate>

CREATE OR REPLACE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
- dropping a view
`` DROP VIEW view_name``
---
- stored procedure, produces are transmitted in a pack (like a function)
```
--#SET TERMINATOR @
CREATE PROCEDURE RETRIEVE_ALL       -- Name of this stored procedure routine

LANGUAGE SQL                        -- Language used in this routine
READS SQL DATA                      -- This routine will only read data from the table

DYNAMIC RESULT SETS 1               -- Maximum possible number of result-sets to be returned to the caller query

BEGIN

    DECLARE C1 CURSOR               -- CURSOR C1 will handle the result-set by retrieving records row by row from the table
    WITH RETURN FOR                 -- This routine will return retrieved records as a result-set to the caller query

    SELECT * FROM PETSALE;          -- Query to retrieve all the records from the table

    OPEN C1;                        -- Keeping the CURSOR C1 open so that result-set can be returned to the caller query

END
@                                   -- Routine termination character
```
- calling procedure
`` CALL procedure_name(input(s))``
---
**Transactions** either one operations all occur or none of them occurs
- **ACID** transactions
    1. Atomic: All changes must be performed successfully or not at all
    2. Consistent: Data must be in a consistent state before and after the transaction
    3. Isolated: No other process can change the data while the transaction is running
    4. Durable: The changes made by the transaction must persist
```
BEGIN
    bulks of operations
COMMIT or ROLLBACK
```
---
**JOIN** operators
- combine rows from tables based on a relationship
- **PRIMARY KEY**  uniquely identifies each row in a table
- **FOREIGN KEY** refers to a primary key of another tables
- types of join include Inner join, Outer join (Left, Right, Full)
---
**INNER Join** Syntax
```
SELECT alias1.column_name_1, alias1.column_name_2, alias2.column_name_1, alias2.column_name_2 From table_name_1 alias1 INNER JOIN table_name_2 alias2 ON alias1.column_name_n = alias2.column_name_n
```
---
**OUTER Join** Syntax
```
LEFT JOIN
RIGHT JOIN
FULL JOIN
```
- the default values will be NULL
**Cartesian JOIN**
```
SELECT column_name(s)
FROM table1
CROSS JOIN table2;
```
