# Code Snippets from SQL

## SELECT statements

### Select all from table
```sql
SELECT *
FROM [table];
```
### Select X amount of columns
```sql
select *
from [table]
limit 10;
```

### Select distinct values from a variable
```sql
select distinct [variable]
from [table];
```

### Select rows where it fulfills a certain condition
```sql
select [variable]
from [table]
where [condition] >=< [X];
```

### Select multiple variables which upholds multiple conditions
```sql
select [variable], [variable], [variable]
from [table]
where [condition] >=< [X] and [condition] >=< [X];
```
### Select multiple variables which upholds multiple conditions 2 (date)
```sql
select [variable], [variable], [variable]
from [table]
where ([variable] between '2007-02-19 19:00:00' and '2007-02-20 19:00:00') and [condition] > >=< [X];
```
### Select rows sorted (ascending and descending)
```sql
select * 
from [table]
order by [variable];

select * 
from [table]
order by [variable] desc;
```
## CREATE TABLE

