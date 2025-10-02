```sql
-- Find the employee number for employees named MARTIN.
SELECT employee_number FROM employees WHERE employee_name = 'MARTIN';

-- Find the employee(s) with a salary greater than 1500.
SELECT * FROM employees WHERE salary > 1500;

-- List the names of salesmen that earn more than 1300.
SELECT employee_name FROM employees WHERE job = 'SALESMAN' AND salary > 1300;

-- List the names of employees that are not salesmen.
SELECT employee_name FROM employees WHERE job <> 'SALESMAN';

-- List the names of all clerks together with their salary with a deduction of 10%.
SELECT employee_name, salary, salary * 0.9 AS salary_after_deduction FROM employees WHERE job = 'CLERK';

-- Find the name of employees hired before May 1981.
SELECT employee_name FROM employees WHERE hire_date < '1981-05-01';

-- List employees sorted by salary in descending order (i.e. highest salary first)
SELECT employee_name, salary FROM employees ORDER BY salary DESC;

-- List departments sorted by location.
SELECT * FROM departments ORDER BY location;

-- Find name of the department located in New York.
SELECT department_name FROM departments WHERE location = 'NEW YORK';

-- You have proven your worth at the company. Your colleague comes to you trying to remember what's-his-name. It starts with a J and ends with S. Can you help her?
SELECT employee_name FROM employees WHERE employee_name LIKE 'J%S';

-- Maybe that wasn't helpful. "Oh yeah, I remember now!" they say and tell you that he is a manager.
SELECT employee_name FROM employees WHERE job = 'MANAGER' AND employee_name LIKE 'J%S';

-- How many employees are there in each department?
SELECT department_number, COUNT(*) AS number_of_employees FROM employees GROUP BY department_number;

-- List the number of employees
SELECT COUNT(*) AS number_of_employees FROM employees;

-- List the sum of all salaries (excluding commission).
SELECT SUM(salary) AS total_salaries FROM employees;

-- List the average salary for employees in department 20.
SELECT AVG(salary) AS avg_salary FROM employees WHERE department_number = 20;

-- List the unique job titles in the company.
SELECT DISTINCT job FROM employees;

-- List the number of employees in each department.
SELECT department_number, COUNT(*) AS number_of_employees FROM employees GROUP BY department_number;

-- List in decreasing order the maximum salary in each department.
SELECT department_number, MAX(salary) AS max_salary FROM employees GROUP BY department_number ORDER BY max_salary DESC;

-- List total sum of salary and commission for all employees.
SELECT SUM(salary + IFNULL(commission,0)) AS total_compensation FROM employees;
```
# opgavetechcompany
