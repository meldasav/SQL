# SQL
select * from countries;
select * from employees;

SELECT concat(concat(lower(first_name), upper(' is the name')), concat(' and their job is: ', job_id )) from  employees;


--HEy I am farching only the job_history table
--select * from job_history;

/*
select * from departments;

select * from employees;
*/

select employee_id, first_name, last_name from employees;

select min_salary, max_salary from jobs;

select * from employees
where employee_id=200;

select first_name from employees 
where department_id=50;

select * from departments;

SELECT department_name from departments 
where department_id=10 and location_id=1700;

SELECT department_name from departments 
where department_id=10 or location_id=1700;

--Class Task
--Write the query to get all columns from the employees' table if the department id is 50 and the job id is “ST_MAN”
SELECT * FROM employees where department_id=50 and job_id = 'ST_MAN';

--Write the query to get all columns from the employees’ table if the department id is 50 or the job id is “ST_MAN”
SELECT * FROM employees where department_id=50 or job_id = 'ST_MAN';

--Write the query to get all columns from the employees’ table 
--if the department id is 70 or the salary is more than 5000
SELECT * FROM employees where department_id=70 or salary > 5000;

--Write the query to get all columns from the employees’ table 
--if the department id is 70 and the salary is more than 5000
SELECT * FROM employees where department_id=70 and salary > 5000;

--Write the query to find the employees who are not displayed in step 4.
SELECT * FROM employees where department_id!=70 and salary <= 5000;

Select * from employees;

Select * from employees
where department_id is null;

Select * from employees
where department_id is not null;

Select * from employees
where commission_pct is not null;


SELECT * FROM employees
WHERE hire_date BETWEEN '01-JULY-96' AND '31-JULY-96';

Select department_name from departments
Where department_id between 10 and 100;

Select department_name from departments
Where department_id between 10 and 20;



--Class Task
--Write the query to get all columns from employees table if salary is between 1000 and 10000
SELECT * FROM employees
WHERE salary BETWEEN 1000 AND 10000;
--Write the query to get all columns from employees table 
--if salary is between 6000 and 100000 and hire date is after June 7, 1997

SELECT * FROM employees
WHERE salary BETWEEN 6000 AND 100000 AND hire_date > '07-JUN-97';

select * from countries where region_id=2;

--First name and last name are together on the column name and in the data
select first_name || last_name from employees;

--First name and last name are together on the column name and in the data they are seperate 
--it is because of the single quatation
select first_name ||' '|| last_name from employees;

--Column name is changed to the upper case
select first_name ||' '|| last_name as firstname_lastname from employees;

--Column name stays as is.
select first_name ||' '|| last_name as "firstname_lastname" from employees;

select first_name ||' '|| last_name as "firstname lastname" from employees;

select first_name ||' '|| last_name as "FIRSTNAME LASTNAME" from employees;

SELECT * FROM EMPLOYEES;

--Class Task: 

--1. Write the query to get last name and add them ‘@gmail.com’ as columnName is ‘gmailAccount’ from employees table.
select last_name || '@gmail.com' as "gmailAccount" from employees;

--2. Write the query to get last name and add them ‘@gmail.com’ as columnName is ‘Gmail Account’ from employees table.
select last_name || '@gmail.com' as "Gmail Account" from employees;

select * from employees
order by first_name asc;

select * from employees
order by first_name desc;


select * from employees
order by salary desc;

--For multiple sorting, the column is sorted according to the first one, and then when a null value is found, 
--it sorts the column according to the second one.

select * from employees;

Select first_name, commission_pct from employees
order by commission_pct asc, first_name desc;  

--INitially it was sorting based on the department_id, but there is a null value on the department_id,
--then, it started sorting based on the last_name
select department_id, last_name from employees
order by department_id asc, last_name desc;


--Class Task
--Write the query to get all columns from the employee's table 
--for salaries more than 5000 and order the result for hire date in descending order.
select * from employees
where salary > 5000 
order by hire_date desc;

