## Week 3
- uses string pattern to retrieve data from the database (together with the WHERE clause)
- __%__ is called as wildcard, use to substitute for missing values/characters
- **AND and OR** operators in the WHERE clause is possible
- variablename **between** val1 **and** val2 (short hand AND)
- variablename **IN** **(list(s),)** (short hand OR)
- sorting the display of results by using the **ORDER BY** clause
- **ORDER BY** column_name_1, column_name_2, ... **(DESC)** or **(nth column specified(sort by one column))**
- recalling the distinct clause used to retrieve distinct data from a specific column
- what if we want to count the occurance?
```
select country, count(country) from Author GROUP BY country

select country, count(country) as Count (as the column name) from Author GROUP BY country having count(country) > 4
```
---
- using built-in functions in the database for retrieval
- functions for mathematics include AVG(), SUM(), MIN(), MAX(), ROUND()
- functions for string include LENGTH(), UCASE(), LCASE()
- usually the input is a set of column values and output a single value
- `` functionname(input) as new_column_name``
---
- datatime data in SQL functions
- datatype include
  1. Date - YYYYMMDD
  2. Time - HHMMSS
  3. Timestamp - YYYYXXDDHHMMSSZZZZZZ (milliseconds)
- YEAR(), MONTH(), DAY(), DAYOF(), DAYOFMONTH(), DAYOFWEEK(), WEEK(), DAYOFYEAR(), HOUR(), MINUTE(), SECOND()
- can do arithmetic operations like + 3 DAYS
- special register like CURRENT_TIME AND CURRENT_DATE IS POSSIBLE, they returns YMMDD
---
**Sub-Queries or Nested Queries**
- built in functions cannot be used in the WHERE clause
E.g.
```
Select column_name_1, column_name_2 from table_name where column_name_1 < (select AVG(column_name_1) from table_name)
```
E.g. 2 - column expressions is needed
```
select column_name_1, column_name_2, AVG(column_name_1) AS new_column_name from table_name
```
- this is not possible, instead use this
```
select column_name_1, column_name_2, (select AVG(column_name_1) from table_name) AS new_column_name from table_name
```
---
**DERIVED TABLE** can use for join operations, ...
```
select * from (select column_name_1, column_name_2 from table_name) AS new_table_name
```
---
**Working with multiple tables**
1. using Sub-queries
2. Implicit JOIN
3. JOIN operators(INNTER JOIN, OUTER JOIN, etc)
E.g.
```
select * from table_name where column_name_1 IN (select column_name_1 from table_name_2);
```
**Cartesian Join or Full Join**-every row  in the first table is join with every row in the second table
- results will have more rows than in both tables
`` select * from table_name_1, table_name_2``
short hand aliases
``select * from table_name_1, table_name_2 where table_name_1.column_name_1 = table_name_2.column_name_2``
is equivalent to
``select * from table_name_1 Alias1, table_name_2 Alias2 where Alias1.column_name_1 = Alias2.column_name_2``
aliases can be used in select clause as well
---
