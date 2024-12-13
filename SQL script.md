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
where ([variable] between '2007-02-19 19:00:00' and '2007-02-20 19:00:00') and [condition] >=< [X];
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
### Select number of [variable] and creating new variable 
```sql
select [variable], count([variable]) as [new_variable]
from [table]
group by [variable]
order by [new_variable] desc 
limit [X];
```
### Select number of [variable] and creating new variable with conditions
```sql
select [variable], count([variable]) as [new_variable]
from [table]
group by [variable]
having count [variable] >=< [X] and count[variable] >=< [X];
```

### Computing average of column
```sql
select avg([variable])
from [table];
```

### Creating buckets (above average, at the average and below) 
```sql
select [variable],  
	case
		when [variable] > [X] then 'Above average'
		when [variable] = [X] then 'At the average'
		when [variable] < [X] then 'Below the average'
		else 'No data available'
	end as [new_variable]
from [table];
```

## CREATE TABLE
### Creating a table with varchar, integer, decimal, timestamp and boolean
```sql
create table [SCHEMA NAME].[TABLE NAME] (
	[id] serial,
	[variable] varchar(200),
	[variable] integer,
	[variable] decimal(10, 3),
	[variable] timestamp,
	[variable] boolean
);
```
### Inserting data into a table
```sql
insert into [SCHEMA NAME].[TABLE NAME]([variable], [variable], [variable], [variable], [variable]) 
	values ('[X]', '[X]', [X], '[X-date]', '[X]')
           ,('[X]', '[X]', [X], '[X-date]', '[X]');
```