--first name starts with upper case 'A'
select * from employees
where first_name like 'A%';

--first name ends with the lower case 'a'
select * from employees
where first_name like '%a';

--first names the lower cases 'a' anywhere in the first name
select * from employees
where first_name like '%a%';

select * from employees
where first_name like '%a%r';


Select * from employees
Where first_name like '%tt%'
Order by first_name;

--We are skipping the first char on the first name and second char is a.
select * from employees
where first_name like '_a%';

--There should be minimum one char in the first name 
--and we do not put any condition in terms of letters.
select * from employees
where first_name like '_%';

--There should be min 8 chars in the first name.
select * from employees
where first_name like '________';

--There should be min 8 chars or more in the first name.
select * from employees
where first_name like '________%';

select * from employees
where first_name like 'D_v_d';

--Class Task:
--1. Write the query to find all columns from the employees’ table for first_name starting with ‘C’.
select * from employees
where first_name like 'C%';


--2. Write the query to find all columns from the employees' table for the length of last_name is 6.

select * from employees
where last_name like '______';

--3. Write the query to find all columns from the employees’ table for first_name that contains two lowercase ‘a’.
select * from employees
where first_name like '%a%a%';

select UPPER(first_name) AS first_name from employees
where first_name = 'John'; 

select LOWER(first_name) as "First Name" from employees
where first_name = 'John'; 

--Inner function makes all first names upper case
--Initcap make first letter of the first name upper case and rest of the letters in the first name keeps lower cases
select INITCAP(UPPER(first_name)) as "First Name" from employees
where first_name = 'John'; 

--Class Task

--Write the query to get all employees last names in upper case.
select UPPER(LAST_NAME) FROM EMPLOYEES;
--Write the query to get all employees emails in lower case.
select LOWER(EMAIL) FROM EMPLOYEES;
--Write the query to get all employees first name in upper case, last names in lower case and emails in only first letter upper case. 
select UPPER(FIRST_NAME), LOWER(last_name), INITCAP(EMAIL) FROM EMPLOYEES;

select concat ('Techglobal – ' ,first_name) as TECHGLOBAL from employees;

select 'Techglobal – ' || first_name as TECHGLOBAL from employees;

select REGION_NAME, length(region_name) from regions;

select * from employees;

--3 represents which letter we start cutting 5 represents number of the letter we are getting
select substr(first_name,3,5) from employees where first_name='Alexander';

select substr(first_name,1,6) from employees where first_name='Alexander';

--It is find the index of the string. It is getting the firt location if there are multiple letters.
select city, instr(city, 'a') from locations;

--Class Task
--5.  Write the query to get all last names that starting from index number 2 and upto 4 character from employees.
select last_name, substr(last_name,2,4) from employees;

--6.  Write the query to get all last names that starting from index number 4 from employees .
select last_name, substr(last_name,4) from employees;

--7. Write the query to find the city includes 'a' character in locations table.
--Option 1
select city from locations where city like '%a%'; 
--Option 2
select city, instr(city, 'a') from locations where instr(city, 'a')!=0; 

--8. Write the query to return first name and last name combined as lower case with the space 
--and find the index number of 'ka' from combined firstname and lastname from employees.
--Option 1
select lower(concat(first_name, concat(' ',last_name))), instr(lower(concat(first_name, concat(' ',last_name))), 'ka') from employees;
--Option 2
select lower(first_name || ' ' || last_name) from employees;

select first_name, instr(first_name, 'a') from employees;

select instr(lower(first_name || ' ' || last_name), 'ka') from employees;

select lower(first_name || ' ' || last_name) as "first_name last_name", instr(lower(first_name || ' ' || last_name),'ka') as "index of ka" from employees;

--ROUND( number [, decimal_places] )

SELECT ROUND(125.315)  FROM DUAL;      

SELECT ROUND(125.315, 0)  FROM DUAL;    

