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

## CREATE TABLE

