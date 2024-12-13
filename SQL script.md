# Code Snippets from SQL

## SELECT statements
```sql
# Select all from table
SELECT *
FROM [table];

# Select X amount of columns
select *
from [table]
limit 10;

# Select distinct values from a variable
select distinct [variable]
from [table];

# Select rows where it fulfills a certain condition
select [variable]
from [table]
where [condition] >=< [X];

# Select multiple variables which upholds multiple conditions
select [variable], [variable], [variable]
from [table]
where [condition] >=< [X] and [condition] >=< [X];
```

## CREATE TABLE