SELECT ROUND(125.315, 1)  FROM DUAL;    

SELECT ROUND(125.315, 2)  FROM DUAL;

SELECT ROUND(125.3154, 3)  FROM DUAL;

SELECT ROUND(-125.3155, 3)  FROM DUAL;

select ROUND(125.315) from dual;     --Result: 125 

select ROUND(125.315, 0) from dual;  --Result: 125 

select ROUND(125.315, 1) from dual;  --Result: 125.3 

select ROUND(125.315, 2) from dual;  --Result: 125.32 

select ROUND(125.315, 3) from dual;  --Result: 125.315 

select ROUND(-125.315, 2) from dual; --Result: -125.32  

SELECT ROUND(123.456, -1) FROM DUAL;--Result: 120

SELECT ROUND(123.456, -2) FROM DUAL; --Result: 100

SELECT ROUND(123.456, -3) FROM DUAL; --Result: 

SELECT TRUNC(123.456) FROM DUAL;                  --Result: 123

SELECT TRUNC(123.456, 0) FROM DUAL;              --Result: 123

SELECT TRUNC(123.456, 1) FROM DUAL;              --Result: 123.4

SELECT TRUNC(123.456, 2) FROM DUAL;               --Result: 123.45

SELECT TRUNC(123.456, 3) FROM DUAL;                --Result: 123.456

SELECT TRUNC(-123.456, 2) FROM DUAL;               --Result: -123.45

SELECT TRUNC(123.456, -1) FROM DUAL;               --Result: 120

SELECT TRUNC(123.456, -2) FROM DUAL;               --Result: 100

SELECT TRUNC(123.456, -3) FROM DUAL;                --Result: 0

select * from employees;

select UPPER(first_name) from employees where manager_id=100;

select * from employees where first_name='Karen';

--
SELECT ROUND(AVG(salary), 2) FROM EMPLOYEES;

select * from employees;

SELECT COUNT (*) FROM EMPLOYEES;

SELECT COUNT (salary) FROM EMPLOYEES;

-- when we specify the column name on the count,  it does not count the null values
SELECT COUNT (commission_pct) FROM EMPLOYEES;
-- we are validating that, when we specify the column number with count id does not fetch the null values
SELECT COUNT (commission_pct) FROM EMPLOYEES where commission_pct is not null;

-- It ignores the null values
SELECT MAX(salary) FROM EMPLOYEES;

SELECT MIN(salary) FROM EMPLOYEES;

select * from employees ;

select max(first_name) from employees;

select min(first_name) from employees;

select * from employees order by first_name desc;

select max(hire_date) from employees;

Select sum(salary) from employees;

--Class Task
--Write the query to find the count of employees if the employee first name has more than 4 character.

SELECT COUNT(FIRST_NAME) FROM EMPLOYEES
WHERE LENGTH(FIRST_NAME) > 4; 

select count (first_name) from employees where first_name like '_____%';

--Find the number of the first name which includes two 'a's  in it.
select count(first_name) from employees
where first_name like '%a%a%';

--As we consider given salaries are monthly, Write the query to find the total salary in yearly.
select sum(salary * 12) from employees;

-- Distinct fetches only the unique values from the column. 
-- If the value is duplicate it takes one of them.

select * from employees;

SELECT DISTINCT(FIRST_NAME) FROM EMPLOYEES;

select count(first_name) from employees
where first_name = 'Ellen';

select count(first_name) from employees
where first_name = 'Alexander';

select count(first_name) from employees
where first_name = 'Allan';

select distinct(first_name) from employees
where first_name = 'Alexander';

--Example  1
select * from countries;

select count(country_name) from countries;

select region_id, count(country_name) from countries group by region_id;

select region_id, count(country_name), count(country_id) from countries 
group by region_id 
order by region_id desc;


--Example 2
select region_id, count(country_name) as number_of_countries 
from countries group by region_id 
order by region_id;

