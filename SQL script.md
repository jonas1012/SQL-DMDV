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
### Creating table with foreign key
```sql
create table [SCHEMA NAME].[TABLE NAME] (
	[variable] integer PRIMARY KEY,
	[variable] varchar(255),
	[variable] varchar(255),
	constraint FK_[variable that refers to primary key] foreign key ([variable that refers to primary key])
	references bi.[PRIMARY TABLE NAME] (id)
	);
```

### Creating multiple tables with connections and constraints
```sql
-- Department table
create table bi.Department (
	department_code serial primary key,
	deparment_name varchar(255),
	department_location varchar(255)
);

insert into BI.Department
	values (default, 'Computer Science', 'Aarhus C'),
		  (default, 'Economics and Business Economics', 'Aarhus V'),
		  (default, 'Law', 'Aarhus C'),
		  (default, 'Medicine', 'Aarhus C');


-- Student table
create table bi.Student (
	student_number serial primary key,
	student_name varchar(255),
	department_code integer,
	constraint FK_department_code foreign key(department_code)
	references BI.Department (department_code)
);

insert into BI.Student
	values (default, 'Birgit', 2),
		  (default, 'Anders', 1),
		  (default, 'Pia', 3),
		  (default, 'Henrik', 3);

-- Course
create table BI.Course(
	course_id serial primary key,
	course_name varchar(250),
	course_major varchar(250)
);

insert into bi.Course 
	values (default, 'Programming I', 'BSc in Computer Science')
		  ,(default, 'Principles of Economics', 'BSc in Economics')
		  ,(default, 'Distributed systems', 'BSc in Computer Science')
		  ,(default, 'Animal Law', 'Bsc in Law')
		  ,(default, 'Biochemistry', 'Bsc in Medicine')
		  
-- Student course
create table BI.Student_course(
	student_number integer,
	course_id integer,
	accepted varchar(50),
	constraint PK_student_course primary key (student_number, course_id),
	constraint FK_student_number foreign key (student_number)
	references BI.Student (student_number),
	constraint FK_course_id foreign key (course_id)	
	references BI.Course (course_id)
	);

insert into BI.student_course
	values (1, 2, 'Accepted')
		  ,(1, 3, 'Not accepted')
		  ,(2, 1, 'Accepted')
		  ,(3, 4, 'Accepted')
		  ,(3, 3, 'Awaiting')
		  ,(4, 2, 'Not accepted');
-- Drop tables
drop table BI.Student_course;
drop table BI.course;
drop table BI.Student;
drop table BI.Department;
```

## Joining tables for returns of data from multiple tables
### Inner join
```sql
select *
from [SCHEMA].[TABLE] 
inner join
[SCHEMA].[TABLE2] 
on [variable] = [variable];
```
### Inner join with constraints
select [TABLE].[variable],
	   [TABLE].[variable]	   
from [SCHEMA].[TABLE] 
inner join [SCHEMA].[variable] 
on [variable] = [variable]; 

