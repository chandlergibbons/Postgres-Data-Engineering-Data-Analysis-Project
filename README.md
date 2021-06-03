# Postgres Data Engineering & Data Analysis Project

![](postgres_sql_gif.gif)

SQL Homework Assignment 



For this assignement I engineered a postgres database to hold sample employee data from CSV's using an [ERD](https://www.quickdatabasediagrams.com). I then imported the CSVs into a Postgres and ran some queries to get the information below.

I first ran a query to list details of each employee: employee number, last name, first name, sex, and salary.

`<SELECT employees.emp_no, employees.last_name, employees.first_name, employees.sex, salary.salary
  FROM employees
  LEFT JOIN salary
  ON employees.emp_no = salary.emp_no;r>`

Next I ran a query to list first name, last name, and hire date for employees who were hired in 1986.

`<SELECT  employees.last_name, employees.first_name, employees.hire_date
  FROM employees
  WHERE (SELECT EXTRACT (YEAR FROM hire_date) = '1986');>`

Then a ran a query that listed the manager of each department with their department number, department name, employee number, last name, first name.

`<SELECT departments.dept_no, departments.dept_name, dept_manager.emp_no, employees.last_name, employees.first_name
  FROM departments
  LEFT JOIN dept_manager
  ON departments.dept_no = dept_manager.dept_no
  LEFT JOIN employees
  ON dept_manager.emp_no = employees.emp_no;>`

The next query I created got me the department of each employee, plus their employee number, last name, first name, and department name.


List first name, last name, and sex for employees whose first name is "Hercules" and last names begin with "B."


List all employees in the Sales department, including their employee number, last name, first name, and department name.


List all employees in the Sales and Development departments, including their employee number, last name, first name, and department name.


In descending order, list the frequency count of employee last names, i.e., how many employees share each last name.