--Class Task:
--Write a query to get number of employees for same manager id which is not null and order by manager id.
--SELECT, WHERE, GROUP BY, ORDER BY

select manager_id, count(first_name)  from employees
where manager_id is not null
group by manager_id
order by manager_id;

select manager_id, count(first_name)  from employees
where manager_id is not null
group by manager_id
order by count(first_name);

--Write a query to get number of employees for same job id and order by number of employees it is found.
--SELECT, WHERE, GROUP BY, ORDER BY

select * from employees;

SELECT job_id, COUNT(*) FROM employees
group by job_id
order by COUNT(*);

--Write a query to get max salary for each department id which is not null.

select max(salary), department_id from employees
where department_id is not null
group by department_id
order by max(salary) desc;


--Write a query to get min salary for each department id 
--that has min salary more than 5000 and department is not null.

select min(salary) from employees
where salary>5000 and department_id is not null
group by department_id;

--Write a query to get sum of salaries for each job id and order by sum ascending.
select job_id, sum(salary), count(*) from employees
group by job_id
order by sum(salary) asc;

--Write a query to get max of sum of salaries for each job id.
select max(sum(salary)) from employees --- print also the job_id
group by job_id;

--Write a query to group employees by their first name’s first letter 
--and get the number of employees for each group and order by the numbers that are found.

select substr(first_name, 1, 1), count (*) from employees
GROUP BY substr(first_name, 1, 1)
order by count(*);


--Having

select round(avg(salary)) from employees
where avg(salary)>7000  --It does not work because where clause does not work with the aggrigate functions
group by department_id;

select round(avg(salary)) from employees
group by department_id
having avg(salary)>7000;

--Class Task:
--Write a query to count employees under same manager id that is not null.
--Option  1
select manager_id, count(*) from employees 
where manager_id is not null
group by manager_id;

--Option  2

select manager_id, count(first_name) from employees 
group by manager_id
having manager_id is not null;


--Write a query to get manager id and lowest paid employees for each manager 
--and make sure that manager is not null and lowest salary is higher than 6000 
--and then order by lowest salaries descending. 

select manager_id, min(salary) from employees
group by manager_id 
having manager_id is not null and min(salary)>6000
order by min(salary) desc;

--select salary from employees where manager_id=145; 

--SubQueries
--Name of the employee who is getting the max salary from employees table
select first_name from employees
where salary=(select max(salary) from employees);

select first_name, salary from employees
where salary=(select max(salary) from employees);


select first_name, salary from employees;

--select first_name, max(salary) from employees; 
-- we  cannot get the  name of the employee is because there is also aggregate function as a column name.
-- if we would use group by function, it worked.

select first_name, salary from employees
where salary=(select max(salary) from employees);



--Class Task
--Write a query to get employees first_name 
--and salary who makes more than employee who has employee_id 121 and then order by salary ascending.
select first_name, salary from employees
where salary > 3000
order by salary;

select first_name, salary from employees
where salary > (select salary from employees where employee_id = 121)
order by salary;

--Write a query to get employees first_name, department_id 
--who works in same department with employee who has employee_id 150.
select first_name, department_id from employees
where department_id =( select department_id from employees where employee_id=150);



--Write a query to find second largest salary. (This is the interview question)

select salary from employees order by salary desc;

select max(salary) from employees
where salary< (select Max(salary) from employees);

--Write a query to get name of employees who is making second largest salary.

select first_name, max(salary) from employees
where salary< (select Max(salary) from employees); -- you will get an error becasu 
--you cannot just use column name with aggregate functions without group by

--give me the first names if the salary is equal to second largest salary
select first_name from employees
where salary =(select max(salary) from employees
where salary < (select Max(salary) from employees));

--Write a query to get number of postal code under same countries from locations table.

select country_id, count(postal_code) from locations
group by country_id;

--Write a query to get number of postal code under same countries from locations table 
--if their count is more than 1.
select country_id, count(postal_code) from locations
group by country_id
HAVING count(postal_code)>1; --We cannot use where clause because of the aggrigate function count.
--instead we should use having function


