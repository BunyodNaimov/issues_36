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

