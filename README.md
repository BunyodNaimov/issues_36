                            1. HR database
## 1. From the following tables, write a SQL query to find the first name, last name, department number, and department name for each employee.
```sql
select e.first_name, e.last_name, e.department_id, d.department_name
from employees e
join departments d
on e.department_id = d.department_id
```
![image](https://user-images.githubusercontent.com/122611882/221796099-f52dd098-6774-4253-b4ca-31d492a099b8.png)

## 2. From the following tables, write a SQL query to find the first name, last name, department, city, and state province for each employee.

```sql
select e.first_name, e.last_name, d.department_name, 
    l.city, l.state_province
from employees e
join departments d
on e.department_id = d.department_id
join locations l
on d.location_id = l.location_id
```

![image](https://user-images.githubusercontent.com/122611882/221805418-1434047b-42c6-4883-a20b-739490c18573.png)

## 3. From the following table, write a SQL query to find the first name, last name, salary, and job grade for all employees.

```sql
select e.first_name, e.last_name, e.salary, j.grade_level
from employees e
join job_grades j
on e.salary between j.lowest_sal and j.highest_sal
```
![image](https://user-images.githubusercontent.com/122611882/221809485-762e8a18-188a-4a84-970d-1ab1304a9110.png)

## 4. From the following tables, write a SQL query to find all those employees who work in department ID 80 or 40. Return first name, last name, department number and department name.

```sql
select e.first_name, e.last_name, e.department_id, 
    d.department_name
from employees e
join departments d
on e.department_id = d.department_id
where e.department_id = 40 or e.department_id = 80
```
![image](https://user-images.githubusercontent.com/122611882/221818523-2444bf8d-bf56-48e8-bc38-b735882ae9fd.png)

## 5. From the following tables, write a SQL query to find those employees whose first name contains the letter ‘z’. Return first name, last name, department, city, and state province.

```sql
select e.first_name, e.last_name, d.department_name, 
    l.city, l.state_province
from employees e
join departments d
on e.department_id = d.department_id
join locations l
on d.location_id= l.location_id
where e.first_name like '%z%'
```
![image](https://user-images.githubusercontent.com/122611882/221823890-7dc47e21-a0bd-4ab9-bc69-d0ef6ff627d6.png)

## 6. From the following tables, write a SQL query to find all departments, including those without employees. Return first name, last name, department ID, department name.

```sql
select e.first_name, e.last_name, d.department_id, 
    d.department_name
from employees e
right join departments d
on e.department_id = d.department_id
```
![image](https://user-images.githubusercontent.com/122611882/221826279-582be583-bdeb-4424-91cc-009a4520b86d.png)


## 7. From the following table, write a SQL query to find the employees who earn less than the employee of ID 182. Return first name, last name and salary.
```sql
select e.first_name, e.last_name, e.salary
from employees e
join employees j
on e.salary < j.salary and s.employee_id = 182
```

## 8. From the following table, write a SQL query to find the employees and their managers. Return the first name of the employee and manager.
```sql
select e.first_name as "Ishchi_nomi",
   m.first_name as "Manager"
from employees e
join employees m
on e.manager_id = m.employee_id;
```
![image](https://user-images.githubusercontent.com/122611882/222030962-55f27d63-12b9-4b76-b384-a36c414817c4.png)

## 9. From the following tables, write a SQL query to display the department name, city, and state province for each department.

```sql
select d.department_name, l.city, l.state_province
from departments d
join locations l
on d.location_id = l.location_id
```
![image](https://user-images.githubusercontent.com/122611882/222031731-fad54089-e01d-4d6f-a8eb-ff456ece4517.png)

## 10. From the following tables, write a SQL query to find out which employees have or do not have a department. Return first name, last name, department ID, department name.

```sql
select e.first_name, e.last_name, e.department_id,
   d.department_name
from employees e
left join departments d
on e.department_id = d.department_id
```
![image](https://user-images.githubusercontent.com/122611882/222033340-e8581fa5-d37e-4016-85dd-0050eb2b0c6c.png)

## 11. From the following table, write a SQL query to find the employees and their managers. Those managers do not work under any manager also appear in the list. Return the first name of the employee and manager.
```sql
select e.first_name as "Ishchi_nomi",
    j.first_name as "Manager"
from employees e
left join employees j
on e.employee_id = j.manager_id
```
![image](https://user-images.githubusercontent.com/122611882/222036050-edb37a1d-1968-4022-90dc-39633ed0137d.png)

## 12. From the following tables, write a SQL query to find the employees who work in the same department as the employee with the last name Taylor. Return first name, last name and department ID.
```sql
select e.first_name, e.last_name, e.department_id
from employees e
join employees j
on e.department_id = j.department_id
and j.last_name = 'Taylor'
```
![image](https://user-images.githubusercontent.com/122611882/222037208-8874ef22-225c-4ee4-bc75-52671b798530.png)

## 13. From the following tables, write a SQL query to find all employees who joined on or after 1st January 1993 and on or before 31 August 1997. Return job title, department name, employee name, and joining date of the job.
```sql
select job_title, department_name, first_name || ' '|| 
    last_name as employee_name, start_date
from job_history
join jobs using (job_id)
join departments using (department_id)
join employees using (employee_id)
where start_date >= '1993-01-01' 
and start_date <= '1997-08-31'
```
![image](https://user-images.githubusercontent.com/122611882/222070963-0a554262-41d8-45cc-8aaf-366a79b2f853.png)

## 14. From the following tables, write a SQL query to calculate the difference between the maximum salary of the job and the employee's salary. Return job title, employee name, and salary difference

```sql
select 
    job_title,
    first_name || ' ' || last_name as employee_name,
    max_salary - salary as salary_difference
from employees
natural join jobs
```
![image](https://user-images.githubusercontent.com/122611882/222077964-42051135-a857-4d51-acb4-308e5edc7c88.png)