--Write a query to get all employees who is making more than average salary and order by salary.
select * from employees 
where salary > (select avg(salary) from employees)
order by salary;

--Write a query to get all cities' names which have same state with Toronto from locations table.
select * from locations;

select city from locations 
where state_province = (select state_province from locations where city = 'Toronto');

--Write a query to find the employee who is making second lowest salary.

select first_name, salary from employees order by salary;


select first_name from employees where salary =
(select min(salary) from employees where salary > (select min(salary) from employees));

--ROWNUMBER

select first_name, salary
from employees where rownum<10
order by salary desc;

--JOINS 
-- it is getting all the columns from both tables
select * from regions 
join countries on regions.region_id = countries.region_id;

--Write the query to the print country name, country id, and region name for each country.
select * from regions;
select * from countries;

select * from regions r
join countries c 
on r.region_id=c.region_id;

select c.country_name, c.country_id, r.region_name  from regions r
join countries c 
on r.region_id=c.region_id;

select c.country_name, c.country_id, r.region_name from regions r
join countries c on r.region_id=c.region_id;


--This query will fail it is because of the there are two region_id s.
-- so we need to specify from which table we will get the region id
select region_id from regions 
join countries on regions.region_id = countries.region_id;

-- it is getting region_id from countries table
select countries.region_id from regions 
join countries on regions.region_id = countries.region_id;

--This query will pass because there is only one region_name on both tables
select region_name from regions 
join countries on regions.region_id = countries.region_id;

select regions.region_name from regions 
join countries on regions.region_id = countries.region_id;


--Alias
select countries.region_id from regions 
join countries on regions.region_id = countries.region_id;

--For the tables we use alias. We used c for countries table 'r' for regions table
select c.region_id from regions r 
join countries c on r.region_id = c.region_id;

--CLASS TASK

--Write the query to the print country name, country id, and region name for each country.

select c.country_name, c.country_id, r.region_name from regions r
join countries c on r.region_id=c.region_id;

--following query has also region_id from both tables 
--but we choose to get it from region table
select c.country_name, c.country_id, r.region_name, r.region_id from regions r
join countries c on r.region_id=c.region_id;

--Write the query to print the last name, email, and  job title for each employee.

select e.last_name, e.email, j.job_title from jobs j
join employees e 
on j.job_id=e.job_id;


--INNER JOIN

--IT brings the result only matching data from the tables

select e.last_name, e.email, j.job_title
from employees e inner join jobs j
on e.job_id=j.job_id;



select * from employees;
select * from departments;

select *
from employees e  inner join departments d
on e.department_id=d.department_id;

select * from country;
delete country;
Create table country (country_id number(3), Country_name varchar(20));
Insert into country values(1, 'USA');
Insert into country values(2, 'Canada');
Insert into country values(4, 'Japan');
Insert into country values(NULL, '');

select * from state;

Create table state (state_id number(3), country_id number(3), state_name varchar(20));
Insert into state values(1, 1, 'Chicago');
Insert into state values(2, 1, 'Texas');
Insert into state values(3, 2, 'Ontorio');
Insert into state values(4, Null, 'Wisconsin');
Insert into state values(Null, Null, Null);

--delete country where country_id is null;
--delete state where state_id is null;
--update state set state_name='Illinois' where state_id=1;


select * from state s 
inner join country c
on s.country_id = c.country_id;

select s.state_name, c.country_name  from state s 
inner join country c
on s.country_id = c.country_id;

select *
from employees e  inner join departments d
on e.department_id=d.department_id;

-- LEFT JOIN
-- It is getting all the data from left table and matching data from both tabels
select * from state s
LEFT join country c
on s.country_id = c.country_id;

select s.state_name, c.country_name from state s
LEFT join country c
on s.country_id = c.country_id;

-- RIHT JOIN
--WE are getting the all data from the right table and only maching ones from the left table

