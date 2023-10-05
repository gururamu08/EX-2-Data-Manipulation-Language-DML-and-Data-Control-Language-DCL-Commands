# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:

![1](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/39346a82-c178-4052-855a-b87accbd0875)

### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:


![2](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/fbee1a81-d09c-4025-89bb-26dd72695719)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:

![3](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/497e6a2a-acb6-4f0a-9f3f-17c23640131c)

### Q4) List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:

![4](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/496d93d7-e532-49a6-8a6c-d66819f9ebd3)


### Q5)	List the names of employee who are not Managers.
### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:

![5](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/380f67f6-07e1-4e29-af04-5670ed0c93f4)

### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:

![6](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/e3bc645b-2262-4b35-bf97-ec9180032f4d)


### Q7)	List employees whose name either start or end with ‘s’
### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:

![7](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/860c0da2-6f0f-41d4-9f7b-3a882119b8ac)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:

![8](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/8030f064-4de8-44fb-9ff3-3a502d4ac9b4)


### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:

![9](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/51846899-5f81-41e1-b784-4c54deef2201)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:

![10](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/ca9fcc45-9f9c-47f4-ad8f-c9c714787af3)


### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:

![11](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/5b8db385-e0e5-4ca6-86a3-b44f4b516ac8)


### Q12) Find number of rows in the table EMP
### QUERY:
```
select count(*) from manager;
```
### OUTPUT:

![12](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/57f2975f-c94e-489e-a718-aaaf83ef9f35)


### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
## MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:

![13 1](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/80cbf32b-b27f-4cfb-8ea2-4a890190f5c6)


## MINIMUM:
```
select min(salary) from manager;
```
## OUTPUT:

![13 2](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/87bc6e28-e621-433d-ab07-3029609edc20)


## AVERAGE:
```
select avg(salary) from manager;
```
## OUTPUT:

![13 3](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/51284610-cbde-4ca2-92ad-ba32a5d873bb)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:

![14](https://github.com/gururamu08/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118707009/c9b6b86f-f5c5-408a-bdf9-7572a7ca1c46)


### Name : GURUMOORTHI
### Register no:212222230042
### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
