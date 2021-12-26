## Week 4
- to connect to a Database API, we need a connection object, cursor object
- connection methods include
```
.cursor()
.commit()
.rollback()
.close()
```
- cursor methods include
```
.callproc()
.execute()
.executemany()
.fetchone()
.fetchmany()
.fetchall()
.nextset()
.arraysize()
.close()
```
- E.g. of querying with Python
```
from dbmodule import connect
# Create connection object
Connection = connect('databasename', 'username', 'password')
# Create a cursor object
Cursor = connection.cursor()
# Run Queries
Cursor.execute('select * from mytable')
Results = cursor.fetchall()
# Free resources
Cursor.close()
Connection.close()
```