select * from state s
right join country c
on s.country_id = c.country_id;

select s.state_name, c.country_name from state s
right join country c
on s.country_id = c.country_id;

--Outer Join

select * from state s
full outer join country c
on s.country_id = c.country_id;

select s.state_name, c.country_name from state s
full outer join country c
on s.country_id = c.country_id;

/* 3. Write a query to display the name (first name and last name), salary, department id 
for those employees who earn such amount of salary which is the smallest salary of any of the departments. */

select salary from employees;

SELECT first_name,
       last_name,
       salary,
       department_id
  FROM employees
  WHERE salary IN (SELECT MIN(salary)
                     FROM employees
                     GROUP BY department_id);
                     
select count(department_id) from employees
group by department_id;

SELECT MIN(salary), department_id
                    FROM employees
                     GROUP BY department_id;
                     
                     
 --SELF JOINS
 
 select employee_id, first_name, manager_id from employees;
 
 
 Create table report (emp_id number(3), emp_name varchar(20), Job_id varchar(20), mgr_id number(3));
Insert into report values(1, 'Alex', 'Clerk', 4);
Insert into report values(2, 'James', 'Sales_Rep', 3);
Insert into report values(3, 'Christen', 'Accountant', 4);
Insert into report values(4, 'Nils', 'Manager', null);
Insert into report values(5, 'Mike', 'Asst_Manager', 4);
 
select * from report;

SELECT * FROM REPORT E 
JOIN REPORT M 
ON E.MGR_ID=M.EMP_ID;

SELECT E.EMP_NAME EMP_NAME, M.EMP_NAME MGR_NAME FROM REPORT E 
JOIN REPORT M 
ON E.MGR_ID=M.EMP_ID;


--Write a query to get count of employees for each manager and order by count of employees.
 
 
select count(e.employee_id), m.employee_id from employees e
join employees m 
on e.manager_id=m.employee_id
group by m.employee_id
order by count(e.employee_id);
 
 select count(e.employee_id), m.employee_id from employees e
 join employees m 
 on e.manager_id=m.employee_id
 group by m.employee_id
 order by count(e.employee_id);
 
select e.employee_id, e.first_name, m.employee_id, m.first_name from employees e
join employees m on e.manager_id=m.employee_id;

 --join Version 
 
 --1 regular

Select d.department_name, d.manager_id, d.location_id, l.city, l.state_province
From locations l right outer join departments d
On d.location_id=l.location_id;

--Version 2 with where clause

Select d.department_name, d.manager_id, d.location_id, l.city, l.state_province
From locations l, departments d
where d.location_id=l.location_id;

--Version 3 natural join

Select department_name, manager_id, location_id, city, state_province From locations  natural join departments;

--Natural joins is eliminiting one of the same columns
select * from employees natural join departments;

select * from employees e 
join departments d
on e.department_id=d.department_id;


select first_name, department_name 
from employees e  
join departments d
on (e.manager_id=d.manager_id and e.department_id=d.department_id);


---Version 4 with “using” keyword

Select department_name, manager_id, location_id, city, state_province
From locations join departments 
Using(location_id);

--CLASS TASK
--3. Write the query to find count of employees for each state province.

SELECT l.state_province, count(e.employee_id)
FROM locations l JOIN departments d 
ON l.location_id = d.location_id
JOIN employees  e 
ON d.department_id = e.department_id
group by l.state_province;

select * from locations;
select * from departments where location_id =1100;

--4- Write the query to find last name , department name, city, country name, region name for each employee
--TABLES TO JOIN:  employees, departments, countries, locations, regions
Select e.last_name, d.department_name, l.city, c.country_name, r.region_name from employees e 
Join departments d on e.department_id=d.department_id
Join locations l on d.location_id=l.location_id
Join countries c on c.country_id=l.country_id
Join regions r on r.region_id=c.region_id;

--SET OPERATORS

--UNION
--UNION -> UNION is used to combine the results of two or more SELECT statements. 
--However, it will eliminate duplicate rows from its result, and output is sorted. 
--And it is not desired from the performance aspect 
--because it is removing the duplicate and sorting the output.

--UNION brings us the unique values
Select first_name, last_name, department_id from employees where department_id in (10,20)
UNION
Select first_name, last_name, department_id from employees where department_id in (20,40);

--UNION ALL -> This operation is like Union. 
--But it also shows the duplicate rows and it will not sort the data 
--and preferred from the performance aspect.

Select first_name, last_name, department_id from employees where department_id in (10,20)
UNION ALL
Select first_name, last_name, department_id from employees where department_id in (20,40);

--INTERSECT -> Intersect operation is used to combine two SELECT statements, 
--but it only returns the records which are common from both SELECT statements. 
--In the case of Intersect, the number of columns and datatype must be the same.

Select first_name, last_name, department_id from employees where department_id in (10,20)
INTERSECT
Select first_name, last_name, department_id from employees where department_id in (20,40);

--MINUS -> The Minus operation combines results of two SELECT statements 
--and returns only those in the result, 
--which belong to the first set of the result.


Select first_name, last_name, department_id from employees where department_id in (10,20)
MINUS
Select first_name, last_name, department_id from employees where department_id in (20,40);

--Class Task
--Write a query to get not duplicated employees’ first_name, hire_date, and salary 
--where salary range is 4000 to 7000 and 6000 to 9000 and then order by salary.
SELECT FIRST_NAME, HIRE_DATE, SALARY FROM EMPLOYEES WHERE SALARY IN (4000,7000)
UNION
SELECT FIRST_NAME, HIRE_DATE, SALARY FROM EMPLOYEES WHERE SALARY IN (6000,9000)
ORDER BY SALARY;

--CREATING THE TABLE

--command    name
Create table students (student_id number(3), full_name varchar(30), class_id number(3));

select * from students;

Insert into students values(101, 'Abe', 4);
Insert into students values(102, 'Ahmad', 4);
Insert into students values(103, 'Alona', 4);
Insert into students values(104, 'Andrei',4);
Insert into students values(105, 'Kaly', 4);
Insert into students values(106, 'Daria', 4);
Insert into students values(107, 'Datkaiym', 4);
Insert into students values(108, 'David', 4);
Insert into students values(109, 'Deniz', 4);
Insert into students values(110, 'Guluzar', 4);
Insert into students values(111, 'Ismail', 4);
Insert into students values(112, 'Jonathan', 4);
Insert into students values(113, 'Kaycee', 4);
Insert into students values(114, 'Kerem', 4);
Insert into students values(115, 'Melda', 4);
Insert into students values(116, 'Naim', 4);
Insert into students values(117, 'Nataliia', 4);
Insert into students values(118, 'Ozden', 4);
Insert into students values(119, 'Rami', 4);
Insert into students values(120, 'Reem', 4);
Insert into students values(121, 'Regina', 4);
Insert into students values(122, 'Salah', 4);
Insert into students values(123, 'Sheker', 4);
Insert into students values(124, 'Tasniem', 4);
Insert into students values(125, 'Taylor', 4);
Insert into students values(126, 'Torrie', 4);
Insert into students values(127, 'Uthman', 4);
Insert into students values(128, 'Vita', 4);
Insert into students values(129, 'Yakeen', 4);
Insert into students values(130, 'Murat', 1);
Insert into students values(131, 'Bahar', 1);
Insert into students values(132, 'Dajve', 1);
Insert into students values(133, 'Mariia', 1);

--changing the column name on the students table
Alter table students rename column full_name to name;

select * from students;

--inserting another student for batch 5
Insert into students values(134, 'John', 5);

--Class Task:
--Write a query to get name and class name for each student.


select name,class_id from students;

--Update the student
Update students set student_id= 999, name='Burak Simsek' where student_id = 134;

Delete students where student_id = 999;

select * from students;






